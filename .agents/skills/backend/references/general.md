# Backend General

- Inspect the existing module, transport, persistence, validation, authentication, error, and logging
  conventions before introducing a new layer.
- Keep entrypoints, route handlers, controllers, jobs, and adapters thin. Delegate domain behavior to
  modules that can be tested without the transport or process boundary.
- Keep domain transformations independent of HTTP, storage, queues, timers, and other platform
  effects where practical.
- Isolate network, storage, time, process, and third-party effects at explicit boundaries.
- Validate type, length, range, format, and allowed values at every external boundary. Treat request
  data, headers, cookies, files, webhooks, queues, and third-party responses as untrusted.
- Enforce authentication, authorization, ownership, and tenant membership on the server for every read
  and mutation. A client-side restriction is not authorization.
- Never mutate state through `GET`; protect cookie-authenticated mutations against CSRF where relevant.
- Return generic errors to untrusted callers and log useful context without secrets, tokens, credentials,
  personal data, stack traces, or internal paths.
- Make timeouts, request limits, retry behavior, idempotency, and partial failures explicit for external
  operations.
- Keep configuration and secrets out of source control and client-facing responses. Fail fast on
  missing required production configuration.
- Use parameterized database APIs, fixed allowlists for dynamic identifiers, and argument-array process
  APIs. Do not concatenate untrusted input into queries, shell commands, templates, or redirects.
- Keep public APIs small and return domain-oriented values rather than implementation details.
- Add focused tests for validation, authorization, unsafe input, failure paths, and important edge cases
  at the boundary where behavior is established.
