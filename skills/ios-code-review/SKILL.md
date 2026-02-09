---
name: ios-code-review
description: Perform iOS/Swift 代码审查; cover SwiftUI, UIKit, 并发, 性能, 安全, 测试, 架构; trigger on iOS/Swift 代码审查、SwiftUI、UIKit、并发、性能、安全、测试、架构 requests.
---

## Workflow
- 接收输入：读取需求、变更范围、关键文件与目标平台。
- 分类问题：按正确性/崩溃、并发、性能、内存、API 设计、可维护性、测试、架构与安全归类。
- 执行检查：逐类核对，定位高风险与可重复出现的问题。
- 生成输出：输出可执行建议、优先级与可验证的修复点。

## Output Template
- 问题描述：
- 影响：
- 建议：
- 可选代码示例：

## Reference Loading
- 遇到并发相关代码时，加载并发参考。
- 遇到 SwiftUI 视图、状态或生命周期时，加载 SwiftUI 参考。
- 遇到网络请求、缓存或安全通信时，加载网络参考。
- 遇到持久化（Core Data、文件、Keychain、Realm 等）时，加载持久化参考。
