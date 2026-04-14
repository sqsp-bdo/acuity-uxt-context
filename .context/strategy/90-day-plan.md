# UX Transformation Team: 90-Day Strategy
<!-- DRAFT — April through June 2026 -->

> Scope: April 2026 through June 2026. Time-boxed to align with Epoch planning cycle.

---

## Context

Acuity Standalone has been underperforming subscription operating plan by **10–17%** since the start of 2026. We believe the root cause is a poor new-user experience, not external factors alone. The goal of the 90-day plan is to redesign the E2E new trialer experience so Acuity feels intuitive, guided, and easy to see yourself using.

---

## Diagnosis

**Trialers encounter too much unguided configuration when getting started on Acuity.**

- The main problem for most prospects is not a lack of features — it's difficulty finding and using them.
- Users struggle with abstract features that don't demonstrate immediate value, compounded by usability issues in basic flows (setting up availability, testing the E2E client experience).
- We don't have much time: nailing the day-0/day-1 experience is paramount.
- Complex-use-case prospects don't know which parts of the product to use, even when it's possible.

### Urgency Matrix

| Dimension | Level | Notes |
|-----------|-------|-------|
| **Unworkable** — How severely do problems hinder users? | Moderate | Workable for highly motivated solopreneurs, highly unworkable for class-based sellers and anyone whose mental model doesn't match Acuity's vocabulary |
| **Unavoidable** — Is the problem inevitable? | High | Every trialer must go through some form of setup to experience value |
| **Urgent** — Is immediate action required? | High | Standalone subs down 10–17% vs. OP since Jan |
| **Underserved** — Are existing solutions inadequate? | High | Competitors are simple but lack flexible scheduling and integrated payments; we're complex where they aren't |

---

## Guiding Policy

Focus on the **Activation** phase: after trial creation, before first booking.

Two predominant trialer mindsets drive the strategy:

**Evaluator Mindset — "I want to test this out and see what I think"**
Simplify onboarding, provide an opinionated flow for their background and needs, use progressive disclosure to hide complexity.

**Intentful Mindset — "I'm just going for it and starting setup"**
Route users directly into relevant product areas as fast as possible.

This ladders into:
- **Acuity strategy**: Providing Simplicity and Delight — functionality + utility + simplicity + delight
- **Squarespace strategy**: Growing share of the service seller market

---

## Action Plan

Six coordinated initiatives. Team assignments are tentative; staffing can shift.

### 1. Post-Trial Interstitial Onboarding (Sequential)
**Squad**: Acquisition

**Why**: Dec 2024 experiment proved immersive mobile onboarding works (+4.46pp Trial to Updating CSP, +18% directional Assign to Sub), but pre-trial placement caused friction that sharply decreased trial volume. Post-trial users currently land on the generic homepage checklist with no opinionated guidance.

**What**: Immersive guided wizard after trial creation — build a bookable experience without navigating core UX. Primarily designed for the **Evaluator mindset**.

**Relevant hypotheses**: HYP 2 (vocabulary), HYP 4 (minimum data to go live)

---

### 2. Improve Appointment Type Creation
**Squad**: Activation

**Why**: Current editor exposes all configuration options to all users. Solopreneurs don't need the SMB/multi-location depth.

**What**: Visually reorganize and collapse advanced functionality that doesn't cover basic 1:1 appointment needs. Primarily designed for the **Evaluator mindset**.

**Relevant hypotheses**: HYP 2, HYP 4, HYP 5 (configurability over simplicity)

---

### 3. Simplify Availability and Calendar UX
**Squad**: TBD

**Why**: Availability is the most-cited friction point across years of research. Timezones, variable availability, and calendar integration are all major pain points in trial UXR.

**What**: Streamline availability and calendar paradigms for making appointment types bookable. Will be broken into phases. Designed for **both mindsets** — availability is a recurring task, not just onboarding.

**Relevant hypotheses**: HYP 3 (not opinionated enough), HYP 4, HYP 5

---

### 4. Scrape Existing Website or Scheduler
**Squad**: Acquisition

**Why**: ~18% of prospects are actively deciding whether to switch from a competitor (survey research). 18% of paid non-branded search traffic goes to the Acuity vs. Calendly compare page — this channel underperforms on TTS despite outperforming on LTT/LTS.

**What**: Scraping tool to create a personalized scheduling starting point from an existing scheduling link (Calendly, Square Appointments) or any page with business info (Instagram, website, Facebook). Unique experience possible for Attached prospects with existing SS website content. Primarily designed for the **Intentful mindset**.

**Relevant hypotheses**: HYP 1 (first booking is aha moment), HYP 5

---

### 5. Post-Trial AI Chatbot Onboarding (Non-Sequential)
**Squad**: Acquisition

