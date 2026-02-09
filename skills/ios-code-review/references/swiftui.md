# SwiftUI 审查清单

## 重点检查
- 状态来源是否单一：`@State`/`@StateObject`/`@ObservedObject`/`@EnvironmentObject` 使用是否正确。
- 视图刷新：是否避免在 `body` 中执行昂贵计算或副作用。
- 生命周期：`task`/`onAppear`/`onDisappear` 中是否避免重复请求。
- 列表/网格性能：是否使用稳定 `id`，避免过度嵌套。

## 常见问题提示
- `@StateObject` 被重复创建导致状态丢失。
- `onAppear` 触发多次网络请求。
- `body` 中进行同步 IO 或复杂计算造成卡顿。

## 可执行建议模板
- “将耗时计算移出 `body`，改为 `@State` 缓存或在 `task` 中异步计算。”
- “为列表项提供稳定 `id`，避免重建导致闪烁。”
