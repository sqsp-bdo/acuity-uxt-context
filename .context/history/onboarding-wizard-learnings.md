# Historical: Onboarding Wizard Learnings

These are validated learnings from prior onboarding experiments. Engineers and designers should treat these as strong priors when making implementation decisions.

## 1. The Original Onboarding Wizard Was Failing Most Users

- **54% of users closed the wizard before completing step 1** — never saw a fully set-up scheduling page
- Dropoff was significantly worse for Attached users (70%) vs Standalone users (40%) on step one
- Only 30% completed all wizard steps; 13% completed just step one; 3% completed two steps

**Implication**: A wizard that front-loads too many steps or asks for too much too soon will be abandoned. Every step must feel immediately valuable.

## 2. Home Page MVP Replaced the Wizard — and Drove +9% Trial-to-Sub

When the Acuity Home Page launched (May 17, 2023), it replaced the wizard with clear, paced setup steps + a preview of their scheduling page.

| Metric | Result |
|--------|--------|
| Overall Trial → Sub | **+9% increase** |
| Attached Trial → Sub | +14% increase |
| Standalone Trial → Sub | +7% increase |

**Why it worked**: +34% more users viewed the Customize Appearance page — this was their "aha moment" (seeing a live preview of what clients would see).

## 3. The Wizard Was Then Removed — Flat Result

A/B test to remove the wizard ran 6/13/24–7/20/24 after the Home Page launched:
- Trial-to-Sub was **flat** across all cuts
- Activation event rates decreased (wizard front-loaded actions), but **no correlation found between activation events and subscriptions**
- Variant users had **lower 1-day churn** (11.28% vs 15.40%) — less friction during trial period
- **Decision**: Roll out wizard removal to 100%

### Brian's Perspective on This Decision
> The A/B test was more or less equal on both groups, but the decision was made to remove the wizard because of a bias for the shiny new Home Page. This may have been the right call at the time, but does **not** mean a wizard concept is undesirable. The tested wizard was dated and not robust in meeting the goal of establishing a business-ready/bookable state. It likely tested on par with control because of that, not because wizards don't work.

**Implication**: A modern, well-designed wizard optimized for today's user needs could be net positive. Don't read the flat result as evidence against wizards — read it as evidence that *that specific wizard* wasn't good enough.

## 4. Friction at Trial Start Is Highly Detrimental

Pre-Trial Landing Page test (April 2024) gated trial creation behind a CTA:

| Metric | Control | Experiment |
|--------|---------|------------|
| Trial starts | 88% of visitors | 23% of visitors |
| Views Scheduling → Sub (14D) | 2.5% | 1.9% |
| 1-day Churn | 4.7% | 2.2% |

**Key learning**: The automatic trial experience is a powerful conversion lever. Users want to get to the product immediately. Consistent UXR finding: **"get me to the product."**

## 5. Day 0 Is the Make-or-Break Moment

- **55–84% of trialers drop off between Day 0 and Day 1**
- Users who complete all basic setup actions on Day 0 are far more likely to subscribe
- **Customize Appearance was the most-clicked task** (9,024 uniques), beating even Create Appointment Type (6,534)

**Implication**: The "aha moment" is seeing their own branded scheduling page — not completing configuration. Prioritize getting users to a visual preview fast.

## 6. Lowering Task Completion Barriers Leaned Positive

"Drive home page tasks directly to sub-pages" test (May–June 2025):
- **+2.5% increase in 14D Trial-to-Sub** (not stat sig, but rolled out to 100%)
- Task completion criteria were also lowered (e.g., editing the default 'Consultation' appointment counts as "Create appointment type")

## 7. Pushing the Mobile App Too Early Hurt Conversion

A/B test with mobile app QR code on Home Page (Nov–Dec 2024):
- **Leaned negative on Trial-to-Sub** — rolled back
- Hypothesis: pushing users to the app before completing key activation tasks made onboarding harder due to lack of onboarding in the mobile app at that time

