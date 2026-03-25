## 🚀 Use of @ExtendWith
## 🧪 Problem
There was a need to execute additional logic during test execution (e.g., screenshots).

## 🔍 Cause
JUnit 5 requires extensions to add additional behavior.

## ✅ Solution
`@ExtendWith` was used to register extensions:

//```java
@ExtendWith({
    ScreenshotOnFailureExtension.class,
    io.qameta.allure.junit5.AllureJunit5.class
})

💡 Lesson Learned

@ExtendWith allows you to integrate functionalities such as:

Custom hooks
Integrations (e.g., Allure)
Test lifecycle event handling