---
name: airwallex-beneficiary-creation
description: Fetch the per-country bank-detail schema, validate supplier bank details against it, then create and
  confirm the beneficiary. Mirrors Airwallex's published beneficiary-creation skill.
api: openapi/airwallex-openapi.yml
operations:
- beneficiaries_schema
- beneficiaries_validate
- listBeneficiaries
- createBeneficiary
- retrieveBeneficiary
generated: '2026-10-20'
method: generated
source: Grounded in openapi/airwallex-openapi.yml; every operationId verified verbatim in the spec.
mirrors: skills/published/airwallex-agentos/beneficiary-creation/SKILL.md
---

# Create a payout beneficiary

Fetch the per-country bank-detail schema, validate supplier bank details against it, then create and confirm the beneficiary. Mirrors Airwallex's published beneficiary-creation skill.

## Steps

1. `beneficiaries_schema` — `POST /api/v1/beneficiaries/schema` — Get the required fields for the bank country, currency and transfer method.
2. `beneficiaries_validate` — `POST /api/v1/beneficiaries/validate` — Validate the extracted details without creating anything; fix every reported field.
3. `listBeneficiaries` — `GET /api/v1/beneficiaries` — Check for an existing beneficiary with the same account to avoid duplicates.
4. `createBeneficiary` — `POST /api/v1/beneficiaries/create` — Create the beneficiary with a fresh `request_id`.
5. `retrieveBeneficiary` — `GET /api/v1/beneficiaries/{id}` — Read it back and confirm the stored details with the user.

## Rules that apply to every step
- **Auth**: exchange `x-client-id` + `x-api-key` via `authentication_login` (`POST /api/v1/authentication/login`) for a Bearer token valid 30 minutes; cache and reuse it (authentication/airwallex-authentication.yml). Through AgentOS MCP or the CLI, the connector handles OAuth instead.
- **Idempotency**: write operations take a body field `request_id` — a fresh UUIDv4 per logical operation, reused only when retrying that same operation; a replay returns `duplicate_request` (conventions/airwallex-conventions.yml, errors/airwallex-problem-types.yml).
- **Errors**: see errors/airwallex-problem-types.yml; on `429`, back off exponentially with jitter (rate-limits/airwallex-rate-limits.yml).
- **Sandbox first**: test against `https://api.sandbox.airwallex.com` before production `https://api.airwallex.com`.
- **Money out needs a human**: Airwallex's AgentOS guardrail is no money-out actions by default; ask for explicit confirmation before any create/confirm that moves funds.

Airwallex publishes its own version of this workflow, saved verbatim at `skills/published/airwallex-agentos/beneficiary-creation/SKILL.md`; prefer it when running through the Airwallex CLI or AgentOS MCP.