**Implication**: The app upsell must come after users have seen value, not before.

## 8. Trial Load Time Directly Impacts Conversion

- ~20% of users were lost during the trial loading screen
- Median trial load time: **18 seconds**; P95: **45 seconds**
- Optimizing load time (median -3s, P95 -3.5s) showed **stat sig improvement in 7-day Trial-to-Sub**

**Implication**: Performance is a conversion lever. Any wizard or onboarding flow must load fast.

## 9. Pre-Account-Creation Onboarding Phase 2 Proved Guided Flows Work

- **+4.46pp increase in Trial to Updating CSP** (stat sig)
- **+18% directional increase in Assign to Sub** for mobile web users
- BUT: pre-trial placement created friction that **sharply decreased trial volume**

**Implication**: Guided onboarding works on mobile web. The question is placement. Post-trial is the current bet to get the activation gains without the volume penalty.

## 10. Three Core Themes for Future Onboarding

From Core Journey Review and UXR Brief:
1. **Tailored onboarding flows** — Use intent data (industry, goals, stage of business) to personalize
2. **Driving deeper actions** beyond basic setup — Users aren't being guided past initial page configuration
3. **Real-time preview** — Users can't see changes in context, which delays the "aha moment"

---

## UXR: A/B Concept Test Synthesis (April 2026)

*Source: Luenne Neri — FigJam synthesis from 6/12 usability tests comparing Concept A (template cards) vs Concept B (stepped creation). Conducted before the April 16 leads weekly.*

### 11. "Good Starting Point" Is the Right Mental Model for Generated Content

Users did not expect AI/fixture-generated cards to be final or accurate. They expected them to be a reasonable starting point that they would edit. This is healthy — it means generated content won't backfire as long as it's framed as suggestions, not pre-made answers.

**Implication**: Copy and UX framing must reinforce the "starting point" idea. Phrases like "we'll suggest a few" or "customize these" set the right expectation. Do NOT frame generated cards as "your services" or present them as if already configured.

### 12. "False Summit" on Screen 5 — The Completion Screen Felt Like an End, Not a Beginning

Users who reached Screen 5 ("You are ready for your first booking!") felt the product was less capable than expected. The finish-line framing made the product feel shallow — like setup was *done* when in reality they'd only done the minimum.

**Implication**: Screen 5 must be designed as a **launchpad**, not a finish line. Surface next steps prominently. "Book a test appointment" and "Add more services" should be visible CTAs — not buried. The screen should communicate "you're ready to take bookings AND there's more to explore."

### 13. "Ready to Book" Meant Different Things to Different Users

Some users interpreted "ready for your first booking" as meaning a client could already book — and were surprised when they explored further and found more setup required. Others expected the phrase to mean "the minimum is done, there's more to do."

**Implication**: Avoid language that implies completeness. Prefer language that implies capability: "You can now take bookings" vs "You're ready." The distinction matters for expectation setting.

### 14. Broad Industry Selection Alone Doesn't Generate Relevant Suggestions

Selecting a broad vertical (e.g., "Wellness") is not specific enough to produce relevant appointment type cards. Users from different sub-verticals within the same category found the suggestions too generic.

**Implication**: A more specific data-collection step is needed between Screen 2 (service type) and Screen 3 (appointment creation). What it collects is TBD (design input needed), but it must narrow the context enough to produce cards that feel tailored rather than generic.

### 15. Concept A and Concept B Serve Different User Mindsets — Both Are Needed

- **Concept B** (stepped creation flow) was preferred overall by 4/6 users — it felt thorough and confidence-building
- **Concept A** (template cards) excelled for users who wanted to go fast — it reduced blank-slate anxiety instantly
- Neither worked well alone for the full range of users

**Implication**: The hybrid is not a compromise — it's the right design. Concept A as the entry point (fast path via template cards) with Concept B as the depth mode (activated via "Create your own") serves both the speed-focused and thoroughness-focused user mindsets.
