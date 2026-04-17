# acuity-uxt-context

Shared AI context for the Acuity UX Transformation Team. Gives any engineer's AI assistant consistent, up-to-date knowledge of UXT projects, design specs, strategy, and team operations — regardless of which AI tool they use.

## Quick start

### Claude Code (slash commands)

```bash
npx skills add sqsp-bdo/acuity-uxt-context
```

Then in Claude Code:
```
/uxt-context   — load all team context before any UXT work
/uxt-wizard    — load the post-trial wizard design spec
```

**Getting updates**: Skills are installed as a snapshot. When this repo changes, re-run:

```bash
npx skills update
```

### Cursor / Copilot / other tools

Clone alongside the `acuity` repo and reference the prompt files:

```bash
git clone https://github.com/sqsp-bdo/acuity-uxt-context ~/Documents/Repos/acuity-uxt-context
```

Then attach or `@`-reference:
- `prompts/uxt-context.md` — load all team context
- `prompts/uxt-wizard.md` — load the wizard design spec

### Git submodule (team-wide, inside the acuity repo)

```bash
cd ~/acuity
git submodule add https://github.com/sqsp-bdo/acuity-uxt-context .uxt-context
```

---

## What's in `.context/`

| Directory | Contents |
|-----------|----------|
| `team/` | Mandate, guiding principles, ICPs, sprint operations |
| `projects/` | One-pagers for each active project |
| `strategy/` | 90-day plan, mobile web vs. app strategy |
| `design/` | Screen-by-screen wizard spec with Figma references |
| `history/` | Validated learnings from prior experiments |
| `reference/` | Metrics glossary with baselines |
| `meetings/` | Concept review decisions and direction updates |

See [`.context/index.md`](.context/index.md) for the full map.

---

## Keeping this up to date

- New project one-pager → add to `.context/projects/`
- Design decision or concept review → add to `.context/meetings/`
- Strategy shift → update `.context/strategy/`
- New Figma screens approved → update `.context/design/`
- Prompt changes → update `skills/` and `prompts/` together

Owner: Engineering lead on UXT. PRs welcome from any squad member.
