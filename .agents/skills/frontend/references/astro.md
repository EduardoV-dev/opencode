# Astro

Apply this reference only when the repository uses Astro.

- Treat `src/pages` as the routing boundary. Keep pages and layouts thin and delegate feature logic
  to the owning module.
- Prefer Astro's server-rendered or static HTML and add client-side islands only for real interactive
  behavior.
- Keep browser scripts small and scoped to the island or feature that owns the interaction. Do not
  move server work into the browser to avoid understanding the data boundary.
- Keep content, data loading, and privileged operations on the server when possible. Validate route
  parameters, form data, endpoint input, and external responses before use.
- Use the repository's existing component integration and client directive conventions; do not add a
  UI framework for a component that Astro or HTML already handles.
- Keep processed assets under `src/` and use `public/` only for assets that must be copied unchanged.
  Follow the repository's existing directories rather than forcing the default layout.
- Never expose credentials through `PUBLIC_` environment variables, client scripts, rendered props, or
  logs.
- Make loading, error, and not-found behavior explicit for user-visible failure paths.
- Use the repository's configured Astro check and build scripts after changes to pages, integrations,
  adapters, or configuration.
