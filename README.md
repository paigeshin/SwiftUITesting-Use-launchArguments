# SwiftUITesting-Use-launchArguments


```swift
class OnboardingUITests: XCTestCase {
    var app: XCUIApplication!

    // MARK: - XCTestCase

    override func setUp() {
        super.setUp()

        // Since UI tests are more expensive to run, it's usually a good idea
        // to exit if a failure was encountered
        continueAfterFailure = false

        app = XCUIApplication()

        // We send a command line argument to our app,
        // to enable it to reset its state
        app.launchArguments.append("--uitesting")
    }
}

func application(_ application: UIApplication,
                 didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey : Any]?) -> Bool {
    if CommandLine.arguments.contains("--uitesting") {
        resetState()
    }

    // ...Finish setting up your app

    return true
}

```
