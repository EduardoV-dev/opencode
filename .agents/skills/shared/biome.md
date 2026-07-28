# Biome

Read this reference when the repository is configured to use Biome, regardless of role.

- Treat the repository's Biome configuration as authoritative for formatting, linting, imports, and
  supported file types.
- Use the existing package scripts or documented commands to run Biome; do not assume a package
  manager or add a new command wrapper.
- Keep formatting and lint fixes focused on the changed scope unless the task explicitly requests a
  repository-wide cleanup.
- Do not disable a rule or add an ignore merely to hide a real defect. If an exception is necessary,
  keep it narrow and explain the constraint.
- Remove unused imports and symbols rather than suppressing the diagnostic.
