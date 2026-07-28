---
name: instruction-curator
description: Manage persistent OpenCode instructions when the user explicitly asks to remember, persist, add, remove, or update a rule for a role, technology, stack, repository, or development cycle.
---

# Instruction Curator

Use this skill only after an explicit request to save, remember, persist, enforce, add, remove, or
update a rule in the instructions. Ordinary corrections and preferences apply to the current session
only; never infer that they should be persisted.

## Scope Selection

Inspect existing instructions before choosing a target. Use the narrowest scope that matches the rule:

| Rule | Target |
| --- | --- |
| Universal engineering behavior | `~/.config/opencode/instructions/general/` |
| Testing, security, completion, architecture, or code style | The matching general instruction file |
| Frontend-wide behavior | `~/.config/opencode/.agents/skills/frontend/references/general.md` |
| Backend-wide behavior | `~/.config/opencode/.agents/skills/backend/references/general.md` |
| React/Vite, Next.js, or Astro behavior | Matching frontend `references/<technology>.md` |
| Express.js or NestJS behavior | Matching backend `references/<technology>.md` |
| TypeScript or Biome behavior | `~/.config/opencode/.agents/skills/shared/<technology>.md` |
| One repository only | That repository's `AGENTS.md` or established local instruction file |

If a requested technology does not have an entry, create the role reference and update the role
skill's detection list so it can be selected from repository evidence. Do not create a duplicate when
an existing entry can own the rule.

## Workflow

1. Extract the rule, affected role or technology, lifecycle stage, and whether it is global or
   repository-local.
2. Search the selected scope and nearby scopes for duplicates, contradictions, and a better existing
   owner.
3. Normalize the rule into one concise, actionable instruction. Preserve the user's intent and avoid
   speculative examples or abstractions.
4. Present the proposed target path, the reason for that scope, and the minimal diff.
5. Ask for confirmation before changing persistent files. An explicit request to update is permission
   to prepare the change, not permission to silently broaden its scope.
6. After confirmation, edit only the selected file(s) with `apply_patch`, then inspect the diff and
   validate Markdown/frontmatter and any affected configuration.
7. Apply the confirmed rule for the current task and state that OpenCode must be restarted before a
   global skill or instruction change is loaded by a new session.

Prefer updating an existing section over adding a new file. Remove or rewrite contradictory guidance
instead of leaving two rules for the same behavior. Do not persist secrets, personal data, temporary
workarounds, or repository-specific facts in global instructions.
