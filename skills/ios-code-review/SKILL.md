---
name: ios-code-review
description: iOS/Swift/Objective-C 代码审查技能，覆盖 Swift、Objective-C、SwiftUI、UIKit、并发、性能、内存、安全、测试与架构；当需要审查 iOS 代码变更、PR、Swift/Objective-C 文件、应用架构或生成可执行 Review 反馈时使用。
---

## Goal
- 生成可执行、可验证的代码审查意见，突出高风险问题与改进收益。

## Required Inputs
- 变更范围与目标平台（iOS 版本、Swift 版本、设备/架构）。
- 关键文件与功能路径（入口、网络、存储、UI、并发）。
- 预期行为与性能/安全约束。

## Workflow
1. 确认上下文：梳理需求、关键路径、边界条件与目标平台。
2. 快速扫描：定位高风险点（崩溃、数据丢失、竞态、隐私泄漏）。
3. 分类审查：按正确性/并发/性能/内存/API 设计/可维护性/测试/架构/安全逐类检查。
4. 验证建议：为每条意见给出可验证的依据或复现路径。
5. 归类输出：按严重度与优先级输出（Blocker/Major/Minor）。

## Review Checklist (Condensed)
- 正确性：空值、越界、状态一致性、错误处理完整性。
- 并发：隔离/线程安全、Actor/主线程更新、任务取消与生命周期。
- 性能与内存：主线程耗时、布局/渲染抖动、缓存策略、对象持有。
- API 设计：命名、可测试性、依赖注入、扩展点。
- 安全与隐私：敏感信息、网络传输、权限最小化。
- 测试：关键路径覆盖、回归风险、可测试性。

## Output Template
- **问题**：
- **影响**：
- **建议**：
- **验证方式/示例**：
- **严重度**：Blocker / Major / Minor

## Reference Loading
- 并发相关：加载 `references/concurrency.md`。
- SwiftUI 视图/状态/生命周期：加载 `references/swiftui.md`。
- UIKit 视图/生命周期/布局：加载 `references/uikit.md`。
- Objective-C 文件与桥接/互操作相关：加载 `references/objective-c.md`。
- 网络/缓存/安全通信：加载 `references/networking.md`。
- 持久化（Core Data/文件/Keychain/Realm）：加载 `references/persistence.md`。
- 测试策略与可测试性：加载 `references/testing.md`。
