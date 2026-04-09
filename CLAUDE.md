# UX Transformation Team — AI Context Repository

This repository is the shared context hub for the Acuity UX Transformation Team. It is designed to be read by AI agents to provide consistent, up-to-date project context across all engineers on the team.

## How to use this repo

Clone it alongside your main `acuity` repo:
```
~/acuity/                  # main repo
~/acuity-uxt-context/      # this repo
```

Then use the slash commands below from within the `acuity` repo (or any project directory) by pointing Claude at this repo's context files.

## Slash commands

| Command | Purpose |
|---------|---------|
| `/uxt-context` | Load all team context — start here before any UXT work |
| `/uxt-wizard` | Load the post-trial wizard design spec for implementation |

## When to read what

Before writing any UXT-related code, run `/uxt-context`. Claude will read the key files and confirm its understanding of the project before you give it a task.

For wizard screen implementation specifically, run `/uxt-wizard` to load the screen-by-screen design spec.

## Keeping this up to date

These files should be updated when:
- A new one-pager is approved → add to `.context/projects/`
- A concept review decision is made → add to `.context/meetings/`
- Strategy shifts (e.g., mobile app investment changes) → update `.context/strategy/mobile-strategy.md`
- New Figma screens are approved → update `.context/design/`

Owner: Engineering lead on UXT. PRs welcome from any squad member.
