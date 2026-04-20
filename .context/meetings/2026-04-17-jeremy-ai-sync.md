# AI Infrastructure Sync: Jeremy Johnstone (Principal Engineer)
**Date**: April 17, 2026
**Attendees**: Brian Do, Jeremy Johnstone

---

## Key Decision

### Do not use `sqsp/ai-content-generator`
Guidance from Jeremy: `ai-content-generator` follows bad practices — he wants to avoid using it. Acuity should **not** integrate with it.

### Acuity-owned service is the better fit overall
Beyond latency concerns (cross-DC AWS↔GCP), Jeremy noted that an Acuity-owned solution can better serve Acuity's specific needs — for example, authenticating without requiring `memberAccountId` and `websiteId`, which are Squarespace-platform concepts that don't map cleanly to Acuity's auth model.

**Implication**: Acuity will build and own its own AI service in AWS rather than integrating with Squarespace's shared GCP-based service. This gives Acuity control over auth patterns, latency, and service quality.

---

## Context

`sqsp/ai-content-generator` was evaluated as a potential shortcut for Phase 2 of the post-signup wizard (AI-generated appointment type suggestions on Screen 3). It offered:
- SSE streaming
- Rate limiting + caching (bucket4j + hazelcast)
- Structured JSON output
- OpenAI → Anthropic fallback
- Existing production deployment on GCP

However, Jeremy's guidance to avoid the service makes this moot — both on code quality grounds and because an Acuity-owned service sidesteps the cross-DC latency and auth mismatch issues entirely.

---

## Architecture Implications

The Onboarding Intelligence Service (Go microservice, AWS, Acuity-owned) remains the correct Phase 2 architecture. Acuity must build its own equivalents of:
- LLM API key management (Vault or AWS Secrets Manager)
- Rate limiting
- Response caching
- Fallback logic (AI down → fixture templates)
- SSE streaming
- Structured output schema for appointment type cards

The JWT auth pattern (monolith issues short-lived token → MFE calls service directly) validated by Jon Tascher on April 16 remains unchanged.
