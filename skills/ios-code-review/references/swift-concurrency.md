# Swift Concurrency Review Checklist

## Actor usage
- Are shared mutable states isolated behind `actor` or other synchronization?
- Avoid crossing actor boundaries with non-Sendable types unless explicitly justified.
- Check `@MainActor` usage for UI-bound state and ensure heavy work is off the main actor.

## async/await correctness
- Validate async functions are `async throws` where appropriate and errors are surfaced to callers.
- Ensure `await` is used for async calls; avoid blocking waits (semaphores, `DispatchGroup.wait`).
- Confirm `async` work is structured (avoid detached tasks unless necessary).

## Task / TaskGroup
- Use `Task {}` within proper scope; avoid fire-and-forget for critical work.
- Verify `TaskGroup` handles cancellation and error propagation.
- Ensure child tasks are awaited or cancelled to prevent leaks or unexpected background work.

## Thread safety & data races
- Identify shared mutable state accessed from multiple tasks.
- Check for `@Sendable` closures and `Sendable` conformance on types crossing concurrency boundaries.
- Review usage of `nonisolated` and `@unchecked Sendable` for justified safety.

## Cancellation
- Ensure long-running operations check `Task.isCancelled` or respond to cancellation.
- Use `withTaskCancellationHandler` when cleanup is required.
- Propagate cancellation to nested tasks and network requests.

## Key notes
- Prefer structured concurrency; avoid mixing with GCD unless needed for legacy APIs.
- Avoid calling blocking APIs from async contexts.
- Document concurrency assumptions in APIs that expose shared state.
