# Next.js

Apply this reference only when the repository uses Next.js.

- Keep route files, layouts, handlers, and framework entrypoints thin; delegate feature behavior to
  the owning module.
- Prefer server-rendered modules by default. Add a client boundary only for browser APIs, local
  interaction state, or event handlers that require it.
- Keep server-only modules, credentials, and privileged operations out of client bundles.
- Treat route parameters, headers, cookies, form data, request bodies, webhooks, and third-party
  responses as untrusted input. Validate them on the server.
- Enforce authentication, authorization, ownership, and tenant checks in server handlers and actions;
  a hidden client control is not protection.
- Do not mutate state through `GET`. Protect cookie-authenticated state changes against CSRF where
  cross-site requests are possible.
- Prevent request waterfalls and unnecessary client-side fetching. Use the repository's data-loading
  conventions and existing framework patterns.
- Keep loading, error, and not-found behavior explicit for user-visible failure and recovery paths.
- Never expose server secrets through public environment variables, serialized props, logs, or errors.
- Preserve the repository's chosen router, rendering, caching, and server-action conventions instead of
  mixing incompatible patterns.
