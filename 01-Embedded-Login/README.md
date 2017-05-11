# Embedded Login

- [Full Tutorial](https://auth0.com/docs/quickstart/native/ios-swift/01-embedded-login)

This sample project shows how to present a login dialog using the Lock widget interface. Once you log in, you're taken to a very basic profile screen, with some data about your user.

#### Important Snippets

##### 1. Present the login widget

In `HomeViewController.swift`:

```swift
@IBAction func showLoginController(_ sender: UIButton) {
  Lock
      .classic()
      .onAuth { credentials in
          guard let accessToken = credentials.accessToken else { return }
          self.showSuccessAlert(accessToken)
      }
      .present(from: self)
}
```
