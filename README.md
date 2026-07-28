# opencode config

Personal [opencode](https://opencode.ai) config + agent skills.

## Setup

```bash
git clone git@github.com:EduardoV-dev/opencode.git ~/.config/opencode
```

## Structure

- `opencode.json` — Provider, models, agent modes, MCP config
- `AGENTS.md` — Always-active harness scope, skills, and documentation rules
- `instructions/general/` — Technology-agnostic engineering defaults
- `.agents/skills/frontend/` — Frontend role and React/Vite, Next.js, and Astro references
- `.agents/skills/backend/` — Backend role and Express.js and NestJS references
- `.agents/skills/shared/` — Cross-role TypeScript and Biome references
- `.agents/skills/instruction-curator/` — Explicit, confirmation-gated instruction updates
- `.agents/skills/` — Other custom skills (caveman, cavecrew, etc.)
- `skills-lock.json` — Skill dependency lockfile

## Usage

Run `opencode` from any project. Global `AGENTS.md` and `instructions/general/*.md` are loaded
automatically. The frontend and backend role skills inspect the repository and load only the
matching technology references. Use the instruction curator explicitly when a rule should persist.
