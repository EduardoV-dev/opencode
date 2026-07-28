# Completion Checklist

Before considering work complete:

- Confirm the requested behavior and any assumptions.
- Inspect the final diff for unrelated changes, stale comments, unused code, and accidental secrets.
- Keep authored source files within the repository's applicable size limit.
- Confirm new files live at the narrowest ownership level and boundaries remain clear.
- Validate untrusted input, authorization, error handling, and sensitive-data behavior for changed
  paths.
- Add or update focused tests for observable behavior and regressions where practical.
- Run the repository's documented formatter, linter, type checker, tests, and build checks that apply
  to the change. Discover commands from project documentation, manifests, and scripts instead of
  assuming a package manager or framework.
- Report what was verified and what could not be run. Do not claim checks passed without running them.
