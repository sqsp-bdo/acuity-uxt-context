# Post-Trial Wizard: Open Questions & Decisions
<!-- Last updated: April 15, 2026 -->

Tracks architectural decisions and open items for the post-trial onboarding wizard. See [post-trial-onboarding.md](post-trial-onboarding.md) for the full project brief and [pre-account-architecture.md](pre-account-architecture.md) for the predecessor flow.

---

## Decided

### Trigger point — standalone route, not tied to OAuth callback
The wizard will live at its own route (e.g. `/onboarding`) rather than being wired into the trial creation OAuth callback. This makes it more versatile and easier to test independently.

Access will be gated so users who have already completed or dismissed the wizard cannot re-enter the route (equivalent to checking `usedPresetAndHasNotCustomized` in the pre-account flow — a new flag needed on the user record).

### Screen 3 AI generation — mock first, decide later
The AI service suggestion mechanic is still unclear from design and product. Plan:
1. Stand up the route first with mocked fixture data to unblock frontend work
2. Meet with Squarespace to understand what AI/ML integrations are available
3. Evaluate whether this belongs in a dedicated microservice responsible for the onboarding domain (pros: isolation, independent scaling; cons: new infra, cross-team dependency)

`/api/industry-fixture` (from pre-account) may serve as the interim mock source.

### Availability write path — identify via codebase exploration
Screen 4 writes business hours to an existing account. The exact API endpoint in the monolith needs to be found. Can be done via codebase search when ready to implement Screen 4.

---

## Still Open (needs design/product input)

### Concept A fast path
Designs not yet finalized — awaiting updated Figma from Luenne (as of April 9, 2026). Do not implement until designs land.

### Classes path (Screen 2)
Phase 1 builds appointments only. If a user selects "Classes" or "Both" on Screen 2, it is unclear whether to:
- Dead-end with a message
- Show a placeholder / "coming soon"
- Route them out of the wizard entirely

Product and design need to resolve this before Screen 2 is implemented.
