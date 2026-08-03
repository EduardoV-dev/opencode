# Global Harness

This directory contains personal defaults for every repository opened with
OpenCode.

- Apply `instructions/general/*.md` to every repository.
- When a repository contains frontend code, inspect it and load the `frontend`
  skill. When it contains backend code, inspect it and load the `backend` skill.
  Full-stack repositories may need both. Each role skill selects the matching
  technology reference after inspecting manifests, configuration, imports, and
  existing source.
- TypeScript and Biome guidance lives in the shared references consumed by both
  role skills; do not load or create technology files under `instructions/`.
- Load the `instruction-curator` skill only when the user explicitly asks to
  remember, persist, add, remove, or update a rule in the instructions.
- Follow repository-local instructions and established conventions when they
  are more specific than these defaults.
- Do not force a role or technology profile onto an unrelated repository.

## Skills: Available

- **ponytail** — Load with `skill("ponytail")` at the start of every session.
- **caveman** — Ultra-compressed communication. Load with `skill("caveman")`.
- **frontend** — Load when repository inspection finds frontend code; selects the matching frontend
  technology references.
- **backend** — Load when repository inspection finds backend code; selects the matching backend
  technology references.
- **instruction-curator** — Load only for explicit persistent instruction updates.

<!-- context7 -->
Use Context7 MCP to fetch current documentation whenever the user asks about a library, framework, SDK, API, CLI tool, or cloud service — even well-known ones like React, Next.js, Prisma, Express, Tailwind, Django, or Spring Boot. This includes API syntax, configuration, version migration, library-specific debugging, setup instructions, and CLI tool usage. Use even when you think you know the answer — your training data may not reflect recent changes. Prefer this over web search for library docs.

Do not use for: refactoring, writing scripts from scratch, debugging business logic, code review, or general programming concepts.

## Steps

1. Always start with `resolve-library-id` using the library name and what to look up in the library's documentation, unless the user provides an exact library ID in `/org/project` format
2. Pick the best match (ID format: `/org/project`) by: exact name match, description relevance, code snippet count, source reputation (High/Medium preferred), and benchmark score (higher is better). If results don't look right, try alternate names or queries (e.g., "next.js" not "nextjs", or rephrase the question). Use version-specific IDs when the user mentions a version
3. `query-docs` with the selected library ID and what to look up in the library's documentation (not single words), scoped to a single concept. If the question spans multiple distinct concepts (e.g. routing and auth and caching), make a separate `query-docs` call per concept with the same library ID, unless the question is about how the concepts interact — combined queries dilute ranking and return shallow results for each topic
4. Answer using the fetched docs
<!-- context7 -->

<!-- CODEGRAPH_START -->
## CodeGraph

In repositories indexed by CodeGraph (a `.codegraph/` directory exists at the repo root), reach for it BEFORE grep/find or reading files when you need to understand or locate code:

- **MCP tool** (when available): `codegraph_explore` answers most code questions in one call — the relevant symbols' verbatim source plus the call paths between them, including dynamic-dispatch hops grep can't follow. Name a file or symbol in the query to read its current line-numbered source. If it's listed but deferred, load it by name via tool search.
- **Shell** (always works): `codegraph explore "<symbol names or question>"` prints the same output.

If there is no `.codegraph/` directory, skip CodeGraph entirely — indexing is the user's decision.
<!-- CODEGRAPH_END -->
