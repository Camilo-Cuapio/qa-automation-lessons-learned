## 🚀 Allure shows 0 tests
🧪 Problem

//The Allure report was showing "0 test cases" even though the tests were running successfully with Maven.

🔍 Cause

The allure-results folder was either not being generated or was not properly configured.

//✅ Solution
Verify that the allure.properties file exists:
allure.results.directory=target/allure-results
Run the tests:
mvn clean test
Generate the report:
allure serve target/allure-results
💡 Lesson Learned

Allure completely depends on the results generated in the allure-results folder.
If the folder does not exist or is empty, the report will show 0 test cases.

Allure dependencies were updated from version 4 to version 5.

The Allure version was upgraded because the previous version was outdated.