# Networking & Security Review Checklist

## URLSession usage
- Use appropriate `URLSessionConfiguration` (ephemeral for sensitive data).
- Validate request timeout, retry, and caching behavior.
- Ensure background sessions are used for long-running transfers if needed.

## TLS & certificate handling
- Avoid disabling ATS; document any exceptions.
- If certificate pinning is used, implement robust rotation and fallback.
- Verify trust evaluation and error handling for TLS failures.

## Sensitive data handling
- Never log PII, credentials, or tokens.
- Store secrets in Keychain, not `UserDefaults` or plaintext files.
- Redact sensitive values in error messages or analytics.

## API responses & parsing
- Validate status codes and content types before parsing.
- Guard against large payloads and unbounded memory usage.
- Ensure decoding failures are surfaced and monitored.

## Key notes
- Consider network reachability and offline scenarios.
- Use `URLCache` or custom caching only when data is safe to cache.
- Sanitize user input in requests to prevent injection or malformed data.
