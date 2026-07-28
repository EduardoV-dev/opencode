---
name: frontend
description: Apply frontend role guidance for browser UI work and React/Vite, Next.js, or Astro projects. Use when repository inspection shows frontend code.
---

# Frontend Role

Use this skill for frontend work. Do not apply it to a backend-only repository.

1. Inspect the package manifest, workspace configuration, framework config files, scripts, and
   existing source before choosing a technology reference.
2. Read `references/general.md` from this skill directory.
3. Read every matching technology reference:
   - `references/react-vite.md` for React projects using Vite.
   - `references/nextjs.md` for Next.js projects.
   - `references/astro.md` for Astro projects.
4. Read `../shared/typescript.md` when the repository uses TypeScript.
5. Read `../shared/biome.md` when the repository uses Biome as its formatter or linter.
6. If multiple frontend technologies are present, keep each boundary explicit and read all relevant
   references. If no supported technology is detected, use only the frontend general guidance.

Repository-local instructions and established conventions override these defaults when they are more
specific and do not conflict with correctness, security, accessibility, or data integrity.
