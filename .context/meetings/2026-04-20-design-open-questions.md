# Design Open Questions — Post-Signup Onboarding
**Date**: April 15–20, 2026 (async comments on shared doc, reviewed in meeting April 20)  
**Participants**: Brian Do (Engineering), Leunne Neri (Design)  
**Source**: Google Doc — "Open Questions Post-Signup Onboarding"

---

## Decisions Made

### 1. Free-Text Input Handling
**Question**: How should we handle garbage or misaligned free-text input in open-ended fields (e.g., specific service request)?  
**Decision**: If input doesn't align with the selected industry, fall back to generic appointment types for that broad industry. The concept is intentionally not agentic/chat-based, so misaligned input should degrade gracefully. Leunne sees an opportunity to learn from user inputs and light-test mapping common answers to predefined industries, but for Phase 1, invalid input = go generic.

### 2. Default Data for Duration & Price
**Question**: What drives default selections for appointment duration and price? AI-generated? What inputs?  
**Decision**: Defaults will be AI-generated based on **industry, service, and ideally location**. For the "create new" path, price should take all previous steps into account (including duration input). Phase 1 uses fixtures; AI generation in Phase 2.

### 3. Image Generation — Deferred
**Question**: Is image generation still required for this phase given limited inputs and high cost/latency concerns?  
**Decision**: **Deferred to a later iteration.** Leunne agreed this is a valid concern and is fine with a standard upload utility for Phase 1 instead of AI image generation.

### 4. AI Streaming — Not Needed
**Question**: Should we use a streaming API (ChatGPT-style) for AI generation feedback on mobile?  
**Decision**: **Not needed for Phase 1.** Brian: "Don't think that this will be an issue with fast models and the simple nature of the responses." Revisit if latency becomes a problem.

### 5. Availability Screen — Keep Simple
**Question**: Can we move "Select your business hours" earlier in the flow as an interstitial while AI generates appointment types?  
**Decision**: Keep it simple with "Selecting your business hours" — similar to how the home page stage 1 works. Leunne is still refining the interface for users who want to set more advanced availability, but the wizard version should stay basic (business hours only, not availability groups or complex schedules).

### 6. Final Styling Page (CSP) — Deferred Full CSP
**Question**: Should the final screen launch the full CSP styling page instead of the limited view?  
**Decision**: **Do not use the actual full CSP.** Brian: "The more I think about using the actual CSP, the more I believe that it might slow our velocity." Revisit in a later iteration. Keep the mini/limited CSP preview for Phase 1.

### 7. AI Dependencies Down — Fixture Fallback
**Question**: What happens when AI service is unavailable?  
**Decision**: Fall back to **templatized appointment types per vertical**. Leunne has a list of verticals for industry and is going to determine the template appointment types for each. This aligns with the Phase 1 fixture-first approach.

### 8. Abandoning the Wizard
**Question**: If a user skips or abandons the wizard, do they see the home page on next login? Is partial setup discarded?  
**Decision**:
- **Passive quit** (browser crash, accidental close): Show the wizard again on next login.
- **Active quit** (user explicitly skips): Show the home page on next login; do not re-show the wizard.
- **Partial setup is discarded** for Phase 1.
- A **confirmation dialog** will be added to skip/abandon actions. Leunne will add this to designs.
- The "Do this later" text should be revised to make it clearer the user is choosing to skip.
- Rationale: Differentiating active vs. passive quitters avoids tricky states (e.g., user creates appointment types in the traditional UI, then returns to the wizard).

### 9. Homepage State After Wizard Completion
**Question**: Does the user see home page stage 2 after completing the wizard?  
**Decision**: **Leunne is designing a new home page component** to signify that the user completed the wizard and show progress better. Not simply stage 2 — a distinct post-wizard treatment.

### 10. Foreign Currency — USA Only for Phase 1
**Question**: Should we support foreign currency in generated appointment types?  
**Decision**: **Limit to USA for Phase 1.** Need to think through edge cases with currency, UX implications, and sync between Squarespace and Acuity before expanding.

### 11. CSP Style Setting — Being Rethought
**Question**: How does the color/style selection work on the final screen? Style groups vs. individual color pickers?  
**Decision**: **Leunne is rethinking this page.** She identified that the color selection is not fully represented on the mini CSP. Updated designs pending.

---

## Still Open

### Flow Conclusion
**Question**: What does the share button interaction look like on the final screen? How does the user transition from the final screen of the wizard to `home.php`?  
**Status**: No response yet. Needs design input from Leunne.

---

## Impact on Wizard Scope

| Area | Before | After |
|------|--------|-------|
| Image generation | Included in concept | **Deferred** — use upload utility |
| AI streaming UX | Open question | **Not needed** for Phase 1 |
| Full CSP on final screen | Open question | **Deferred** — keep mini CSP |
| Currency support | Unspecified | **USA only** for Phase 1 |
| Availability complexity | Two screens (edit + display) | **Simplified** — business hours only |
| Wizard abandonment | Unclear | **Active vs. passive quit** distinction with confirmation dialog |
| AI fallback | Undefined | **Fixture templates per vertical** |
| Post-wizard homepage | Stage 2 assumed | **New component** being designed |
| CSP style selection | Unclear | **Being rethought** by Leunne |
| Flow conclusion (share → home) | Undefined | **Still open** |
