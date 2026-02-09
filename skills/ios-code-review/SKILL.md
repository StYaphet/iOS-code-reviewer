# iOS Code Review Skill

## Purpose
Provide reusable review checklists and key guidance for iOS code reviews, with targeted reference documents for common areas.

## When to load references
Load the relevant reference file(s) when the request mentions any of the triggers below or when the code change touches related areas.

### Triggers by keyword or change type
- **Concurrency / async work** (keywords: `actor`, `async`, `await`, `Task`, `TaskGroup`, `@MainActor`, `Sendable`, `thread`, `race`, `cancellation`, `structured concurrency`): load `references/swift-concurrency.md`.
- **Memory / performance** (keywords: `retain cycle`, `ARC`, `leak`, `Instruments`, `allocation`, `performance`, `profiling`, `capture list`): load `references/memory-and-performance.md`.
- **UI / accessibility** (keywords: `SwiftUI`, `UIKit`, `Auto Layout`, `Dynamic Type`, `VoiceOver`, `accessibility`, `layout`, `trait`, `safe area`): load `references/ui-and-accessibility.md`.
- **Networking / security** (keywords: `URLSession`, `certificate`, `pinning`, `TLS`, `token`, `keychain`, `sensitive`, `PII`, `crypto`): load `references/networking-and-security.md`.
- **Persistence / data** (keywords: `CoreData`, `Realm`, `UserDefaults`, `cache`, `SQLite`, `migration`, `serialization`, `disk`, `offline`): load `references/persistence-and-data.md`.

## Using references
- Start with the most relevant reference based on the change set.
- If multiple areas are touched, load multiple references and synthesize a combined checklist.
- Prefer checklist items that are directly applicable to the change.
