# UX Transformation Team — Context Hub

This folder is the source of truth for the Acuity UX Transformation Team (UXT). Read it before writing code, reviewing designs, or making architectural decisions for any UXT-related work.

## What's here

### Team
| File | Read when... |
|------|-------------|
| [team/mandate.md](team/mandate.md) | You need to understand the mission, guiding principles, or hypotheses we're testing |
| [team/operations.md](team/operations.md) | You need to understand sprint cadence, measurement approach, or how we ship |
| [team/icps.md](team/icps.md) | You need to understand our target customers and their mental models |

### Active Projects
| File | Read when... |
|------|-------------|
| [projects/post-trial-onboarding.md](projects/post-trial-onboarding.md) | Working on the post-trial wizard / interstitial onboarding flow (Acquisition squad) |
| [projects/appt-type-creation.md](projects/appt-type-creation.md) | Working on appointment type creation UX improvements (Activation squad) |
| [projects/mobile-bridge.md](projects/mobile-bridge.md) | Working on the Frontsite experiment to drive mobile web users to the app |

### Strategy
| File | Read when... |
|------|-------------|
| [strategy/90-day-plan.md](strategy/90-day-plan.md) | Understanding the overall Q2 2026 plan: 6 initiatives, guiding policy, success metrics, deferred scope |
| [strategy/mobile-strategy.md](strategy/mobile-strategy.md) | Making decisions about mobile web vs. mobile app surface placement |

### Design
| File | Read when... |
|------|-------------|
| [design/post-trial-wizard-flow.md](design/post-trial-wizard-flow.md) | Implementing any screen in the post-trial onboarding wizard |

### Reference
| File | Read when... |
|------|-------------|
| [reference/metrics-glossary.md](reference/metrics-glossary.md) | You encounter an unfamiliar metric (TTS, LTT, LTS, Sub 8D) or need baselines |

### History
| File | Read when... |
|------|-------------|
| [history/onboarding-wizard-learnings.md](history/onboarding-wizard-learnings.md) | Making decisions about onboarding flow design — 10 validated learnings from prior experiments |

### Meetings
| File | Read when... |
|------|-------------|
| [meetings/2026-04-09-design-direction-update.md](meetings/2026-04-09-design-direction-update.md) | Latest wizard direction: hybrid concept (Concept A fast-path + Concept B stepped creation) |
| [meetings/2026-03-30-concept-review.md](meetings/2026-03-30-concept-review.md) | Why Concept 2 was chosen over Concept 1 for the wizard |
| [meetings/2026-03-kickoff.md](meetings/2026-03-kickoff.md) | Team structure, Q2 focus, and measurement approach |

---

## Key facts every engineer should know

- **Primary KPI**: Trial to Sub 14D (mobile web)
- **Target surface**: Mobile web first. Desktop and app are out of scope until mobile proves out.
- **Modality scope**: Appointment-based (1:1) only for Phase 1. Classes deferred.
- **Design principle**: Collect minimum viable inputs to reach "open for business." Defer everything else.
- **Language rule**: Use service-provider vocabulary. Never expose Acuity's internal model (appointment types → services, availability → hours, resources → rooms/spaces).
- **Measurement**: Persistent holdout group (5–10%) + staged rollouts. Not A/B tests by default.
- **The aha moment**: Users seeing their own branded scheduling page — not completing configuration. Get them there fast.
- **Active Figma (wizard)**: [UXT / Onboarding](https://www.figma.com/design/okhVkzSEB2CLfob8eUABcm/%E2%9C%BC-UXT---Onboarding)
- **Active Figma (strategy)**: [UX Transformation 90-Days](https://www.figma.com/design/71IQcpbC00rIwNB6QgpoY6/ux-transformation-90-days?node-id=19333-10221)
