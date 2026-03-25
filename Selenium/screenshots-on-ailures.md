## 🚀 Screenshots on Failures
## 🧪 Problem
No visual evidence was generated when a test failed.

## 🔍 Cause
There was no implementation to capture screenshots in case of failure.

## ✅ Solution
A JUnit 5 `TestWatcher` was implemented, along with `AfterTestExecutionCallback` to properly hook into the test lifecycle:

```java
public class ScreenshotOnFailureExtension implements TestWatcher, AfterTestExecutionCallback {

    @Override
    public void testFailed(ExtensionContext context, Throwable cause) {
        WebDriver driver = ((BaseTest) context.getRequiredTestInstance()).getDriver();

        byte[] screenshot = ((TakesScreenshot) driver)
                .getScreenshotAs(OutputType.BYTES);

        Allure.addAttachment(
                "Failure Screenshot",
                new ByteArrayInputStream(screenshot)
        );
    }

    @Override
    public void afterTestExecution(ExtensionContext context) {
        // Additional lifecycle handling if needed
    }
}

And it was registered with:

@ExtendWith(ScreenshotOnFailureExtension.class)

💡 Lesson Learned

Automatic evidence greatly simplifies debugging and improves the quality of test reports.