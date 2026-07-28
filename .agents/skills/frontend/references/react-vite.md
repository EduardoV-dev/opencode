# React And Vite

Apply this reference only when the repository uses React with Vite.

- Follow the repository's established React structure before introducing a new layout.
- Keep props immutable and use the framework's state update APIs rather than mutating rendered data.
- Use hooks for React state and lifecycle behavior; keep non-trivial form handling, requests,
  navigation, and interaction state in a domain-oriented hook or boundary beside the component.
- Do not create a hook merely to wrap one trivial derived value or toggle.
- Derive values during render instead of synchronizing duplicate state with effects.
- Use effects to synchronize with external systems, not to calculate values that can be derived during
  render.
- Do not add memoization by default. Measure first and use the repository's supported concurrency
  primitives only when they improve a real interaction.
- Keep Vite configuration focused on the repository's actual plugins and build needs.
- Treat `VITE_` environment variables as public browser configuration. Never put secrets in them,
  client source, or generated public assets.
- Use the repository's package scripts for development, checking, testing, and production builds.
