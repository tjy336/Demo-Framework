
markdown
# Demo Framework

A lightweight and modular iOS framework for decoupling view controller navigation logic.  
Simplify your code structure and enable dynamic in-app routing!

---

## Table of Contents
1. [Features](#features)
2. [Requirements](#requirements)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Advanced Configuration](#advanced-configuration)
6. [License](#license)
7. [Project Glossary](#project-glossary)

---

## Features
- **Decoupled Navigation**: Navigate between controllers without direct dependencies.
- **Dynamic Routing**: Supports identifier-based or URL scheme navigation.
- **Swift 5.7+ Support**: Fully compatible with modern Swift syntax.
- **iOS 13+ Optimization**: Designed for iOS 13 and later versions.
- **Error Handling**: Built-in safety checks for invalid identifiers.
- **Lightweight**: Zero third-party dependencies.

---

## Requirements
- iOS 13.0+
- Xcode 14.0+
- Swift 5.7+
- CocoaPods 1.10.0+ (if using CocoaPods)

---

## Installation

### CocoaPods (Recommended)
1. Add the following line to your `Podfile`:
   ```ruby
   pod 'demo-framework', '1.0.3'

2.  Run `pod install`.
    
3.  Import the framework in your Swift files:
    
    swift  
    import DemoFrameworkKit
    

### Manual Installation

1.  Download the `DemoFrameworkKit.xcframework` from the [Releases](https://github.com/PritKothadiya/Demo-Framework/releases) page.
    
2.  Drag the `.xcframework` into your Xcode project.
    
3.  Select "Embed & Sign" in the target settings.
    

----------

## Usage

### Basic Navigation

1.  **Define a View Controller Identifier**:  
    Set a unique identifier in your Storyboard or code (e.g., `"HomeVC"`).
    
2.  **Programmatic Navigation**:
    
    swift
    DemoNavigator.openViewController(identifier: "HomeVC")
    

### URL Scheme Support

Navigate using custom URLs (e.g., `myapp://home`):

swift
DemoNavigator.openViewController(url: URL(string: "myapp://home")!)

### Error Handling

Gracefully handle invalid identifiers:

swift
do {
    try DemoNavigator.safeOpenViewController(identifier: "SettingsVC")
} catch {
    print("Navigation failed: \(error.localizedDescription)")
}

----------

## Advanced Configuration

### Custom Navigation Stack

Override the default navigation controller:

swift
DemoNavigator.configureNavigationController(UINavigationController.self)

### Debug Logging

Enable logs for troubleshooting:

swift
DemoNavigator.isLoggingEnabled = true

----------

## License

Distributed under the MIT License.  
See [LICENSE](https://license/) for details.

----------

## Project Glossary

English

Description

Framework

A reusable code library structure

View Controller

Component managing UI and business logic

Identifier

Unique string for resource identification

Dependency Manager

Tool for managing third-party libraries

Dynamic Routing

Flexible navigation through configuration

Debug Logging

Log output for issue diagnosis

Error Handling

Mechanism to catch and manage exceptions

