# Design: Post-Signup Onboarding Wizard

**Figma source**: [UXT / Onboarding — [4.8] Hybrid](https://www.figma.com/design/okhVkzSEB2CLfob8eUABcm/%E2%9C%BC-UXT---Onboarding?node-id=1284-28539)  
**UXR research**: [A/B Concept Test Synthesis (FigJam)](https://www.figma.com/board/FigJam-board-link) — 6/12 tests, Luenne Neri  
**Key frames node**: `898:8470` (Wizard / Key frames)  
**Selected concept**: Hybrid — Concept A template cards (fast path) + Concept B stepped flow (creation path). Confirmed April 16, 2026 by UXR research synthesis. See [leads weekly](../meetings/2026-04-16-leads-weekly.md) and [design direction update](../meetings/2026-04-09-design-direction-update.md).

## Screen Inventory

### Screen 0 — Intro (`750:30505`)
**Nav**: Back (top left)  
**Headline**: "WELCOME TO ACUITY / Get your booking page ready in minutes"  
**Body**: 3-step list with illustrations:
1. Tell us about you — We'll personalize the setup to how you work.
2. Create your first service — Describe what clients can book and set your schedule.
3. Style your page — Customize your page so it represents your brand.

**CTAs**:
- Primary: "Get started" (full-width dark button, bottom)
- Secondary: "Skip" (text link below button)

---

### Screen 1 — Business Type
**Nav**: Back | Step X of Y | Skip  
**Headline**: "What best describes what you do?"  
**Subtext**: "This helps us tailor your experience and make recommendations."  
**Selection grid** (icon + label):
- Beauty
- Wellness
- Fitness
- Business Services
- Utility
- Education
- Other (free text / type-ahead)

**CTA**: "Next" (full-width dark button)

---

### Screen 2 — Service Type
**Nav**: Back | Step X of Y | Skip  
**Headline**: "What type of services do you offer?"  
**Subtext**: "This helps us tailor your experience and make recommendations."  
**Options** (single select):
- **Appointments** — Clients book a service and pick a time slot. Perfect for 1:1 bookings or consultations.
- **Classes** — Multiple people book into the same time slot.
- **Both appointments and classes**

**CTA**: "Next"  
**Note**: Phase 1 only builds the appointments path. Classes path deferred.

---

### Screen 2.5 — [TBD: More Specific Step]
> **Status**: Not yet designed. UXR confirmed that broad industry selection alone (Screen 1) is insufficient to generate relevant fixture cards. A more specific step is needed before Screen 3 to narrow the user's context (e.g., sub-vertical, target client type, or specific service category). What this step collects is not yet defined — needs design input from Luenne. Do not implement Screen 3 until this step is specified.

---

### Screen 3 — Appointment Creation
**Nav**: Back | Step X of Y | Skip  
**Headline**: "Add your first appointment"  
**Subtext**: "Choose up to 3 services to start with, or create your own."  
**Content**: Carousel of fixture-based appointment suggestions based on business type (Phase 1: deterministic fixtures; Phase 2: AI-generated)  
Each card shows:
- Appointment type name (e.g., "Haircut")
- Duration + price (e.g., "60 minutes @ $100.00")
- AI-generated description (editable)
- "Public Access" toggle
- Edit (pencil) icon

**Interactions**:
- User can edit name, duration, price, description inline
- "Create your own" link below carousel (was "+ New appointment type" — renamed per UXR)
- Expand card to edit details

**CTA**: "Select and continue"

**UXR note**: Users expected fixture/AI-generated cards to be a good *starting point*, not ready-to-use output. Framing as suggestions (not pre-made answers) reduces anxiety. Users were comfortable editing — they just needed to know editing was expected.

---

### Screen 4 — Business Hours
**Nav**: Back | Step X of Y | Skip  
**Headline**: "Set up your business hours"  
**Subtext**: "You'll be able to edit this and individual calendars' availabilities later."  
**Preset options** (radio-style, single select):
- Tuesday to Sunday, 10 AM – 7 PM
- Tuesday to Sunday, 9 AM – 5 PM
- Weekends, 9 AM – 5 PM
- Everyday, 9 AM – 10 PM
- ✏️ Custom business hours

**Helper text**: "Suggested times based on similar businesses."  
**CTA**: "Next"

---

### Screen 5 — Booking Ready
**Nav**: Back (top left) | Close (top right)  
**Headline**: "You are ready for your first booking!"  
**Subtext**: "Share this appointment and let clients book with you."  
**Preview card**: Live rendering of their booking page showing:
- Schedule (e.g., "Every Tuesday @ 7 PM")
- Service name + duration + price
- Description
- Book button
- Spots remaining

**Brand customization strip** (bottom):
- Color palette selector (dark/light)
- Font selector (e.g., Source Sans Pro)
- Cover image picker

**CTAs**:
- Primary: "Share" (full-width dark button)
- Secondary: "Book a test appointment" (lets users experience their own booking flow)
- Tertiary: "Continue editing" (text link or close)

**Next steps treatment** (launchpad, not finish line): Surface 2–3 suggested next actions after sharing, e.g.:
- "Book a test appointment to see what clients experience"
- "Add more services"
- "Set up payment"

**UXR note**: Screen 5 has a "false summit" problem — users completing it felt the product was less capable than expected because the screen looked like an end state, not a launchpad. The fix is to make it clear that the wizard was a fast path to get started, and that more setup awaits. Do NOT present this as "done." The headline and CTA framing should convey "you're ready to start taking bookings" while clearly surfacing what's next.

---

## Visual Design Notes

- **Background**: White (#FFFFFF)
- **Primary button**: Dark navy/black, full-width, rounded, white text
- **Secondary action**: Text link, no button chrome
- **Typography**: Serif headline (large, centered), sans-serif body
- **Progress**: "Step X of Y" shown in top nav
- **Nav pattern**: Back chevron (top left), Skip (top right)
- **Viewport**: Mobile web, 390px width

## Concept A: Template-First (Fast Path)

> **Status as of April 16, 2026**: **Confirmed as the central fast path** in the hybrid concept. UXR synthesis (6/12 tests, Luenne) validated Concept A's speed advantage — users prioritizing fast setup consistently preferred the template-card approach. Concept B is the depth mode for custom creation. Updated designs from Luenne pending.

Originally called "Concept 1" and deprioritized at the March 30 concept review. Reconsidered April 9 after early UXR signals. Fully confirmed April 16 after UXR synthesis.

UXR findings:
- 4/6 users preferred Concept B overall, but Concept A excelled in **speed perception**
- Template cards reduce blank-slate anxiety — users don't have to start from nothing
- Users expected generated cards to be a starting point, not final output — framing matters
- Merged concept uses Concept A as the entry path, with Concept B activating when user taps "Create your own"

Original concern (still valid): users must not feel like they are "correcting" system-generated content. Template cards should feel like a fast-path choice, not a bundle that was auto-applied.
