# UIKit 审查清单

## 重点检查
- 生命周期：是否在正确生命周期配置 UI/数据。
- 线程：UI 更新是否在主线程。
- 约束：Auto Layout 是否有冲突或不必要的约束。
- 复用：`UITableView`/`UICollectionView` 是否正确复用、避免重复注册。

## 常见问题提示
- `viewDidLoad` 中执行阻塞操作。
- 复用 cell 未重置状态导致错乱。
- 强引用循环（delegate/closure）导致内存泄漏。

## 可执行建议模板
- “在 `prepareForReuse` 中重置 UI 状态，避免复用导致残留。”
- “将阻塞操作移到后台线程并回到主线程更新 UI。”
