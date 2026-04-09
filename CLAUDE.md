# UX Transformation Team — AI Context Repository

This repository is the shared context hub for the Acuity UX Transformation Team. It provides consistent, up-to-date project context for AI assistants across all engineers — regardless of which AI tool you use.

## Installation

Choose the approach that fits your workflow:

### Option 1 — npx skills add (one command, any tool)
```bash
npx skills add squarespace/acuity-uxt-context
```
Installs `/uxt-context` and `/uxt-wizard` into Claude Code (and other supported tools) via the [Vercel Labs skills tool](https://github.com/vercel-labs/skills). Requires the repo to be on GitHub.

### Option 2 — Claude Code plugin
```
/plugin install squarespace/acuity-uxt-context
```
Installs as a Claude Code plugin. Skills become available as `/acuity-uxt-context:uxt-context` and `/acuity-uxt-context:uxt-wizard`.

### Option 3 — Git submodule (best for teams on the acuity repo)
```bash
cd ~/acuity
git submodule add <repo-url> .uxt-context
```
The `.context/` files are then accessible at `.uxt-context/` inside the acuity repo. Engineers stay in sync with `git submodule update`.

### Option 4 — Manual / other AI tools
Clone alongside `acuity` and point your tool at the files directly:
```
~/acuity/
~/acuity-uxt-context/
```

| Prompt file | Purpose |
|-------------|---------|
| `prompts/uxt-context.md` | Load all team context — start here before any UXT work |
| `prompts/uxt-wizard.md` | Load the post-trial wizard design spec for implementation |

Paste into your chat, or use your tool's `@file` / file attachment syntax to reference them.

---

## What's in `.context/`

| Directory | Contents |
|-----------|---------|
| `team/` | Mandate, guiding principles, ICPs, sprint operations |
| `projects/` | One-pagers for each active project |
| `strategy/` | Mobile web vs. app bridge strategy |
| `design/` | Screen-by-screen design specs with Figma references |
| `history/` | Validated learnings from prior experiments |
| `reference/` | Metrics glossary with baselines |
| `meetings/` | Concept review decisions and direction updates |

## Keeping this up to date

- New one-pager approved → add to `.context/projects/`
- Concept review or design decision → add to `.context/meetings/`
- Strategy shifts → update `.context/strategy/`
- New Figma screens approved → update `.context/design/`
- Prompt changes → update `skills/` and `prompts/` together

Owner: Engineering lead on UXT. PRs welcome from any squad member.
