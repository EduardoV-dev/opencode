# General Code Style

## Files And Ownership

- Authored source files must not exceed 400 physical lines unless the repository explicitly sets a
  different limit. Generated files, dependency code, lockfiles, and build output are exempt.
- Split files by responsibility before reaching the limit; do not compress formatting or combine
  unrelated statements to evade it.
- Keep code, tests, styles, constants, schemas, types, and utilities beside their narrowest owner.
- Promote code to shared scope only after a real additional consumer exists.

## Functions And Naming

- Give each function one clear responsibility and prefer early returns over deep nesting.
- Keep transformations pure where practical and make side effects explicit.
- Use descriptive domain names for files, functions, classes, methods, variables, and types.
- Prefix booleans with `is`, `has`, `can`, or `should` where the language convention supports it.
- Prefix callbacks with `on` and internal event handlers with `handle` where that convention applies.
- Avoid vague names such as `data`, `item`, `thing`, `helper`, or `manager` when a precise name exists.

## Values And Comments

- Extract unexplained behavioral numbers, strings, routes, keys, statuses, limits, and repeated
  messages into descriptive constants.
- Keep obvious structural values and one-off presentation copy local when extraction would reduce
  clarity.
- Use comments to explain intent, constraints, invariants, or non-obvious trade-offs.
- Remove stale comments when behavior changes. Do not narrate readable code.

## Formatting

- Follow the repository's configured formatter, linter, import ordering, and line-width rules.
- Keep imports focused and remove unused symbols.
- Match existing naming, quoting, indentation, and file naming conventions unless there is a clear
  reason to improve them consistently.
