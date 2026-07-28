# General Principles

These rules apply to repository-authored work regardless of language, framework, or platform.

## Priorities

- Correctness, security, accessibility, and data integrity take priority over every other rule.
- Choose the simplest design that clearly solves the current problem.
- Do not add abstractions, configuration, or extension points for hypothetical needs.
- Apply SOLID proportionally. Keep responsibilities and dependency boundaries clear without adding
  interfaces, factories, or layers with only one concrete use.
- Reuse existing code, platform features, the standard library, and installed dependencies before
  creating custom infrastructure.

## Working Method

- Inspect the repository, its documentation, configuration, and existing patterns before editing.
- Trace the relevant flow and callers before changing shared behavior.
- Fix root causes at shared boundaries instead of adding repeated guards at individual call sites.
- Keep changes focused. Do not mix unrelated cleanup or reformatting into a feature or fix.
- Prefer deletion and local changes over new layers, wrappers, or general-purpose utilities.
- Preserve compatible behavior unless the task explicitly requires a breaking change.
- Ask for clarification only when the ambiguity changes the implementation materially; otherwise
  choose the smallest reasonable behavior and state the assumption.

## Instruction Scope

- Treat technology-specific instruction files as conditional defaults, not universal requirements.
- Follow the repository's explicit requirements when they do not violate the priorities above.
- When a repository has no established convention, use these defaults as the starting point.
