---
name: airwallex-manage-cashflow
description: Aggregate balances and recent movements, check current FX rates and take an indicative quote.
api: openapi/airwallex-openapi.yml
operations:
- listCurrent
- listHistory
- listFinancialTransactions
- listGlobalAccount
- retrieveCurrent
- createQuote
- retrieveQuote
generated: '2026-10-20'
method: generated
source: Grounded in openapi/airwallex-openapi.yml; every operationId verified verbatim in the spec.
mirrors: skills/published/airwallex-agentos/manage-cashflow/SKILL.md
---

# Review multi-currency cashflow and FX

Aggregate balances and recent movements, check current FX rates and take an indicative quote.

## Steps

1. `listCurrent` — `GET /api/v1/balances/current` — Current balances per currency.
2. `listHistory` — `GET /api/v1/balances/history` — Balance history for the period.
3. `listFinancialTransactions` — `GET /api/v1/financial_transactions` — Underlying financial transactions.
4. `listGlobalAccount` — `GET /api/v1/global_accounts` — Global accounts that receive funds.
5. `retrieveCurrent` — `GET /api/v1/fx/rates/current` — Current FX rate for a currency pair.
6. `createQuote` — `POST /api/v1/fx/quotes/create` — Lock an indicative FX quote.
7. `retrieveQuote` — `GET /api/v1/fx/quotes/{quote_id}` — Re-read the quote before it expires.

## Rules that apply to every step
- **Auth**: exchange `x-client-id` + `x-api-key` via `authentication_login` (`POST /api/v1/authentication/login`) for a Bearer token valid 30 minutes; cache and reuse it (authentication/airwallex-authentication.yml). Through AgentOS MCP or the CLI, the connector handles OAuth instead.
- **Idempotency**: write operations take a body field `request_id` — a fresh UUIDv4 per logical operation, reused only when retrying that same operation; a replay returns `duplicate_request` (conventions/airwallex-conventions.yml, errors/airwallex-problem-types.yml).
- **Errors**: see errors/airwallex-problem-types.yml; on `429`, back off exponentially with jitter (rate-limits/airwallex-rate-limits.yml).
- **Sandbox first**: test against `https://api.sandbox.airwallex.com` before production `https://api.airwallex.com`.
- **Money out needs a human**: Airwallex's AgentOS guardrail is no money-out actions by default; ask for explicit confirmation before any create/confirm that moves funds.

Airwallex publishes its own version of this workflow, saved verbatim at `skills/published/airwallex-agentos/manage-cashflow/SKILL.md`; prefer it when running through the Airwallex CLI or AgentOS MCP.
