# Frontend General

- Inspect the existing UI structure, design system, routing, state, data-fetching, and styling
  conventions before introducing a new pattern.
- Keep feature components, private interaction logic, styles, tests, and assets beside their narrowest
  owner when that matches the repository convention.
- Keep one production UI component per source file unless tightly coupled primitive components are
  intentionally consumed as one family.
- Keep component inputs immutable where the language supports it.
- Components should describe rendered UI. Move non-trivial requests, navigation, form handling, side
  effects, and interaction state into the owning boundary or hook when the framework supports it.
- Do not create a custom hook or wrapper merely to rename one trivial operation.
- Keep state close to its consumers and promote it only when multiple consumers require it.
- Derive view values from existing state instead of synchronizing duplicate state.
- Use effects or browser lifecycle hooks to synchronize with external systems, not to calculate values
  that can be derived during rendering.
- Do not add memoization, caching, virtualization, or background work without a measured bottleneck.
- Prefer semantic HTML, labels, keyboard access, visible focus, meaningful alternatives, and useful
  validation errors. Do not communicate meaning through color alone.
- Treat URL parameters, form data, storage, network responses, and browser APIs as untrusted input.
- Keep credentials and server-only operations out of browser bundles and public environment variables.
- Preserve responsive behavior and test the real interaction path on keyboard and narrow screens.
