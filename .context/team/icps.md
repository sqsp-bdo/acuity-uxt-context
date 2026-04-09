# Ideal Customer Profiles (ICPs)

**Source**: 2026 Acuity ICP document (internal)  
**Established by**: UXT Sprint 1, Track 2 (Emily Ng, accountable)  
**Full doc**: Separate internal document — ask Emily Ng or check the UXT shared drive

## Why ICPs Matter for Engineers

Every feature decision should be tested against: "Does this work for our ICPs?" The ICP personas are the reference point for language choices, complexity tradeoffs, and feature prioritization. When in doubt about copy, flow design, or what to show/hide, ask how the ICP would experience it.

## ICP Scope for UXT

Three ICPs were established for the UX Transformation Team:
1. **Appointment-based ICP** — e.g., a solo beauty professional (nail technician, esthetician, hair stylist)
2. **Class-based ICP** — e.g., a fitness instructor or yoga teacher
3. **Hybrid ICP** — runs both 1:1 appointments and group classes (e.g., a personal trainer who also runs boot camps)

## What We Know About the Appointment-Based ICP

From the concept review and brainstorm sessions, the appointment-based ICP (Phase 1 target) is characterized by:

- **Mental model**: Thinks in terms of "services" and "clients," not "appointment types" and "calendars"
- **Business examples**: Nails by Design, Mud Hut, Shannon Lee Esthetics, BK Metalworks
- **Primary device**: Mobile web for discovery, often switches to desktop to subscribe
- **Setup behavior**: Wants to see what their booking page looks like ASAP — visual preview is the aha moment
- **Frustration**: Acuity's configuration vocabulary (appointment types, availability, calendars, resources) doesn't match how they describe their business
- **Core task**: Get a bookable offering live as fast as possible. Everything else is secondary.

## Known Vocabulary Mismatches

Acuity uses → ICP says:
- "Appointment types" → "services" or "offerings"
- "Availability" → "my hours" or "when I'm open"
- "Calendars" → "my schedule" or "my staff"
- "Resources" → "rooms," "spaces," "equipment"
- "Client Scheduling Page" → "my booking page" or "my link"

**Engineering implication**: Use service-provider language in all new UXT surfaces. Don't expose Acuity's internal model vocabulary to new trialers.

## Stub Notice

This file contains what was discussed in UXT sessions. The full ICP document (including demographics, behavioral data, and research backing) lives separately. This file should be updated when that document is finalized and shared.
