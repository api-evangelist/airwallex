---
name: airwallex-accept-a-payment
description: Create, confirm and capture a payment intent, then refund it if needed.
api: openapi/airwallex-openapi.yml
operations:
- createPaymentIntent
- paymentIntents_confirm
- retrievePaymentIntent
- capture
- createRefund
- retrieveRefund
generated: '2026-10-20'
method: generated
source: Grounded in openapi/airwallex-openapi.yml; every operationId verified verbatim in the spec.
---

# Accept a card payment and refund it

Create, confirm and capture a payment intent, then refund it if needed.

## Steps

1. `createPaymentIntent` — `POST /api/v1/pa/payment_intents/create` — Create the intent with amount, currency, merchant_order_id and a fresh `request_id`.
2. `paymentIntents_confirm` — `POST /api/v1/pa/payment_intents/{id}/confirm` — Confirm with the payment method (server-side), or hand the client_secret to a hosted/embedded element.
3. `retrievePaymentIntent` — `GET /api/v1/pa/payment_intents/{id}` — Poll status (or rely on webhooks, asyncapi/airwallex-webhooks.yml); declines are explained in errors/airwallex-decline-codes.yml.
4. `capture` — `POST /api/v1/pa/payment_intents/{id}/capture` — Capture when the intent was authorized for manual capture.
5. `createRefund` — `POST /api/v1/pa/refunds/create` — Refund all or part of a succeeded intent.
6. `retrieveRefund` — `GET /api/v1/pa/refunds/{id}` — Track the refund to completion.

## Rules that apply to every step
- **Auth**: exchange `x-client-id` + `x-api-key` via `authentication_login` (`POST /api/v1/authentication/login`) for a Bearer token valid 30 minutes; cache and reuse it (authentication/airwallex-authentication.yml). Through AgentOS MCP or the CLI, the connector handles OAuth instead.
- **Idempotency**: write operations take a body field `request_id` — a fresh UUIDv4 per logical operation, reused only when retrying that same operation; a replay returns `duplicate_request` (conventions/airwallex-conventions.yml, errors/airwallex-problem-types.yml).
- **Errors**: see errors/airwallex-problem-types.yml; on `429`, back off exponentially with jitter (rate-limits/airwallex-rate-limits.yml).
- **Sandbox first**: test against `https://api.sandbox.airwallex.com` before production `https://api.airwallex.com`.
- **Money out needs a human**: Airwallex's AgentOS guardrail is no money-out actions by default; ask for explicit confirmation before any create/confirm that moves funds.
