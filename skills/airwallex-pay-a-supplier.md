---
name: airwallex-pay-a-supplier
description: Convert funds and send a transfer to an existing beneficiary, validating before creating.
api: openapi/airwallex-openapi.yml
operations:
- listBeneficiaries
- listCurrent
- createConversion
- transfers_validate
- createTransfer
- retrieveTransfer
generated: '2026-10-20'
method: generated
source: Grounded in openapi/airwallex-openapi.yml; every operationId verified verbatim in the spec.
---

# Pay a supplier, converting currency if needed

Convert funds and send a transfer to an existing beneficiary, validating before creating.

## Steps

1. `listBeneficiaries` — `GET /api/v1/beneficiaries` — Select the beneficiary (create one with the beneficiary-creation skill first).
2. `listCurrent` — `GET /api/v1/balances/current` — Check the source-currency balance.
3. `createConversion` — `POST /api/v1/fx/conversions/create` — Convert currency when the balance is in another currency (confirm the rate with the user).
4. `transfers_validate` — `POST /api/v1/transfers/validate` — Validate the transfer request.
5. `createTransfer` — `POST /api/v1/transfers/create` — Create the transfer only after explicit user approval.
6. `retrieveTransfer` — `GET /api/v1/transfers/{id}` — Track the transfer status.

## Rules that apply to every step
- **Auth**: exchange `x-client-id` + `x-api-key` via `authentication_login` (`POST /api/v1/authentication/login`) for a Bearer token valid 30 minutes; cache and reuse it (authentication/airwallex-authentication.yml). Through AgentOS MCP or the CLI, the connector handles OAuth instead.
- **Idempotency**: write operations take a body field `request_id` — a fresh UUIDv4 per logical operation, reused only when retrying that same operation; a replay returns `duplicate_request` (conventions/airwallex-conventions.yml, errors/airwallex-problem-types.yml).
- **Errors**: see errors/airwallex-problem-types.yml; on `429`, back off exponentially with jitter (rate-limits/airwallex-rate-limits.yml).
- **Sandbox first**: test against `https://api.sandbox.airwallex.com` before production `https://api.airwallex.com`.
- **Money out needs a human**: Airwallex's AgentOS guardrail is no money-out actions by default; ask for explicit confirmation before any create/confirm that moves funds.