**Why**: Scheduling workflows vary enormously by business size, offerings, industry, and staff role. Our current onboarding treats all trialers the same. A chatbot that learns a trialer's needs and configures the product for them gets them to first booking faster.

**What**: Chat-based onboarding where user dialogue drives product actions. Extends into post-trial to route users to configuration areas (payments, intake forms, reminders). Especially relevant for Attached prospects familiar with Squarespace Beacon.

**Note**: Agentic onboarding is most useful once calendars are connected and user data is set up.

**Relevant hypotheses**: HYP 1, HYP 3, HYP 4, HYP 5

---

### 6. Test Appointment Mode Iteration
**Squad**: Activation

**Why**: Experiencing the E2E client experience is crucial for trialers to feel confident about committing to Acuity.

**What**: Iterate on test appointment mode (ABC experiment kicking off April 2026) to increase confidence in the E2E client experience. [One-Pager: Help more trialers test booking an appointment](https://docs.google.com/document/d/1CV7YWbIJfxlt6aoMFjK0Pn58TyQoLVTDt21ua3Aq0Vo/edit)

**Relevant hypotheses**: HYP 1

---

## Success Metrics

- **Primary**: Landing to Sub 14D
- **Secondary**:
  - Volume of unique users with >1 booked appointment
  - Time to first booked appointment
- **Measurement approach**: Holdout groups (not traditional A/B testing). See [Operations Overview](https://docs.google.com/document/d/11Os2HZ8rH24aToZhEeQTu7ehaTgIYgBZs6hde0ySD1Y/edit).

---

## What We're Deferring

| Deferred Scope | Reason |
|----------------|--------|
| Pre-trial experiences | Need to fix post-trial activation first; activation investment amplifies future acquisition/pre-trial work |
| Homepage-only iterations | Smaller impact; homepage state depends on which onboarding we ship |
| Navigation-only iterations | Existing Growth Activation experiments in flight; Classes team may also propose nav changes |
| Classes setup/use case | Focus on simplest unit: 1:1 time. Keep classes in mind for availability changes but don't design for it in Phase 1 |

---

## Appendix: User Problems and Hypotheses

### Three Core User Problems (in sequence)

1. **"I can't see myself in this product"** → Must be resolved before 2 and 3
   - HYP 2: Vocabulary vs mental models
   - HYP 3: Not opinionated enough in setup

2. **"I need to see firsthand value of what my business looks like in this tool faster"**
   - HYP 1: First booking is the aha moment
   - HYP 4: Haven't defined minimum data to go live
   - HYP 5: Configurability over simplicity / guidance

3. **"I can't tell if this will actually work for my clients"**
   - HYP 1: First booking is the aha moment
   - HYP 4: Haven't defined minimum data to go live
   - HYP 5: Configurability over simplicity / guidance

---

### Five Hypotheses

**HYP 1: The first booking is the "aha" moment**
- Hypothesis: It's "real" for prospects when they experience that first booked appointment — even if they book it themselves
- Prompt: "Is this true? If so, can we guide them to create that first appointment rather than source it from a client?"
- Tactic: [Help more trialers book an appointment](https://docs.google.com/document/d/1CV7YWbIJfxlt6aoMFjK0Pn58TyQoLVTDt21ua3Aq0Vo/edit)

**HYP 2: Vocabulary vs mental models**
- Hypothesis: Our concepts (appointment types, availability, calendars, classes) don't match how sellers describe their work (sessions, programs, courses, staff, rooms)
- Prompt: "For our top 3 ICPs, how do they naturally describe what they sell and schedule? Where does Acuity vocabulary clash?"
- Research: [Acuity Nav & Homepage UXR](https://docs.google.com/document/d/1c0m_gvsnyVKY42wOvw5a_FnNnAMyrUiHX-FXNxhuWQw/edit)

**HYP 3: Not opinionated enough in setup**
- Hypothesis: We force users to design their own system instead of offering opinionated starting points by modality and vertical
- Prompt: "If we were uncompromisingly opinionated for our top 3 ICPs, what exact steps would we prescribe in the first 5 minutes?"

**HYP 4: We haven't defined the minimum data needed to go live**
- Hypothesis: We ask for too much configuration before users see value; we haven't agreed on minimum viable inputs to reach "open for business" — we over-optimize for completeness vs momentum
- Prompt: "What is the absolute minimum we must know about a seller to generate a credible, bookable experience? Everything else is optional or deferred."

**HYP 5: Configurability over simplicity / guidance**
- Hypothesis: Years of additive iteration have created an experience where customers succeed *in spite* of onboarding, not because of it; complexity is exposed up front rather than progressively
- Prompt: "If we started from zero and designed for 'guided by default' on mobile, what would we strip away or hide until after first booking?"
