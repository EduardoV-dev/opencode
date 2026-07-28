# Express.js

Apply this reference only when the repository uses Express.js.

- Keep the app setup, middleware registration, route declarations, and server startup separate when
  that matches the repository structure.
- Keep route callbacks thin. Parse and validate input at the route boundary, then delegate domain work
  to the owning module.
- Preserve middleware order intentionally: request context and security middleware before routes, error
  handling after routes, and body parsing only where it is needed.
- Forward asynchronous failures through the repository's established Express error boundary. Do not
  leave rejected promises or thrown errors to become hanging requests or process-level surprises.
- Do not trust `req.params`, `req.query`, `req.headers`, `req.cookies`, `req.body`, or `req.files` until
  they have been validated and narrowed.
- Use explicit status codes and response shapes. Do not leak internal errors, stack traces, or database
  details through responses.
- Keep route and middleware modules focused; do not turn a shared middleware file into a service layer.
- Configure proxy, CORS, cookies, body limits, and production error behavior from the repository's
  actual deployment requirements rather than permissive defaults.
