## 🚀Difference Between JUnit and Allure Annotations
## 🧪 Problem
There was confusion between JUnit 5 and Allure annotations.

## 🔍 Cause
Both frameworks use annotations, but for different purposes.

## ✅ Explanation

### JUnit 5
Controls test execution:

//```java
@Test
@DisplayName("Successful login")
Allure

Adds metadata to the report:

@Description("Verifies that the user can log in")
@Feature("Authentication")
@Story("Login")
@Severity(SeverityLevel.CRITICAL)

💡 Lesson Learned

JUnit → Executes tests
Allure → Documents and reports

Both work together but have different responsibilities.