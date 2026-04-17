# Staff Engineer Review: Post-Trial Wizard Architecture
**Date**: April 16, 2026
**Attendees**: Brian Do, Jon Tascher (Staff Engineer)

---

## Decisions Made

### AI deferred for MVP
AI integration is not required for the MVP of Screen 3. Industry-based fixture templates (deterministic data per vertical) are sufficient for Phase 1 and provide immediate value. AI generation bolts on as a later iteration and also serves as the fallback if the AI dependency is down.

Jon's framing: a barebones starting point — the 3–5 most common appointment types for a selected industry — is the right MVP approach, especially when a user's specific sub-industry isn't listed.

### Architecture validated
- PHP monolith cannot handle SSE streaming — confirmed by Jon
- Correct pattern: separate Go service with publicly exposed routes, short-lived JWTs for auth
- This is the eventual architecture when AI ships; not needed for Phase 1

### Squarespace AI infrastructure exists
Squarespace has an Enterprise LLM account in use for a proof of concept:
- Mix of fast/cheap models for tasks like appointment type name matching
- More powerful models for conversational response generation
- Caching confirmed as the right approach for cost management and UX consistency
- Jon owns timeline conversations for accelerating the AI framework work

### Beacon ruled out
Beacon was not built for client-facing features. Admin-facing is more realistic but still complex. Not relevant for Phase 1 or the wizard.

### AI framework evaluation (future)
Jon will evaluate off-the-shelf solutions (Mastra, Rasa) for defining AI workflows and providing a routing layer. Relevant when AI gets added post-MVP — raw LLM calls are not the pattern.

---

## What This Changes

| Area | Before | After |
|------|--------|-------|
| Screen 3 data source | LLM via Onboarding Intelligence Service | Fixture templates per industry (`/api/industry-fixture`) |
| Intelligence Service | Build for Phase 1 | Post-MVP — defer until AI timeline is confirmed |
| Streaming (SSE) | Phase 1 requirement | Future state — correct architecture when AI ships |
| Screen 3 API | `GET /suggestions/stream` (SSE) | `GET /api/industry-fixture?industry=X` (request/response) |
| AI infrastructure | Unknown — meeting needed | Confirmed — Squarespace Enterprise account, Jon owns it |

---

## New Action Items

| Item | Owner |
|------|-------|
| Guide design team to use Squarespace stock photo partnership (for Screen 5 branding or Screen 3 cards — TBD) | Brian |
| Start conversations on AI timeline to support future AI framework | Jon |
| Evaluate Mastra / Rasa for AI workflow definition | Jon |
