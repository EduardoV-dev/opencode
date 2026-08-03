# Next.js

Apply this reference only when the repository uses Next.js.

- Keep route files, layouts, handlers, and framework entrypoints thin; delegate feature behavior to
  the owning module.
- Prefer server-rendered modules by default. Add a client boundary only for browser APIs, local
  interaction state, or event handlers that require it.
- Organize each production component as a folder with `index.tsx` and `index.module.css`; keep
  private child components inside that folder, with the same structure in their own subfolders.
- Keep component styling in CSS Modules. Limit global CSS to reset, base, and shared foundation styles.
- Define shared PostCSS responsive mixins for small (`min-width: 30rem`), tablet (`48rem`), laptop
  (`64rem`), and desktop (`80rem`) breakpoints, and reuse them instead of ad hoc media queries.
- Write responsive styles mobile-first: base styles must work from `20rem` (320px), use the shared
  `min-width` mixins for larger layouts, and prevent horizontal content overflow at every viewport.
- When a component needs state, effects, event handling, data handling, or other non-trivial logic,
  move it into a colocated `use-component-name.ts` hook and export `useComponentName`. Keep the
  component focused on declarative rendering; nested components own their corresponding hooks.
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
