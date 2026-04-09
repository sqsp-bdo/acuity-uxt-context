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
