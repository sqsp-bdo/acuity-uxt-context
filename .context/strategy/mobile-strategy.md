# Mobile Strategy: Bridge Approach

## TL;DR

Mobile web and mobile app serve fundamentally different roles. The right strategy uses both.

- **Mobile web** = high-volume, zero-commitment entry point. Optimized for discovery, value demonstration, and routing motivated prospects to the app.
- **Mobile app** = conversion and activation surface. Where prospects who've shown commitment complete setup and reach "open for business."

A Frontsite bridge experiment is already in delivery testing this hypothesis.

## Platform Data (January 2026)

| Platform | Top-of-Funnel | Trials | Trial Conversion | Subs | TTS |
|----------|--------------|--------|-----------------|------|-----|
| Desktop | 252,916 landings | 18,765 | ~7.4% | 11,081 | **11.9%** |
| Mobile Web | 320,315 landings | 24,241 | ~7.6% | 2,524 | **6.90%** |
| Mobile App | 18,388 downloads | 8,688 | ~54.6% | 855 | **8.25%** |

Mobile app trialers also outperform mobile web on every setup action despite being mostly webview-based:
- Customizes CSP: App 2,559 vs. Web 1,941
- Creates Appt Type: Web 2,771 vs. App 3,006
- Updates Availability: App 4,008 vs. Web 2,728

## Mobile Web's Two Problems

The blended 6.90% TTS conflates two distinct issues:
1. **UX/product problem**: Warm, direct-traffic users with intent failing on a clunky desktop-compressed experience
2. **Traffic quality problem**: Paid social / viral links driving high-volume, low-intent traffic

Direct traffic is the #1 source to mobile web — these are prospects who already know Acuity and still aren't converting. This points to a real product experience problem, not just traffic mix.

## Mobile Web's Role in the Funnel

1. **Discovery** — Captures prospect interest at massive scale with zero commitment (320K landings/month vs. 18K app downloads). This is its core strength.
2. **Value Demonstration** — Show enough product (speed of setup, simplicity of availability) that prospects believe Acuity is worth installing. Goal is not full onboarding completion; it's building enough confidence.
3. **Bridge Connection** — Route motivated prospects toward the app, where conversion and setup completion are stronger.

**Implication**: Don't try to build a full-fidelity product experience on mobile web competing with desktop and app. Invest in making mobile web excellent at its actual job: catching interest, demonstrating value quickly, handing off to the app.

## Platform Feature Placement

### Web Only
- Extended configuration (intake forms, integrations, comms templates, packages)
- Decisions with downstream client consequences (pricing structures, legal, integration settings)
- Power users / multi-staff / multi-location

### Both Web and App
Belongs on both if:
1. Needed during initial setup AND ongoing operations
2. Has a meaningful lightweight mobile version
3. Absence on either platform creates a real gap

Examples: Create/manage appointment types, share booking page, view CSP, connect payment processor

### App Only / App-First
1. **On-the-go management**: Quick actions between clients (calendar check, mark arrivals, process payments, client comms)
2. **Mobile-native payments**: Tap to pay, saved cards, POS-adjacent features
3. **In-person client interactions**: Showing a screen, taking a signature, processing a transaction

## Active Hypothesis Tests

- **H1**: Mobile web's conversion problem has two problems (UX friction + traffic quality) — need TTS by traffic source to confirm
- **H2**: Mobile app outperformance is real, not selection bias — cohort analysis on LTV/churn pending
- **H3**: App discovery is already an organic acquisition mechanic — trialers finding app on their own during trial
- **H4**: Bridge strategy can extend organic behavior — **Frontsite experiment in delivery**

## Note for Engineers

When building for mobile web, always ask:
- Is this a "full onboarding completion" feature or a "value demonstration" feature?
- Would showing this to a low-intent prospect increase or decrease their likelihood to install the app?
- Does this belong on web only, both, or app only? (See placement criteria above)
