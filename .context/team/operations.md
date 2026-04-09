# UX Transformation Team — Operations

## Cadence

- **2-week sprints** — every sprint must ship at least one testable change, prototype, or experiment
- **Weekly UXT sync** — both squad leads + PD/PA/UXR: next problem, designs in progress, sprint delivery, learnings vs. north star
- **Day-to-day** stays in normal squad standups; cross-squad dependencies surface in the weekly sync

## North Star Metrics

### Primary
**Standalone Landing to Sub 8D** — Landing on Frontsite to Subscription within 8 days.
- Chosen because LTT and TTS are easy to manipulate with UX changes; LTS is the full-funnel signal.

### Secondary
1. **Unique users with ≥1 booked appointment** (non-test, ideally within 1 month of subscription)
2. **Time to first booked appointment** (median, admin or client-booked)

### Counter Metrics (do not harm)
- Churn
- Trial volume
- Successful setup completion on desktop continuation flows

## Measurement Approach

We **do not default to A/B tests**. We use a persistent holdout group as the measurement backbone.

### Setup
- **5–10% of new trials** → persistent holdout (never sees any UXT releases)
- **90–95% of new trials** → treatment group (receives UXT releases over time)

### Rollout pattern for each release
1. Stage to 10–20% of treatment group
2. Watch guardrail metrics (churn, trial volume, desktop continuation)
3. If clean, ramp to 100% of treatment group

### Decision Framework

| Risk | Uncertainty | Method |
|------|-------------|--------|
| High | High | A/B test (full experiment) |
| High | Low | Staged rollout with guardrail metrics |
| Low | High | Qual validation + staged rollout |
| Low | Low | Ship it, measure in holdout group |

### Example rollout sequence
- Phase 0: Establish holdout + 2–3 week baseline
- Phase 1: Ship Appointment Type Creation redesign (staged → 100% treatment)
- Phase 2: Ship Post-Trial Onboarding (staged → 100% treatment)
- Ongoing: Holdout persists; cumulative lift measured continuously

## Decision Filters

We prioritize work that:
- Reduces time to first booking
- Increases clarity and guidance
- Is mobile-web first
- Is modality-specific (appointment vs. class)

## Sprint Velocity Bar

Bias toward: fast + opinionated changes + qual validation + holdout measurement.
Reserve full A/B tests for: highest-risk, highest-uncertainty bets only.
