# Post-Trial Wizard: Open Questions & Decisions
<!-- Last updated: April 16, 2026 -->

Tracks architectural decisions and open items for the post-trial onboarding wizard. See [post-trial-onboarding.md](post-trial-onboarding.md) for the full project brief and [pre-account-architecture.md](pre-account-architecture.md) for the predecessor flow.

---

## Decided

### Trigger point — standalone route, not tied to OAuth callback
The wizard will live at its own route (e.g. `/onboarding`) rather than being wired into the trial creation OAuth callback. This makes it more versatile and easier to test independently.

Access will be gated so users who have already completed or dismissed the wizard cannot re-enter the route (equivalent to checking `usedPresetAndHasNotCustomized` in the pre-account flow — a new flag needed on the user record).

### Screen 3 data source — fixture templates for MVP, AI deferred
Decided April 16 with Jon Tascher (Staff Engineer).

MVP uses deterministic industry fixture templates (`/api/industry-fixture`) — the 3–5 most common appointment types per industry vertical. No LLM for Phase 1.

Rationale:
- Limited inputs (broad industry only) don't justify LLM complexity for MVP
- Fixtures provide immediate value and a reliable fallback if AI is ever down
- AI bolts on as a later iteration once Jon's framework evaluation (Mastra/Rasa) completes

### Onboarding Intelligence Service — post-MVP
The Go microservice with SSE streaming and LLM integration is the correct eventual architecture (validated by Jon) but is not needed for Phase 1. Deferred until AI timeline is confirmed.

When AI does ship:
- Separate Go service, publicly exposed routes
- Short-lived JWTs issued by the monolith for auth (MFE calls service directly — PHP not in streaming path)
- Squarespace Enterprise LLM account exists — Jon owns access and timeline
- Caching required for cost management

### Streaming (SSE) — future state
SSE architecture is correct and validated but is not a Phase 1 requirement. Screen 3 uses a simple request/response to `/api/industry-fixture` for MVP.

### Deployment — SAS/CDN over npm package
Independent deployability wins for a wizard that will iterate quickly. Separate FEBS build pipeline, bundles deployed to CDN, resolved by a new `PostTrialOnboardingStaticAssetService`. Drone CI config is the primary known challenge (same as pre-account).

### Write path — single batch on completion
Single `POST /api/onboarding/complete` on the final CTA. Not per-step progressive writes. Simpler for Phase 1 and acceptable given the short wizard length.

### Abandoning the wizard
If user skips or abandons before Screen 5, no data is written (follows from batch write approach). On next login they see the homepage — the wizard does not re-show. Anything partially entered during the session is discarded.

### Availability write path — identified
`PATCH /api/app/v1/calendars/{calendarId}/regular-hours`. Requires fetching default `calendarId` first via `GET /api/app/v1/calendars`.

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

### Stock photo integration
Jon's action item: guide design team to use Squarespace's stock photo partnership. Unclear whether this applies to Screen 5 (branding/cover image) or Screen 3 (appointment cards). Needs design clarification.

### Screen 4 placement
Product open question: move business hours (Screen 4) earlier in the flow — after business type but before appointment creation — to act as an interstitial while fixture data loads. No architectural blocker; just a `STEP_ORDER` reorder. Needs product/design sign-off.

### Final styling page (Screen 5)
Open question: should Screen 5 launch directly into the full CSP editor instead of the limited preview? Luenne previously felt embedding full CSP on mobile was too much. Revisit post-launch.

### Homepage state on wizard completion
Needs confirmation: does `completedPostTrialWizard = true` need to trigger a specific homepage variant ("stage 2"), or does the standard homepage with auto-completed checklist tasks suffice?

### AI timeline
Jon owns conversations about accelerating AI framework work (Mastra/Rasa evaluation). Passive dependency for Phase 1 — needed before AI bolts onto Screen 3 post-MVP.
