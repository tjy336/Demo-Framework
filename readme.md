
---

### 中文 README.md

```markdown
# Demo Framework 

轻量级模块化 iOS 框架，用于解耦视图控制器的导航逻辑。  
简化代码结构，实现应用内动态路由！

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


