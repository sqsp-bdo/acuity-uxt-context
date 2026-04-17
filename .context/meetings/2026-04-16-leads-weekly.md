# UXT Leads Weekly
**Date**: April 16, 2026
**Attendees**: Full UXT leads — Claire Crinion, Katie Remlinger, Rob Bertorelli, Claire Comfort, Brian Do, Jon Tascher, Oscar Garcia, Andrej Radisic, Jabari Bell, Luenne Neri, Gina Kim, Emily Ng, Mark Marchione, Andi Azry, Siena Mayer-Costa, Shifa Jiwani, Andrew Johnson, Carl Sutherland, Nate Lawson, Sarah Mitrano

---

## Key Decisions

### Name change: "post-trial" → "post-signup"
The project is now called **post-signup onboarding** (not post-trial). Rationale: "post-trial" implied after a paid subscription; the experience fires after a user *starts* a trial. Update all references accordingly.

### Concept A + B merge — confirmed direction
Research confirmed:
- **Concept B** was preferred overall
- **Concept A** excelled in speed perception — valuable for users prioritizing fast setup
- Both concepts reduced "blank slate anxiety"

The merged concept:
- **Fast path (Concept A) is central** — user taps a generated card to select it in a single tap
- **A more specific step is added before generation** to improve relevance of the generated cards (beyond just broad industry)
- **Concept B is the "depth mode"** — the guided creation flow activates when a user wants to build a custom appointment type rather than pick from suggestions
- Users expected AI-generated content to be a good *starting point*, not ready-to-use — framing matters

### Phased rollout confirmed
Brian raised AI service risk (downtime, latency). Agreed approach:
1. **Phase 1**: Prefabricated content aligned with broad verticals launches first — expedited delivery and learning
2. **Phase 2**: AI integration follows once infra is stable

Luenne confirmed this is a viable approach. Aligns with the fixture-first MVP decision from the Jon Tascher meeting.

### Both onboarding paths will launch
Two parallel paths confirmed for launch:
- **Path A (Linear)**: The stepped wizard (Screens 0–5) — sequential, structured
- **Path B (Chat-based)**: Non-sequential chat onboarding — users choose what's important to them and see relevant parts of Acuity sooner

A **forking path at the start** allows new users to choose between Path A and Path B — similar to Squarespace's chat interstitial implementation.

### Chat-based onboarding — initial scope
- Requires an initial sequential phase to gather core info (vertical, appointment type) before offering non-sequential options
- Uses vertical selection to present a menu of possible service offerings
- Goal: show users what an Acuity booking experience could look like for their industry with assumed defaults
- Coordination underway with Andrew / Anacey on the Appointments Team's concurrent in-product chatbot — goal is seamless tone and handoff between onboarding and in-product

---

## New Information

### Business name in notifications
Business name is blank by default for standalone users. The calendar name (set to user's name from account setup) is used in automated notifications — this field is never blank. Relevant for Screen 0–1 copy and any auto-populated preview content.

---

## Impact on Wizard Scope

| Area | Before this meeting | After |
|------|-------------------|-------|
| Project name | Post-trial onboarding | **Post-signup onboarding** |
| Concept direction | Hybrid A+B (directional) | Hybrid A+B **confirmed** — fast path central, B as depth mode |
| Step before generation | Not defined | New step added before Screen 3 to narrow industry further |
| AI / prefab | MVP = fixtures, AI later | **Phased rollout confirmed** — same plan, now team-aligned |
| Chat path | Initiative 5 in 90-day plan (future) | **Confirmed launching alongside linear wizard** — forking path at start |
| Chat scope | Vague | Initial sequential phase for vertical + appt type, then non-sequential |

---

## Open Items Raised

- Overlap between linear and chat paths needs to be defined — how does chat offer differentiated utility vs. the linear wizard?
- Forking path UX at the start needs design work (who owns this?)
- Coordination with Appointments Team chatbot — ensure onboarding and in-product chatbot tone/handoff is seamless
