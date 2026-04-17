# AI Infrastructure Sync: Jeremy (Principal Engineer)
**Date**: April 17, 2026
**Attendees**: Brian Do, Jeremy (Principal Engineer, Squarespace — Blueprint/Beacon AI infrastructure)

---

## Key Decision

### Do not use `sqsp/ai-content-generator`
Guidance from Jeremy: `ai-content-generator` has bad practices. Acuity should **not** integrate with it.

**Implication**: Acuity will build and own its own AI service in AWS rather than integrating with Squarespace's shared GCP-based service.

---

## Context

`sqsp/ai-content-generator` was evaluated as a potential shortcut for Phase 2 of the post-signup wizard (AI-generated appointment type suggestions on Screen 3). It offered:
- SSE streaming
- Rate limiting + caching (bucket4j + hazelcast)
- Structured JSON output
- OpenAI → Anthropic fallback
- Existing production deployment on GCP

However, the cross-DC latency (Acuity on AWS, service on GCP) was estimated at ~500ms — potentially acceptable — but Jeremy's guidance to avoid the service makes this moot.

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
