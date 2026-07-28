# General Architecture

## Ownership And Boundaries

- Create each element at the narrowest level that owns it.
- Keep feature-specific implementation inside its feature; keep cross-feature code in shared scope.
- Keep entrypoints, adapters, and route handlers thin. Delegate domain behavior to code that can be
  tested without the transport or presentation layer.
- Keep domain transformations independent of UI, routing, storage, network, timers, and other
  platform effects.
- Isolate external effects at explicit boundaries so they can be replaced in tests.
- Keep privileged or server-only modules out of untrusted or client-facing bundles.

## Design

- Give each module one cohesive responsibility and keep dependency direction obvious.
- Keep state close to its consumers and promote it only when multiple consumers require it.
- Derive values from existing state instead of synchronizing duplicate state.
- Keep public APIs small and return domain-oriented values rather than implementation details.
- Add a wrapper only when it creates a concrete boundary or has multiple real consumers.
- Do not introduce a factory, interface, service layer, or configuration object for one implementation
  or one fixed value.
- Prefer a direct call over an abstraction that only renames or forwards it.

## Change Safety

- Preserve invariants at the boundary where they are established.
- Validate inputs before passing them across trust or ownership boundaries.
- Make failure and partial-failure behavior explicit; do not leave corrupted or ambiguous state.
- Keep migrations, compatibility behavior, and cleanup proportional to an actual need.
