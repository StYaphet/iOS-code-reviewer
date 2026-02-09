# Objective-C 审查清单

## 重点检查
- 内存管理：ARC 与 Core Foundation 桥接是否使用 `__bridge`/`__bridge_transfer` 正确处理。
- 属性修饰符：`strong`/`weak`/`copy` 选择是否合理，避免循环引用。
- 空值安全：`nullable`/`nonnull` 标注是否完整，Swift 互操作是否安全。
- 线程安全：可变集合、单例、静态变量是否有同步保护。
- 运行时/动态特性：`performSelector`/method swizzling 使用是否受控。

## 常见问题提示
- `copy` 缺失导致 `NSMutableString`/`NSMutableArray` 被外部修改。
- Block 持有 `self` 未使用 `weak`/`strong` dance 导致循环引用。
- Bridge 时未正确转移所有权导致泄漏或过度释放。

## 可执行建议模板
- “为可变字符串/集合属性使用 `copy`，避免外部修改造成状态不一致。”
- “在 block 内使用 `__weak`/`__strong` self 以避免循环引用。”
- “补充 `nullable`/`nonnull` 标注，减少 Swift 调用时的崩溃风险。”
