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

### System Requirements <!---by chenchengxin --->
1.Operating System
  iOS Devices: Requires iOS devices supporting the arm64 architecture.
  iOS Simulator: Requires macOS with support for arm64 (Apple Silicon) or x86_64 (Intel) architecture simulators.
2.Development Environment
  Xcode: Requires Xcode version 12.0 or higher (to support XCFramework format).
  Compiler Toolchain: Must be compatible with Swift and Objective-C mixed development (e.g., when integrating via Swift Package Manager or CocoaPods).
3.Architecture Support
  Physical Devices: Supports arm64 architecture only (e.g., iPhone, iPad).
  Simulator: Supports arm64 (Apple Silicon Mac) and x86_64 (Intel Mac) architectures.
4.Dependencies
  No external dependencies (the framework encapsulates all necessary components).
  Requires importing DemoFrameworkKit.framework or integrating via XCFramework in your project.
5.Integration Methods
  Supports manual import of .framework files or XCFramework integration.
  Compatible with dependency managers such as Swift Package Manager, CocoaPods, or Carthage.
Compatibility Notes
The framework supports both physical devices and simulators through the XCFramework format, eliminating the need for separate configurations.
For projects requiring compatibility with older iOS versions (e.g., iOS 10 or earlier), verify the framework's minimum supported version (not explicitly stated in the documentation; check Deployment Target).
When integrating via Swift Package Manager, ensure Xcode 11 or higher is used.

### Installation Guide <!-- by litao -->
1. Integration via CocoaPods (Recommended)
Ensure CocoaPods is installed, then add the following to your project's Podfile:
ruby
target 'YourAppTarget' do
  pod 'DemoFrameworkKit', '~> 1.0.4'
end
Execute the installation command:
bash
pod install
2. Manual Integration
Download the Framework
Download DemoFrameworkKit.xcframework from the project repository.
Add to Xcode Project
Open your project in Xcode.
Select the project target ➔ General ➔ Frameworks, Libraries, and Embedded Content.
Click + ➔ Add Other ➔ Add Files.
Navigate to and select DemoFrameworkKit.xcframework.
Set the embedding option to Embed & Sign.
Configure Build Settings
Ensure Build Phases ➔ Link Binary With Libraries includes DemoFrameworkKit.framework.
For Swift projects, add an Objective-C bridging header in Build Settings ➔ Objective-C Bridging Header if necessary.
Configuration Requirements
Xcode Version: 12.0 or higher
iOS Deployment Target: 11.0+
Swift Version: 5.0+
---
### Contributing <!-- by long dalei -->
How to Contribute
Submit an Issue
If you find any bugs or have feature suggestions, please first check if there is an existing issue:
If not, please create a new issue
Clearly describe the problem or suggestion
For bugs, provide steps to reproduce and environment details

Code Contribution Process

Step 1: Fork the Repository

Click the "Fork" button in the top-right corner of the GitHub page

Clone your fork locally:
git clone https://github.com/your-username/Demo-Framework.git  

Step 2: Create a Branch
git checkout -b feature/your-feature-name  # or fix/issue-description  

Step 3: Development and Testing
Make your changes
Ensure the code follows the existing style
Add/update relevant tests
Run tests to ensure they pass

Step 4: Commit Changes
git commit -m "Describe your changes"  

Step 5: Push Changes
git push origin your-branch-name  

Step 6: Create a Pull Request
Visit your fork on GitHub
Select the branch you created
Click "New pull request"
Provide a detailed description of your changes and the reasons for them

Coding Standards
Follow the existing code style
Use Swift 5.7+ syntax
Maintain API compatibility
Add documentation comments for public APIs
Include corresponding test cases for each feature/fix

Other Ways to Contribute
Improve documentation
Translate documentation
Answer questions from other users
Share use cases

---
Here's the English translation of your project structure section:

## Project Structure <!-- by Zhou Longchun -->

Demo-Framework/
├── .gitignore # Git ignore rules configuration
├── Demo-Framework-1.0.4.iml # IntelliJ module configuration file
├── demo-framework.podspec # CocoaPods configuration file
├── Info.plist # Xcode project configuration file
├── misc.xml # IDE configuration file
├── modules.xml # Project modules configuration file
├── workspace.xml # IDE workspace configuration file
└── DemoFrameworkKit/ # Framework core code
├── DemoFrameworkKit.h # Framework main header file
├── DemoFrameworkKit-Swift.h # Swift-ObjC bridging header
└── Info.plist # Framework configuration file


### Key File Descriptions

1. **demo-framework.podspec** - CocoaPods dependency management configuration file that defines the framework name (version 1.0.3), platform requirements (iOS 13.0+), and source location (GitHub repository).

2. **DemoFrameworkKit.xcframework** - Precompiled binary framework (not shown in directory, referenced by podspec), supporting:
   - iOS devices (arm64)
   - iOS simulator (arm64/x86_64)

3. **Info.plist** - Contains XCFramework configuration information, specifying supported architectures and platforms.

4. **Swift Header File** - `DemoFrameworkKit-Swift.h` provides Swift-Objective-C interoperability support, compiled with Swift 5.7.1.

The translation maintains all technical terminology while ensuring readability for English-speaking developers. I kept the original file structure format and Markdown styling consistent with the Chinese version.


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

### 知识扩展  XCFramework <!-- by 农松辰 -->
xcodebuild archive -scheme DemoFrameworkKit -destination "iOS" -archivePath "build/iOS"
xcodebuild archive -scheme DemoFrameworkKit -destination "iOS Simulator" -archivePath "build/Simulator"
xcodebuild -create-xcframework \
  -framework "build/iOS.xcarchive/Products/Library/Frameworks/DemoFrameworkKit.framework" \
  -framework "build/Simulator.xcarchive/Products/Library/Frameworks/DemoFrameworkKit.framework" \
  -output "DemoFrameworkKit.xcframework"

spec.dependency 'Alamofire', '~> 5.4'  # 允许补丁更新，禁止主版本升级

pod lib lint --allow-warnings  # 检查 podspec 语法
pod spec lint --verbose        # 验证远程仓库和标签

###打 Git 标签并推送
git tag 1.0.4
git push origin --tags

###提交到 CocoaPods 仓库
pod trunk push demo-framework.podspec

###私有仓库管理
###若使用私有源，需在 Podfile 顶部声明：
source 'https://github.com/your-company/Specs.git'
source 'https://cdn.cocoapods.org/'

###自动化与持续集成



