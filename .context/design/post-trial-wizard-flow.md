# Design: Post-Trial Onboarding Wizard

**Figma source**: [UXT / Onboarding — [3.30] Concepts](https://www.figma.com/design/okhVkzSEB2CLfob8eUABcm/%E2%9C%BC-UXT---Onboarding?node-id=750-19519)  
**Key frames node**: `898:8470` (Wizard / Key frames)  
**Selected concept**: Concept 2 — Guided Step-Based Creation (see [concept review](../meetings/2026-03-30-concept-review.md))

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

### Screen 3 — Appointment Creation
**Nav**: Back | Step X of Y | Skip  
**Headline**: "Let's add your first appointment type"  
**Subtext**: "Pick and customize these any time."  
**Content**: Carousel of AI-generated appointment suggestions based on business type  
Each card shows:
- Appointment type name (e.g., "Haircut")
- Duration + price (e.g., "60 minutes @ $100.00")
- AI-generated description (editable)
- "Public Access" toggle
- Edit (pencil) icon

**Interactions**:
- User can edit name, duration, price, description inline
- "+ New appointment type" link below carousel
- Expand card to edit details

**CTA**: "Select and continue"

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
- Secondary: "Continue editing" (text link or close)

---

## Visual Design Notes

- **Background**: White (#FFFFFF)
- **Primary button**: Dark navy/black, full-width, rounded, white text
- **Secondary action**: Text link, no button chrome
- **Typography**: Serif headline (large, centered), sans-serif body
- **Progress**: "Step X of Y" shown in top nav
- **Nav pattern**: Back chevron (top left), Skip (top right)
- **Viewport**: Mobile web, 390px width

## Rejected Approach: Concept 1 (Upfront Generation)

Concept 1 pre-generated a bundle of services based on industry. Rejected because:
- Users felt they were "correcting" rather than "building"
- Opinionation must balance showing capabilities without overwhelming
- Team preferred user-provides-input over system-generates-unused-bundle
