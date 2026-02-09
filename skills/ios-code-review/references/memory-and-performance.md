# Memory & Performance Review Checklist

## ARC & retain cycles
- Inspect closures for strong captures; use `[weak self]` or `[unowned self]` where appropriate.
- Check delegates are `weak` when ownership is not required.
- Verify `Timer`, `CADisplayLink`, and `NotificationCenter` observers are invalidated or removed.

## Leaks & lifecycle
- Ensure deinit cleanup for observers, KVO, Combine subscriptions, and async tasks.
- Confirm long-lived singletons do not accumulate strong references.
- Look for reference cycles in `UIView`/`CALayer` hierarchies or `SwiftUI` object graphs.

## Performance hot spots
- Avoid excessive main-thread work; move heavy computations off the main actor.
- Check list rendering for diffing efficiency, stable `id`s, and reuse.
- Prefer lazy loading and pagination for large datasets.

## Instruments guidance
- Use Leaks and Allocations to confirm fixes and detect regressions.
- Use Time Profiler to identify slow code paths.
- Use Energy Log when background work or network usage is heavy.

## Key notes
- Validate caching strategy aligns with memory constraints (size limits, eviction).
- Be mindful of image decoding and resizing on the main thread.
- Avoid unnecessary object churn in tight loops.
