# UX Transformation Team — AI Context Repository

This repository is the shared context hub for the Acuity UX Transformation Team. It provides consistent, up-to-date project context for AI assistants across all engineers on the team — regardless of which AI tool you use.

## How to use this repo

Clone it alongside your main `acuity` repo:
```
~/acuity/                  # main repo
~/acuity-uxt-context/      # this repo
```

Point your AI assistant at the files in `.context/` and `prompts/` before starting any UXT work.

## Using with your AI tool

### Claude Code
Slash commands are pre-configured in `.claude/commands/`:
- `/uxt-context` — loads all team context
- `/uxt-wizard` — loads the wizard design spec

### Cursor / Copilot / Gemini / other tools
Use the prompts in `prompts/` directly — paste them into your chat, or reference them with your tool's file attachment or `@file` syntax:

| Prompt file | Purpose |
|-------------|---------|
| `prompts/uxt-context.md` | Load all team context — start here before any UXT work |
| `prompts/uxt-wizard.md` | Load the post-trial wizard design spec for implementation |

### Any tool
The `.context/` files are plain markdown — attach or reference them however your tool supports it.

## Keeping this up to date

These files should be updated when:
- A new one-pager is approved → add to `.context/projects/`
- A concept review or design decision is made → add to `.context/meetings/`
- Strategy shifts → update `.context/strategy/`
- New Figma screens are approved → update `.context/design/`
- Prompts need changing → update `prompts/`, then `.claude/commands/` will follow automatically

Owner: Engineering lead on UXT. PRs welcome from any squad member.
