# UI & Accessibility Review Checklist

## SwiftUI / UIKit layout
- Verify layout works across size classes, orientations, and Dynamic Type settings.
- Use constraints or stacks that avoid ambiguity; confirm content hugging/compression priorities.
- Avoid hard-coded sizes when intrinsic content or constraints should adapt.

## Dynamic Type & scaling
- Use text styles (`.title`, `.body`, etc.) and `UIFontMetrics` for scaling.
- Ensure layouts handle larger accessibility sizes without clipping.
- Test for truncation and multi-line behavior.

## Accessibility
- Provide accessibility labels, hints, and traits for interactive elements.
- Ensure actionable elements are large enough and have sufficient contrast.
- Validate focus order and grouping for VoiceOver.

## UI state & updates
- Ensure UI updates occur on main thread / main actor.
- Use diffable data sources or `@State` / `@Observable` bindings properly.
- Avoid unnecessary re-renders by scoping state narrowly.

## Key notes
- Respect safe area insets and keyboard avoidance.
- Support Right-to-Left layout where applicable.
- Verify animations are performant and can be reduced if user has Reduce Motion enabled.
