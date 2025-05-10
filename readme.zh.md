# Demo Framework 

Lightweight modular iOS framework for decoupling view controller navigation logic.  
Simplify code structure and enable in-app dynamic routing!

---

## Project Introduction <!-- by Xu Peibin -->

### Background
In iOS app development, as features continuously iterate and code complexity increases, navigation logic between view controllers becomes more intricate and harder to maintain. Traditional navigation approaches often suffer from tight coupling, leading to code that's difficult to reuse, increased testing complexity, and limited development flexibility.  
To address these pain points, **Demo Framework** was created, aiming to provide developers with a lightweight, extensible navigation solution through modular design and dynamic routing mechanisms.

### Overview
- **Decoupled Navigation**: Navigate between view controllers using identifiers or URL protocols without direct dependencies.
- **Dynamic Routing**: Support flexible configuration of dynamic jump logic.
- **Swift 5.7+ Support**: Fully leverages modern Swift features for enhanced productivity.
- **iOS 13+ Optimization**: Tailored for iOS 13 and later versions.
- **Error Handling**: Built-in invalid identifier safety checks.
- **Lightweight Design**: No third-party dependencies, easy installation and integration.

### Use Cases
1. **Modular Development in Large Projects**  
   Improve code reusability and reduce maintenance costs through decoupled navigation logic, ideal for long-term iterative development in large projects.
   
2. **Flexible Dynamic Routing**  
   Supports navigation via identifiers or URL protocols, suitable for in-app multi-scenario jumps (deep linking, dynamic content loading, etc.).
   
3. **Rapid Prototyping**  
   Accelerate MVP or prototype development with lightweight design and simple APIs.
   
4. **Enhanced User Experience**  
   Leverage error handling and debug logging to identify and resolve potential issues, delivering a more stable user experience.

---

## Table of Contents
1. [Features](#features)
2. [Requirements](#requirements)
3. [Installation](#installation)
4. [Usage Guide](#usage-guide)
5. [Advanced Configuration](#advanced-configuration)
6. [Contributing](#contributing)
7. [License](#license)

---

## Features 
- **Decoupled Navigation**: Navigate without direct dependencies.
- **Dynamic Routing**: Support identifier/URL-based navigation.
- **Swift 5.7+ Support**: Modern Swift compatibility.
- **iOS 13+ Optimization**: Built for iOS 13+.
- **Error Handling**: Safe identifier validation.
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
1. Add to your `Podfile`:
   ```ruby
   pod 'demo-framework', '1.0.3'
Run pod install.

Import in Swift files:

swift
import DemoFrameworkKit
Manual Installation
Download DemoFrameworkKit.xcframework from Releases.

Drag the .xcframework into your Xcode project.

Select "Embed & Sign" in Target settings.

Usage Guide
Basic Navigation
Define Controller Identifier:
Set unique identifiers in Storyboard or code (e.g., "HomeVC").

Programmatic Navigation:

swift
DemoNavigator.openViewController(identifier: "HomeVC")
URL Protocol Support
Navigate using custom URLs (e.g., myapp://home):

swift
DemoNavigator.openViewController(url: URL(string: "myapp://home")!)
Error Handling
Gracefully handle invalid identifiers:

swift
do {
    try DemoNavigator.safeOpenViewController(identifier: "SettingsVC")
} catch {
    print("Navigation failed: \(error.localizedDescription)")
}
Advanced Configuration
Custom Navigation Stack
Override default navigation controller:

swift
DemoNavigator.configureNavigationController(UINavigationController.self)
Debug Logging
Enable logs for troubleshooting:

swift
DemoNavigator.isLoggingEnabled = true
Contributing
We welcome contributions! Please read our Contribution Guidelines before submitting PRs.

License
Open-source under MIT License.
See LICENSE.

Glossary (CN-EN)
Chinese	English	Description
框架	Framework	Reusable code library
视图控制器	View Controller	Manages UI and interaction logic
标识符	Identifier	Unique resource identifier string
依赖管理工具	Dependency Manager	Manages third-party libs (e.g., CocoaPods)
动态路由	Dynamic Routing	Flexible jump logic via configuration
调试日志	Debug Logging	Log output for troubleshooting
错误处理	Error Handling	Exception catching and handling
