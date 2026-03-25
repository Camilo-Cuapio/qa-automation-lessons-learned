## 🚀 Allure Report Deployment Summary (GitHub Pages)

During the setup and publication of Allure Reports, a common issue occurred when switching between branches due to generated files being tracked by Git.

### 🔴 Problem

The `allure-report/` directory was mistakenly added to version control in the `main` branch. This caused conflicts when attempting to switch to the `gh-pages` branch, as Git prevented overwriting tracked and untracked files.

### 🚀 Impact

This issue prevented branch switching and blocked the proper publication of the report on GitHub Pages.  
The solution enabled separation between generated artifacts and source code, stabilizing the deployment workflow.

### ✅ Solution

1. Removed `allure-report` from version control:

   ```bash
   git rm -r --cached allure-report

Added generated folders to the .gitignore file:

allure-report/
target/
Committed the changes to clean up the repository.
Successfully switched to the gh-pages branch.

Generated the Allure report from test execution results:

mvn clean test
allure generate target/allure-results --clean -o allure-report
Copied the report files (not the folder itself) into the gh-pages branch.

Published the report using:

git add .
git commit -m "deploy: publish allure report"
git push origin gh-pages --force
🎯 Result

The Allure report was successfully published using GitHub Pages and is now accessible via a public URL for portfolio and demonstration purposes.

🧠 Key Learnings
Always ignore generated files (target/, allure-report/)
Use a dedicated branch (gh-pages) for deployment
Ensure index.html is located at the root of the published branch
Do not mix source code with generated files in the same branch
⚙️ GitHub Pages Configuration

REPOSITORY → SETTINGS → PAGES → BRANCH → gh-pages / (root) → Save

🔄 Update Allure Report
mvn clean test
allure generate target/allure-results --clean -o allure-report
git checkout gh-pages
git rm -rf .
xcopy /E /I /Y allure-report\* .
git add .
git commit -m "update report"
git push origin gh-pages --force