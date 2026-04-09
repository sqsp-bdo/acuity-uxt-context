# Project: Appointment Type Creation Improvements

**Squad**: Growth Activation  
**Stage**: Approved as time-boxed learning bet  
**Author**: Andrej Radisic

## Problem

Appointment creation is the highest-friction moment in the mobile web setup journey. The current flow is an admin-heavy settings page that mixes core offer creation with advanced scheduling and operational settings. Users encounter Acuity's full configuration model before they have a mental model of what matters most.

Today: users are asked to define the offer, assign calendars, manage scheduling constraints, set visibility, attach forms, and understand secondary concepts like resources — all in one dense form.

## Hypothesis

If we redesign appointment creation into a guided, mobile-friendly flow that collects only the minimum viable inputs needed to generate a credible, bookable 1:1 appointment, more users will complete setup, reach "open for business" faster, and improve Trial to Sub 14D.

## Solution: Reorganized 3-Group Flow

Reorganize fields into groups that match the user's mental model, not Acuity's internal config model:

### Group 1 — Appointment Details
*Define the offer itself.*
- Appointment title
- Description
- Image
- Duration
- Price

### Group 2 — Availability & Scheduling
*Define how the appointment can be booked.*
- Buffer before / after appointment
- Assigned calendar
- Category
- Private appointment toggle
- Rooms / resources

### Group 3 — Client Experience
*Define what the client sees and completes.*
- Message after scheduling
- Forms

### Key UX Changes
- **Progressive disclosure**: secondary controls hidden by default
- **Service-provider language**: "rooms and spaces" not "resources"
- **Resource creation inline**: users can create a resource without leaving the flow (currently navigates away and loses context)
- **Mobile-first**: "Get started" / "Continue" button at top right, not bottom
- **Hide "more options"** for mobile web where possible

## Design Principles
- Start with the offer, not the configuration model
- Keep setup shallow and opinionated
- Reduce backtracking and context loss
- Help users get bookable before they get complete
- Clarify supporting concepts (e.g., resources = "shared rooms, spaces, or equipment required for booking")

## In Scope
- Appointment creation only
- Mobile web-first
- 1:1 appointments only
- Updated field grouping, prioritization, and disclosure patterns
- Resource creation via inline modal from the appointment flow

## Deferred
- Class-based modality
- Group appointments
- Desktop / admin app adaptation
- Broader post-publish optimization flows

## KPIs

| Primary | Secondary | Counter |
|---------|-----------|---------|
| Trial to Sub 14D | Appointment creation completion rate, Time to first booking, Time to test appointment, Time to create first public appointment | Do not harm churn, Do not harm trial volume, Do not harm successful setup on desktop |

## Key Risks
- Simpler flow may reduce discoverability of advanced controls some users need early
- Users may still struggle with calendars, category, resources if copy isn't explicit
- Deferring advanced settings may make product feel less powerful if follow-up pathways are weak
- Post-trial placement may not replicate pre-trial guided onboarding gains
- May interact with navigation simplification work — coordinate timing

## Notes from Concept Review
- Remove Airbnb-style banner
- Rename to "services" not "appointment types" (language alignment)
- Modal for resource creation must have a "save" button (currently only cancel/discard)
- Moving create button to top right corner on mobile web
- Availability deep dive needed: is availability a product or a starting point? Currently a result of many constraints (location, staff, virtual/physical)
