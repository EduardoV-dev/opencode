# TypeScript

Read this reference when the repository uses TypeScript, regardless of role.

- Use strict compiler settings and explicit types at exported boundaries when the repository supports
  them.
- Avoid `any`. Use `unknown` at uncertain boundaries and narrow it with runtime validation.
- Validate untrusted input before treating it as a domain type.
- Avoid type assertions unless a runtime check or documented invariant justifies the assertion.
- Use discriminated unions for mutually exclusive states instead of combinations of optional fields.
- Prefer readonly data and props where mutation is not part of the contract.
- Keep public APIs small and return domain-oriented values rather than implementation details.
- Do not weaken compiler or lint rules merely to silence an error; fix the underlying contract or narrow
  the value correctly.
- Let the repository's configured formatter and module conventions determine syntax and imports.
