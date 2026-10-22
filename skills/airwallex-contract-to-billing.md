---
name: airwallex-contract-to-billing
description: Match billing details from a contract or quote against existing customers, products and prices, then
  create an invoice or subscription.
api: openapi/airwallex-openapi.yml
operations:
- listBillingCustomers
- createBillingCustomer
- listProducts
- listPrices
- createPrice
- createInvoice
- invoices_addLineItems
- invoices_finalize
- createSubscription
generated: '2026-10-20'
method: generated
source: Grounded in openapi/airwallex-openapi.yml; every operationId verified verbatim in the spec.
mirrors: skills/published/airwallex-agentos/contract-to-billing/SKILL.md
---

# Turn a contract into invoices and subscriptions

Match billing details from a contract or quote against existing customers, products and prices, then create an invoice or subscription.

## Steps

1. `listBillingCustomers` — `GET /api/v1/billing/billing_customers` — Find the customer; create with createBillingCustomer only if absent.
2. `createBillingCustomer` — `POST /api/v1/billing/billing_customers/create` — Create the billing customer.
3. `listProducts` — `GET /api/v1/billing/products` — Match line items to existing products.
4. `listPrices` — `GET /api/v1/billing/prices` — Match amounts and cadence to existing prices; create with createPrice only when nothing matches.
5. `createPrice` — `POST /api/v1/billing/prices/create` — Create a missing price.
6. `createInvoice` — `POST /api/v1/billing/invoices/create` — One-off charges: create a draft invoice.
7. `invoices_addLineItems` — `POST /api/v1/billing/invoices/{id}/add_line_items` — Add the contract line items to the draft.
8. `invoices_finalize` — `POST /api/v1/billing/invoices/{id}/finalize` — Finalize only after the user approves the draft.
9. `createSubscription` — `POST /api/v1/billing/subscriptions/create` — Recurring terms: create a subscription instead of an invoice.

## Rules that apply to every step
- **Auth**: exchange `x-client-id` + `x-api-key` via `authentication_login` (`POST /api/v1/authentication/login`) for a Bearer token valid 30 minutes; cache and reuse it (authentication/airwallex-authentication.yml). Through AgentOS MCP or the CLI, the connector handles OAuth instead.
- **Idempotency**: write operations take a body field `request_id` — a fresh UUIDv4 per logical operation, reused only when retrying that same operation; a replay returns `duplicate_request` (conventions/airwallex-conventions.yml, errors/airwallex-problem-types.yml).
- **Errors**: see errors/airwallex-problem-types.yml; on `429`, back off exponentially with jitter (rate-limits/airwallex-rate-limits.yml).
- **Sandbox first**: test against `https://api.sandbox.airwallex.com` before production `https://api.airwallex.com`.
- **Money out needs a human**: Airwallex's AgentOS guardrail is no money-out actions by default; ask for explicit confirmation before any create/confirm that moves funds.

Airwallex publishes its own version of this workflow, saved verbatim at `skills/published/airwallex-agentos/contract-to-billing/SKILL.md`; prefer it when running through the Airwallex CLI or AgentOS MCP.
