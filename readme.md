
---

### 中文 README.md

```markdown
# Demo Framework 

轻量级模块化 iOS 框架，用于解耦视图控制器的导航逻辑。  
简化代码结构，实现应用内动态路由！

---

## 项目介绍 <!-- by 许培彬 -->

### 项目背景
在 iOS 应用开发中，随着功能的不断迭代和代码的日益复杂，视图控制器之间的导航逻辑也变得愈加复杂且难以维护。传统的导航方式往往存在强耦合问题，导致代码难以复用，测试难度增加，并且限制了开发的灵活性。  
为了解决这些痛点，**Demo Framework** 应运而生，旨在通过模块化设计和动态路由机制，为开发者提供一种轻量级、可扩展的导航解决方案。

### 功能概述
- **解耦导航**：通过标识符或 URL 协议实现视图控制器间的导航，无需直接依赖。
- **动态路由**：支持灵活配置的动态跳转逻辑。
- **Swift 5.7+ 支持**：充分利用现代 Swift 特性，提高开发效率。
- **iOS 13+ 适配**：专为 iOS 13 及以上版本优化，兼容新功能。
- **错误处理**：内置无效标识符安全检查，提升应用稳定性。
- **轻量化设计**：无第三方依赖，安装与集成更加便捷。

---

## 目录
1. [功能](#功能)
2. [系统要求](#系统要求)
3. [安装](#安装)
4. [使用教程](#使用教程)
5. [高级配置](#高级配置)
6. [贡献指南](#贡献指南)
7. [许可证](#许可证)

---

## 功能 <!-- by 周隆春 -->
- **解耦导航**: 无需直接依赖即可跳转控制器。
- **动态路由**: 支持标识符或 URL 协议跳转。
- **Swift 5.7+ 支持**: 完全兼容现代 Swift 语法。
- **iOS 13+ 适配**: 专为 iOS 13 及以上版本优化。
- **错误处理**: 内置无效标识符安全检查。
- **轻量化**: 无第三方依赖。

---

## 系统要求<!-- by 周隆春 -->
- iOS 13.0+
- Xcode 14.0+
- Swift 5.7+
- CocoaPods 1.10.0+（如使用 CocoaPods）

---

## 安装 <!-- by 许培彬 -->

### CocoaPods（推荐）
1. 在 `Podfile` 中添加：
   ```ruby
   pod 'demo-framework', '1.0.3'

2.  运行 `pod install`。
    
3.  在 Swift 文件中导入框架：
    
    swift
    import DemoFrameworkKit
    

### 手动安装<!-- by 许培彬 -->

1.  从 [Releases](https://github.com/PritKothadiya/Demo-Framework/releases) 页面下载 `DemoFrameworkKit.xcframework`。
    
2.  将 `.xcframework` 拖拽至 Xcode 项目。
    
3.  在 Target 设置中选择 "Embed & Sign"。
    

----------

## 使用教程 <!-- by 农松辰 -->

### 基础导航

1.  **定义控制器标识符**：  
    在 Storyboard 或代码中设置唯一标识符（如 `"HomeVC"`）。
    
2.  **编程式跳转**：
    
    swift
    DemoNavigator.openViewController(identifier: "HomeVC")
    

### URL 协议支持

使用自定义 URL 跳转（如 `myapp://home`）：

swift
DemoNavigator.openViewController(url: URL(string: "myapp://home")!)

### 错误处理

优雅处理无效标识符：

swift
do {
    try DemoNavigator.safeOpenViewController(identifier: "SettingsVC")
} catch {
    print("导航失败: \(error.localizedDescription)")
}

----------

## 高级配置 <!-- by 农松辰 -->

### 自定义导航栈

覆盖默认导航控制器：

swift
DemoNavigator.configureNavigationController(UINavigationController.self)

### 调试日志

启用日志排查问题：

swift
DemoNavigator.isLoggingEnabled = true



----------

## 许可证 <!-- by 周隆春-->

基于 MIT 许可证开源。
详见 [LICENSE]([https://license/](https://github.com/tjy336/Demo-Framework/blob/main/LICENSE))。
---

### 项目术语表（中英文对照）<!-- by 许培彬 -->

| 中文         | 英文                     | 说明                                   |
|--------------|--------------------------|----------------------------------------|
| 框架         | Framework                | 封装可复用功能的代码库                 |
| 视图控制器   | View Controller          | 管理界面和交互逻辑的组件               |
| 标识符       | Identifier               | 用于唯一标识资源的字符串               |
| 依赖管理工具 | Dependency Manager       | 管理第三方库的工具（如 CocoaPods）     |
| 动态路由     | Dynamic Routing          | 通过配置实现灵活跳转的逻辑             |
| 调试日志     | Debug Logging            | 用于排查问题的日志输出功能             |
| 错误处理     | Error Handling           | 对异常情况的捕获和处理机制             |




### XCFramework
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


