# Demo Framework 

Lightweight modular iOS framework for decoupling view controller navigation logic.  
Simplify code structure and enable in-app dynamic routing!

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

## Project Introduction <!-- by Xu Peibin -->

### Background
In iOS app development, as features continuously iterate and code complexity increases, navigation logic between view controllers becomes increasingly complex and difficult to maintain. Traditional navigation approaches often suffer from tight coupling issues, leading to reduced code reusability, increased testing difficulty, and limited development flexibility.  
To address these pain points, **Demo Framework** was born, aiming to provide developers with a lightweight and extensible navigation solution through modular design and dynamic routing mechanisms.

### Overview
- **Decoupled Navigation**: Navigate between view controllers using identifiers or URL protocols without direct dependencies.
- **Dynamic Routing**: Support flexibly configurable dynamic routing logic.
- **Swift 5.7+ Support**: Fully leverages modern Swift features to improve development efficiency.
- **iOS 13+ Optimization**: Tailored for iOS 13 and later versions with new feature compatibility.
- **Error Handling**: Built-in invalid identifier safety checks to enhance app stability.
- **Lightweight Design**: Zero third-party dependencies for easier installation and integration.

### Use Cases
1. **Modular Development in Large Projects**  
   By decoupling navigation logic, development teams can improve code reusability and reduce maintenance costs, particularly suitable for long-term iterative development in large-scale projects.
   
2. **Flexible Dynamic Routing**  
   Supports navigation through identifiers or URL protocols, ideal for multi-scenario in-app routing needs (e.g., deep links, dynamic content loading).
   
3. **Rapid Prototyping**  
   With lightweight framework design and simple API interfaces, developers can quickly implement navigation logic, significantly accelerating MVP or prototype development.

4. **Enhanced User Experience**  
   Leverage error handling and debug logging capabilities to identify and resolve potential issues, delivering a more stable user experience.

---

### Glossary (CN-EN) <!-- by Teng Jingyun -->
| Chinese       | English                  | Description                                   |
|---------------|--------------------------|-----------------------------------------------|
| 框架         | Framework               | A code library encapsulating reusable functionalities |
| 视图控制器   | View Controller         | Component managing UI and interaction logic  |
| 标识符       | Identifier              | String for uniquely identifying resources    |
| 依赖管理工具 | Dependency Manager      | Tool for managing third-party libraries (e.g., CocoaPods) |
| 动态路由     | Dynamic Routing         | Flexible routing logic through configuration |
| 调试日志     | Debug Logging           | Log output functionality for troubleshooting |
| 错误处理     | Error Handling          | Mechanism for capturing and handling exceptions |

---

### XCFramework
```bash
xcodebuild archive -scheme DemoFrameworkKit -destination "iOS" -archivePath "build/iOS"
xcodebuild archive -scheme DemoFrameworkKit -destination "iOS Simulator" -archivePath "build/Simulator"
xcodebuild -create-xcframework \
  -framework "build/iOS.xcarchive/Products/Library/Frameworks/DemoFrameworkKit.framework" \
  -framework "build/Simulator.xcarchive/Products/Library/Frameworks/DemoFrameworkKit.framework" \
  -output "DemoFrameworkKit.xcframework"
ruby
spec.dependency 'Alamofire', '~> 5.4'  # Allow patch updates, prohibit major version upgrades
bash
pod lib lint --allow-warnings  # Check podspec syntax
pod spec lint --verbose        # Validate remote repository and tags

# Create Git tag and push
git tag 1.0.4
git push origin --tags

# Submit to CocoaPods repository
pod trunk push demo-framework.podspec
Private Repository Management
ruby
# Add to top of Podfile when using private sources:
source 'https://github.com/your-company/Specs.git'
source 'https://cdn.cocoapods.org/'
CI/CD Automation
plaintext
[Add your CI/CD pipeline configuration here]
