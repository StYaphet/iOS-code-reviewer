# 并发审查清单（Swift Concurrency / GCD）

## 重点检查
- 在主线程更新 UI（SwiftUI/ UIKit）是否明确切回 `MainActor`。
- 任务生命周期与取消：是否在 `deinit`/`viewWillDisappear`/`task` 取消。
- 共享状态隔离：是否使用 `actor`、`@MainActor` 或其它同步机制。
- 结构化并发：是否避免悬挂任务、`Task.detached` 滥用。
- 错误处理：`async`/`await` 调用是否有清晰的错误路径。

## 常见问题提示
- `@MainActor` 缺失导致竞态或 UI 更新崩溃。
- 忘记取消任务导致内存泄漏或重复请求。
- 使用 GCD 同时访问可变集合导致数据竞争。

## 可执行建议模板
- “将 UI 更新包裹在 `@MainActor` 或 `MainActor.run {}` 中，以保证线程安全。”
- “在 `Task` 创建处保存句柄，在生命周期结束时调用 `cancel()`。”
