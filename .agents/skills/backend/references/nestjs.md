# NestJS

Apply this reference only when the repository uses NestJS.

- Keep modules aligned with domain ownership and use imports/exports to make dependency direction
  explicit.
- Keep controllers thin. Validate and transform transport input at the boundary, then delegate domain
  behavior to focused providers or use-case modules.
- Use pipes, guards, interceptors, filters, and decorators for cross-cutting behavior only when they
  create a real boundary and match the repository's existing conventions.
- Do not make a single service a catch-all for unrelated domains, persistence, transport, and external
  integrations.
- Enforce authentication, authorization, ownership, and tenant checks in guards or server-side domain
  boundaries; decorators and hidden client controls are not protection by themselves.
- Keep DTOs, entities, persistence models, and domain types distinct when their contracts differ. Do
  not expose ORM or internal objects as API contracts by accident.
- Configure validation, serialization, exception filters, and global pipes deliberately; do not weaken
  them to silence an invalid input or type error.
- Keep providers that use credentials, databases, or privileged APIs out of browser-facing code and
  serialize only the fields the caller is allowed to receive.
