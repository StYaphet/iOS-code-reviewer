# Persistence & Data Review Checklist

## Core Data / Realm
- Ensure migrations are defined and tested for schema changes.
- Keep managed object contexts scoped; avoid long-lived background contexts.
- Validate thread confinement rules (Core Data contexts per queue/actor).

## UserDefaults / lightweight storage
- Only store small, non-sensitive values.
- Avoid frequent writes on the main thread.
- Provide defaults and migration when keys change.

## Caching strategy
- Define clear cache invalidation and eviction policies.
- Ensure cached data respects TTLs and data freshness requirements.
- Avoid unbounded disk usage; enforce size limits.

## Serialization & data integrity
- Validate decoding/encoding errors and handle corrupt data.
- Use versioned models or migrations for persistent formats.
- Ensure file writes are atomic to avoid partial corruption.

## Key notes
- Consider offline-first behavior and conflict resolution.
- Use background queues/actors for IO work.
- Respect privacy requirements for stored data.
