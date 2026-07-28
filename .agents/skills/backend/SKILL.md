---
name: backend
description: Apply backend role guidance for server, API, and service work using Express.js or NestJS. Use when repository inspection shows backend code.
---

# Backend Role

Use this skill for backend work. Do not apply it to a frontend-only repository.

1. Inspect the package manifest, workspace configuration, framework config files, scripts, entrypoints,
   routes, controllers, and existing source before choosing a technology reference.
2. Read `references/general.md` from this skill directory.
3. Read every matching technology reference:
   - `references/express.md` for Express.js projects.
   - `references/nestjs.md` for NestJS projects.
4. Read `../shared/typescript.md` when the repository uses TypeScript.
5. Read `../shared/biome.md` when the repository uses Biome as its formatter or linter.
6. If multiple backend technologies are present, keep each boundary explicit and read all relevant
   references. If no supported technology is detected, use only the backend general guidance.

Repository-local instructions and established conventions override these defaults when they are more
specific and do not conflict with correctness, security, or data integrity.
