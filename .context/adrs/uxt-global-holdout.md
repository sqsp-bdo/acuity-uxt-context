# Acuity ADR: UXT Global Holdout Group

| | |
|---|---|
| **Author and Driver** | Brian Do |
| **Approver** | Jabari Bell |
| **Contributor(s)** | Shirley Lau |
| **Informed** | Acquisition, Activation |
| **Impacted Team(s)** | Acquisition, Activation |
| **Created** | April 17, 2026 |
| **Last Updated** | April 17, 2026 |
| **Theme** | Project |
| **Status** | Proposed |

---

### Problem Statement and Goal

The UX Transformation Team is running multiple concurrent experiments across Acquisition, Activation, and Retention squads in Q2 2026. Each experiment will have its own A/B holdout, but those per-experiment holdouts cannot answer the program-level question: **what is the cumulative impact of all UXT changes combined on Trial to Sub 14D (mobile web)?**

Without a persistent global holdout, we risk:

- Attributing cumulative gains (or losses) incorrectly to individual experiments
- Having no clean baseline at program end to validate whether the 90-day bet succeeded
- Contaminating measurement if users flow through multiple UXT experiments and are counted in multiple per-experiment control groups

The goal is a single, persistent holdout group that receives no UXT treatments for the duration of the Q2 2026 program, providing a clean baseline for program-level measurement.

---

### Proposal

Create a `uxt-global-holdout` layer in Statsig with the following configuration:

| Property | Value |
|---|---|
| **Experiment name** | `uxt-global-holdout` |
| **Identifier** | `ACUITY_BUSINESS_ID` |
| **Holdout size** | 10% |
| **Type** | Persistent (users assigned once; assignment does not change) |
| **Variants** | `holdout` (10%) / `eligible` (90%) |
| **Duration** | Until program measurement is complete |

**How it works**: All UXT experiments gate on holdout membership before applying any treatment. A business in the `holdout` variant is excluded from every UXT experiment and receives the baseline product experience throughout the program.

**Why `ACUITY_BUSINESS_ID` and not user ID**: Assignment at the business level ensures all users within a business see the same experience — avoiding split-brain scenarios where two users on the same account see different onboarding flows.

**Why 10%**: Large enough to be statistically meaningful for the primary KPI (Trial to Sub 14D) at expected traffic volumes; small enough to not meaningfully constrain experiment traffic allocations for individual squads.

**Why not per-experiment holdouts alone**: Per-experiment controls measure individual lift. They cannot detect whether two experiments with individually positive results are net-positive in combination, or whether gains are being double-counted across overlapping user journeys. The global holdout is the only mechanism that answers the program-level hypothesis.

**Statsig support**: Holdout groups are a native Statsig primitive — this is a well-supported pattern in the platform, not a custom implementation. Statsig guarantees persistent assignment via deterministic hashing on `ACUITY_BUSINESS_ID`; no database flag or application-level logic is needed to maintain consistency. Critically, Statsig evaluates holdout membership at the layer level, before evaluating any individual experiment. This means experiments automatically return their default (control) values for holdout businesses without each squad needing to write explicit holdout checks in application code. Configuring experiments within the same Statsig layer as `uxt-global-holdout` is sufficient.

**Alternative considered — no global holdout**: Rejected. The 90-day plan is structured as a program-level bet. Without a clean baseline at program end, we cannot validate the bet or learn from it rigorously.

---

### Decision

Implement a `uxt-global-holdout` experiment in Statsig using `ACUITY_BUSINESS_ID` as the assignment identifier, with 10% of businesses permanently assigned to holdout for the duration of the Q2 2026 UXT program. All UXT experiments must be configured within the same Statsig layer to ensure holdout businesses are automatically excluded from all treatments.

---

### Addendum

- [UXT 90-Day Plan](https://www.figma.com/design/71IQcpbC00rIwNB6QgpoY6/ux-transformation-90-days?node-id=19333-10221) — program context and success metrics
- [UXT Context Repo — Team Operations](https://github.com/sqsp-bdo/acuity-uxt-context/blob/master/.context/team/operations.md) — measurement approach and staged rollout policy
- Primary KPI: Trial to Sub 14D (mobile web)
