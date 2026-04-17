# UXT Hypotheses: Evidence and Working Notes

Tracks evidence for and against each of the 5 team hypotheses. Engineers should read this before making assumptions about user motivations or mental models. Come back with evidence (flows, clips, metrics) — not just opinions.

---

## H1 — The first booking is the "aha" moment

**Hypothesis**: It's "real" for prospects when they experience that first booked appointment, even if self-booked. Getting users to this moment fast drives conversion.

**Status**: Under pressure — research findings complicate this.

**Claire Crinion (UXR)**:
> In recent trial research, none of the trialers talked about the first booking as the moment where "things clicked" for them about deciding to subscribe. Common themes for the click/aha moment were: seeing their CSP as a customer would see it; realizing Acuity has a specific feature that would be useful (intake forms, payments, reminders); and seeing the power and complexity behind Acuity — realizing it was more than just a calendar, but a whole business system.

> Overall, the decision to subscribe was not driven by a single aha/lightbulb moment, but rather a **satisficing mindset** — Acuity being the first option that meets their criteria threshold of "good enough" based on functionality/price/access. Participants who subscribed went into trial with a **convergent mindset** (seeing if Acuity checked their boxes) rather than a divergent mindset (exploring options).

**Caveat**: This research reflects people who *did* subscribe with the product as it currently exists. There is a selection bias toward users who value a powerful tool over ease of use. The general population of trialers may behave differently.

**Implication for the wizard**: Getting users to a live scheduling page (seeing their own CSP) may be more important than getting them to a first booking. The "aha" may be the preview, not the booking. Screen 5 of the wizard — the live booking page preview — is doing the right thing. Don't over-index on "book a test appointment" at the expense of the preview experience.

---

## H2 — Vocabulary vs. mental models

**Hypothesis**: Acuity's concepts ("appointment types," "availability," "calendars," "classes") don't match how sellers describe their work.

**Status**: Validated. Rich vocabulary data from classes UXR.

**Claire Crinion (UXR) — language used by class-based businesses**:

*Single, individual class sessions:*
- "Workshop" — preferred over "class" for one-time events (Amber, Lisa, Michelle)
- "One-off" / "One-time" / "One-up" — most common organic term across industries
- "Pop-up" — special event by visiting instructor (Karis)
- "A la carte" — single class outside normal progression (Amber)
- "Drop-in" — universal in pole dance industry for a single class without commitment (Jessie)

*Class series / courses (the overarching concept):*
- "Cohort" — used to signal multi-week commitment (Lisa)
- "Season" — year-long commitment framing (Sonja)
- "Series" — 4-week or ongoing set (Lisa, Jessie, Cyril)
- "Curriculum" — structured learning path with progression (Alejandra, Amber)
- "Program" / "Package" / "Block" — 6-week commitment or grouped classes (Alejandra, Marios)

*Individual parts within a longer class:*
- "Sessions" or "Classes" — pieces of the whole
- "Weeks" — time-based sequential reference
- "Class times" / "Class meetings" — individual days within a month-long class (Janine G)

**Claire's conclusion on "Classes" as a term**:
> "Class" is probably the wrong umbrella term. Customers described offerings like *photography lessons for one person* as a "class" based on the learning element, even though that's structurally an appointment. The key distinction between appointments and classes is scheduling model (customer-matched time vs. set time offered by the business) — but "class" is confusing because it's used for individual sessions, the course, and sessions within a course. "Event" may be a better umbrella term since it captures the defining characteristic: *it's at a set time*.

> Pattern emerging: Fitness businesses tend toward individual sessions/drop-ins. Arts/academic education businesses tend toward courses/cohorts/series. Acuity's current class offering is probably best suited for one-off workshops — not either of these patterns well.

**Navigation implication**:
> "It took me a couple of visits to understand the panel on the left. To understand scheduling page, appointment types, vs calendars. It took me stumbling around in there to figure out what each section represented." — Janine B, Trial Success Research

**Implication for the wizard**: Use service-provider vocabulary throughout. Never expose "appointment types," "calendars," or "availability." The language rule in the wizard ("services," "hours," "spaces") is validated by this research.

---

## H3 — Not opinionated enough in setup

**Hypothesis**: We force users to design their own system instead of offering clear, opinionated starting points by modality and vertical.

**Status**: Supported by pattern evidence.

**Claire Crinion (UXR)**:
> There is a consistent pattern across all Acuity UXR: customers who had an example of a similar business's Acuity setup (from a friend or a business they patronize personally) had a much easier time onboarding than those who didn't. Vertical-specific tutorial content also gives evidence of the need for someone to tell you how to design your system.

**Implication for the wizard**: Fixture-based appointment type suggestions (Screen 3) directly addresses this. The hypothesis is that showing users a pre-configured example for their vertical reduces setup friction. The UXR pattern supports this bet.

---

## H4 — Haven't defined minimum viable inputs to go live

**Hypothesis**: We ask for too much configuration before users see value. We haven't agreed on minimum viable inputs to reach "open for business."

**Status**: No direct evidence yet. The wizard is the test.

**Current definition of minimum viable inputs** (as designed in the wizard):
1. Business type (vertical)
2. Service type (appointments)
3. At least one appointment type (name, duration, price)
4. Business hours

Everything else (branding, payments, intake forms, staff, resources) is deferred.

---

## H5 — Configurability over simplicity

**Hypothesis**: Years of additive iteration exposed complexity up front rather than progressively. Users succeed in spite of onboarding, not because of it.

**Status**: No direct counter-evidence. The wizard is the test.

**Prompt for engineers**: If we started from zero and designed for "guided by default" on mobile, what would we strip away or hide until after first booking? Every screen in the wizard should be evaluated against this question.
