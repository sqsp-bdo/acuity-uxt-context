# Metrics Glossary

Key metrics used by the UX Transformation Team. Reference this when reading data, writing instrumentation, or interpreting experiment results.

## Funnel Metrics

### LTT — Landing to Trial
Percentage of Frontsite landings that result in a trial start.

| Platform | Jan 2026 |
|----------|----------|
| Desktop | 2.84% |
| Mobile Web | 2.53% |
| Mobile App | ~54.6% (downloads → trials) |

Note: App download-to-trial rate is not directly comparable to landing-to-trial (downloading an app is a more deliberate action).

---

### TTS — Trial to Subscription
Percentage of trials that convert to a paid subscription. The most-watched metric for UXT.

| Platform | Jan 2026 |
|----------|----------|
| Desktop | 11.9% (17.2% in separate cut) |
| Mobile Web | 6.90% (7.52% in separate cut) |
| Mobile App | 8.25% |

**Desktop is the benchmark.** Mobile web at 6.90% vs. desktop at 11.9% is the gap UXT exists to close.

---

### LTS — Landing to Subscription
Full-funnel conversion: Frontsite landing → paid subscription. The primary north star metric for UXT (called "Standalone Landing to Sub 8D").

| Platform | Jan 2026 |
|----------|----------|
| Desktop | 0.49% |
| Mobile Web | 0.19% |

---

### Sub 8D / Sub 14D
Subscription within 8 or 14 days of trial creation. "TTS 14D" is the primary project-level KPI for both the post-trial onboarding and appointment type creation projects.

---

## Setup / Activation Metrics

### "Open for Business"
A user has at least one bookable offering live AND has received a first booking. The UXT team's definition of activation success. Measured separately for appointment and class modalities.

### Key Setup Actions (tracked in Amplitude)
In order of significance for predicting subscription:

1. **Customize CSP** (Customer Scheduling Page) — Most predictive of conversion. The visual preview "aha moment."
2. **Create Appointment Type** — Core setup task
3. **Update Availability** — Often the highest-friction setup action
4. **Add Payment Processor** — Indicates serious intent

Jan 2026 unique trialers completing each action:

| Action | Mobile Web | Mobile App |
|--------|-----------|------------|
| Customize CSP | 1,941 | **2,559** |
| Create Appt Type | **2,771** | 3,006 |
| Update Availability | 2,728 | **4,008** |

App outperforms web on CSP and availability despite both running as webviews.

---

## Engagement / Health Metrics

### Time to First Booked Appointment
How long from trial creation to the first non-test appointment booked (by admin or client). Secondary north star metric. Exact qualifier (median vs. average, window) still being finalized by team.

### 1-Day Churn
Percentage of trials that churn within 24 hours. Counter metric — do not harm. Historical baseline: ~4.7–15% depending on test conditions.

### GPV / AOV
Gross Payment Volume / Average Order Value. Used for downstream cohort quality analysis (validating that app users aren't just higher-converting but also more valuable long-term).

---

## Traffic Sources

For mobile web, traffic sources that matter:
- **Direct** — #1 source; presumably high-intent users who already know Acuity. Still converting poorly, suggesting a real product experience problem.
- **Paid social** — High volume, low intent; drags down blended TTS
- **Branded search** — High intent
- **Organic search** — Mixed intent

Note: There's an open question about whether some "direct" traffic is misattributed from LLM referrals or certain link types. Under active investigation by PA.

---

## Experiment Infrastructure

### Holdout Group
5–10% of new trials permanently excluded from all UXT releases. Used to measure cumulative program impact over time. Never exposed to new UXT changes.

### Treatment Group
90–95% of new trials. Receives UXT releases via staged rollouts.

### Staged Rollout
New release ships to 10–20% of treatment group first. Guardrail metrics watched for 1 week. If clean, ramps to 100% of treatment group.
