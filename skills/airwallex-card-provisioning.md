---
name: airwallex-card-provisioning
description: Create (or reuse) a cardholder, issue a virtual or physical card with spend limits, and read back its
  limits.
api: openapi/airwallex-openapi.yml
operations:
- listCardholders
- createCardholder
- retrieveCardholder
- createCard
- listLimits
- cards_activate
generated: '2026-10-20'
method: generated
source: Grounded in openapi/airwallex-openapi.yml; every operationId verified verbatim in the spec.
mirrors: skills/published/airwallex-agentos/card-provisioning/SKILL.md
---

# Provision a corporate card

Create (or reuse) a cardholder, issue a virtual or physical card with spend limits, and read back its limits.

## Steps

1. `listCardholders` — `GET /api/v1/issuing/cardholders` — Look for an existing cardholder for this person.
2. `createCardholder` — `POST /api/v1/issuing/cardholders/create` — Create the cardholder if none exists.
3. `retrieveCardholder` — `GET /api/v1/issuing/cardholders/{id}` — Confirm the cardholder status before issuing.
4. `createCard` — `POST /api/v1/issuing/cards/create` — Issue the card with its authorization controls / spend limits.
5. `listLimits` — `GET /api/v1/issuing/cards/{id}/limits` — Read the remaining limits back to the user.
6. `cards_activate` — `POST /api/v1/issuing/cards/{id}/activate` — Physical cards only: activate on receipt.

## Rules that apply to every step
- **Auth**: exchange `x-client-id` + `x-api-key` via `authentication_login` (`POST /api/v1/authentication/login`) for a Bearer token valid 30 minutes; cache and reuse it (authentication/airwallex-authentication.yml). Through AgentOS MCP or the CLI, the connector handles OAuth instead.
- **Idempotency**: write operations take a body field `request_id` — a fresh UUIDv4 per logical operation, reused only when retrying that same operation; a replay returns `duplicate_request` (conventions/airwallex-conventions.yml, errors/airwallex-problem-types.yml).
- **Errors**: see errors/airwallex-problem-types.yml; on `429`, back off exponentially with jitter (rate-limits/airwallex-rate-limits.yml).
- **Sandbox first**: test against `https://api.sandbox.airwallex.com` before production `https://api.airwallex.com`.
- **Money out needs a human**: Airwallex's AgentOS guardrail is no money-out actions by default; ask for explicit confirmation before any create/confirm that moves funds.

Airwallex publishes its own version of this workflow, saved verbatim at `skills/published/airwallex-agentos/card-provisioning/SKILL.md`; prefer it when running through the Airwallex CLI or AgentOS MCP.
