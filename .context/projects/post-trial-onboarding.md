# Project: Post-Signup Interstitial Onboarding
<!-- Previously called "post-trial onboarding" — renamed April 16, 2026. The experience fires after a user starts a trial (post-signup), not after a paid subscription. -->

**Squad**: Growth Acquisition  
**Stage**: Approved as time-boxed learning bet  
**Author**: Emily Ng  
**Team**: Jabari Bell, Luenne Neri, Siena Mayer-Costa, Adria Evans, David Derocher  
**Figma**: [UXT / Onboarding — [3.30] Concepts](https://www.figma.com/design/okhVkzSEB2CLfob8eUABcm/%E2%9C%BC-UXT---Onboarding?node-id=750-19519)

## Problem

New trialers on mobile web see too much complexity too soon. After trial creation, mobile web users land on the same homepage setup checklist desktop users see — with no guided path, and no opinionated order. Clicking into any checklist item opens deep configuration (compressed desktop webviews) without navigation context.

**Root cause**: Our core setup UX was designed for desktop, then compressed into mobile webviews. Mobile web trialers encounter the full configuration surface before they've built a mental model of what matters most.

## Hypothesis

If we provide an immersive, guided onboarding flow immediately after trial creation — one that lets mobile web trialers build a bookable experience without navigating core configuration UX — more will reach "open for business" faster, improving TTS 14D.

Rests on two validated assumptions:
1. **The first booking is the aha moment** — get users there fast, even imperfectly
2. **Momentum beats completeness** — define minimum viable setup, defer everything else

## Prior Evidence

- **Pre Account Creation Onboarding Phase 2**: +4.46pp increase in Trial to Updating CSP (stat sig), +18% directional lift in Assign to Sub for mobile web. But pre-trial placement hurt trial volume.
- **Goal**: Move guided approach post-trial to capture activation gains without sacrificing top-of-funnel volume.

## Solution: Hybrid of Concept A + Concept B

> **Updated April 16, 2026**: Hybrid confirmed by UXR research. See [leads weekly notes](../meetings/2026-04-16-leads-weekly.md).

Research findings:
- Concept B preferred overall
- Concept A excelled in speed perception
- Both reduced blank slate anxiety
- Users expected AI-generated content to be a good *starting point*, not ready-to-use

**Confirmed merged concept:**
- **Fast path (Concept A) is central** — single-tap card selection from pre-generated suggestions
- **A more specific step is added before generation** (beyond broad industry) to improve card relevance
- **Concept B is the "depth mode"** — guided creation flow activates when user wants to build a custom appointment type

**Two parallel launch paths (both confirmed):**
- **Path A — Linear wizard** (Screens 0–5): Sequential, structured, evaluator mindset
- **Path B — Chat-based**: Non-sequential, user-driven, users choose what matters to them and see relevant parts of Acuity sooner

A forking path at the start allows users to choose between Path A and Path B. Chat path requires an initial sequential phase (vertical + appointment type) before going non-sequential.

Both paths are expected to coexist. The original concept review (see [2026-03-30](../meetings/2026-03-30-concept-review.md)) chose Concept B over Concept A in isolation, but UXR testing confirmed the fastest path combines both.

### Wizard Flow

**Screen 0 — Intro**
- Headline: "Get your booking page ready in minutes"
- 3-step overview shown to user:
  1. Tell us about you (we'll personalize the setup)
  2. Create your first service (describe what clients can book)
  3. Style your page (customize to represent your brand)
- CTA: "Get started" / "Skip"

**Screen 1 — Business Type** (`What best describes what you do?`)
- Helps tailor experience and make recommendations
- Options: Beauty, Wellness, Fitness, Business Services, Utility, Education, Other
- Selection drives AI suggestions in Step 3

**Screen 2 — Service Type** (`What type of services do you offer?`)
- Options:
  - Appointments — Clients book a service and pick a time slot. Perfect for 1:1 bookings or consultations.
  - Classes — Multiple people book into the same time slot.
  - Both appointments and classes
- **Phase 1 scope: Appointments only**

**Screen 3 — Appointment Creation** (`Let's add your first appointment type`)
- Pre-filled AI suggestions based on business type (e.g., "Haircut, 60 minutes @ $100.00")
- User can edit name, duration, price, description
- AI-generated description shown inline for approval/edit
- "+ New appointment type" to add more
- CTA: "Select and continue"

**Screen 4 — Business Hours** (`Set up your business hours`)
- Preset options (smart defaults by similar businesses):
  - Tuesday to Sunday, 10 AM – 7 PM
  - Tuesday to Sunday, 9 AM – 5 PM
  - Weekends, 9 AM – 5 PM
  - Everyday, 9 AM – 10 PM
  - Custom business hours
- Note: "You'll be able to edit this and individual calendars' availabilities later"

**Screen 5 — Booking Ready** (`You are ready for your first booking!`)
- Live preview of their booking page with their service
- Brand customization: color palette, font, cover image
- CTA: "Share" (primary) — let clients book with you
- Secondary: "Continue editing"

### Design Principles Applied
- Start with the offer, not the configuration model
- Keep setup shallow and opinionated
- Use service-provider language, not Acuity jargon
- Progressive disclosure for secondary controls
- Defer sharing, embedding, and advanced config until after appointment is created

## In Scope (Phase 1)
- Mobile web only
- Appointment-based (1:1) modality only
- Post-signup placement (immediately after trial creation)
- Minimum viable inputs to create a bookable appointment
- Both linear wizard (Path A) and chat-based onboarding (Path B) — forking path at start
- Prefabricated fixture content for Phase 1; AI integration in a later phase

## Deferred
- Class-based modality
- Desktop and admin app adaptation
- Deeper guided experience beyond initial onboarding
- Navigation improvements (separate initiative)

## KPIs

| Primary | Secondary | Counter |
|---------|-----------|---------|
| Trial to Sub 14D | Completion of key setup tasks, Time to first booking, Time to test appointment | Do not harm churn, Do not harm trial volume |

## Opportunity Size
- Conservative: +1,183 subs annualized
- Aggressive: +2,365 subs annualized

## Key Risks
- Post-trial placement may not replicate pre-trial lift (pre-trial gains may have been partly self-selection)
- Interaction with Activation team's mobile web nav experiment — coordinate timing
- Users may perceive product as less powerful if follow-up pathways after wizard are weak
