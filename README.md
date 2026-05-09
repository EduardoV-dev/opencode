# opencode config

Personal [opencode](https://opencode.ai) config + agent skills.

## Setup

```bash
git clone git@github.com:EduardoV-dev/opencode.git ~/.config/opencode
```

## Structure

- `opencode.json` — Provider, models, agent modes, MCP config
- `AGENTS.md` — Always-active skills & instructions
- `.agents/skills/` — Custom skills (caveman, cavecrew, etc.)
- `skills-lock.json` — Skill dependency lockfile

## Usage

Run `opencode` from any project — AGENTS.md auto-loads caveman mode and skills.
