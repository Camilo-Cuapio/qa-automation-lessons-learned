📁 5. Issues with PATH and Allure CLI
## 🧪 Problem
The `allure --version` command was showing an outdated version or the command was not recognized.

## 🔍 Cause
- Incorrect path in environment variables (PATH)  
- Conflict between manually installed versions and those installed with Scoop  

## ✅ Solution

1. Verify the executable location:

```powershell
Get-Command allure
Remove old versions
Install/update with Scoop:
scoop update
scoop update allure
Validate:
allure --version

💡 Lesson Learned

A system can have multiple versions of the same tool.
Always verify which executable is actually being used.