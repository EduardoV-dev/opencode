# General Security

Security rules are not optional simplifications. Treat every external value and effect as a trust
boundary.

## Validation And Errors

- Validate type, length, range, format, and allowed values at every external boundary.
- Fail fast on invalid input and impossible internal states.
- Never silently swallow errors. Preserve the original cause when wrapping an error.
- Return generic errors to untrusted callers. Do not expose stack traces, internal paths, query
  details, tokens, credentials, or information that enables enumeration.
- Set request, upload, query, recursion, and execution limits. Handle timeouts and partial failures
  explicitly.

## Injection And Unsafe Input

- Use parameterized database APIs or typed query parameters. Never concatenate untrusted values into
  query text.
- Map dynamic identifiers such as table names, fields, sort directions, and operators to a fixed
  server-side allowlist.
- Avoid shell commands. When required, use argument-array APIs without a shell and never concatenate
  untrusted input into a command.
- Treat templates, logs, email headers, HTTP headers, file paths, serialized data, and expressions as
  injection boundaries. Reject control characters and constrain values to an expected format.
- Validate user-controlled URLs before redirects or assignment to resource locations. Allow only the
  required protocols and reject `javascript:`, `data:`, protocol-relative, and malformed URLs unless
  a reviewed use case explicitly requires them.
- Do not construct executable code, markup, styles, or serialized data by concatenating untrusted
  strings.

## Browser And Application Security

- Render untrusted text through the platform's escaping mechanisms. If raw markup is required,
  sanitize it at the final render boundary with a maintained allowlist and test unsafe payloads.
- Protect state-changing cookie-authenticated requests against CSRF where cross-site requests are
  possible. Do not mutate state through `GET`.
- Set authentication cookies with `HttpOnly`, `Secure`, and an appropriate `SameSite` value.
- Never store session secrets or service credentials in browser-readable storage or client bundles.
- Restrict server-side outbound requests to required hosts and protocols. Block loopback, private,
  link-local, metadata, and unsafe redirect destinations to prevent SSRF.

## Access And Data Protection

- Enforce authentication, authorization, ownership, and tenant membership at the server boundary for
  every read and mutation. Hiding a UI control is not authorization.
- Derive identity, roles, ownership, prices, statuses, and permissions from trusted server state.
- Deny access by default and check both object-level and function-level permissions.
- Grant the least database and application privileges needed.
- Review privileged functions for safe execution context, qualified objects, and restricted access.
- Use platform-supported cryptography. Do not invent encryption, hashing, token, or random-number
  algorithms.
- Collect, retain, and log only the sensitive data the feature needs. Redact secrets, credentials,
  session data, and personal information from logs and analytics.

## Operational Baseline

- Keep production configuration restrictive: disable debug output, limit CORS to known origins, set
  security headers, and remove default accounts, sample endpoints, and unused services.
- Pin dependencies through the lockfile, review dependency changes, and run available vulnerability
  checks.
- Verify authentication callbacks, redirect destinations, session expiry, account recovery, webhook
  signatures, and the provenance of generated or serialized artifacts.
- Rate-limit login, invite, lookup, and other abuse-prone operations.
- Log security-relevant events with request and actor identifiers, but never secrets.
- Threat-model new trust boundaries and sensitive workflows. Add focused tests for authorization,
  injection, unsafe redirects, forged requests, and cross-tenant access where applicable.
