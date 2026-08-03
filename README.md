# Airwallex (airwallex)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Airwallex is a financial technology company that specializes in providing global payment solutions for businesses. Their platform enables companies to accept payments, manage multi-currency accounts, convert currencies at competitive rates, send cross-border payments, issue corporate cards, and embed financial services into their own products. Airwallex serves businesses in over 150 countries with APIs for payment acceptance, FX, accounts, transfers, and embedded finance.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/airwallex/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/airwallex/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

- Cross-Border Payments
- FinTech
- Foreign Exchange
- Payments
- Global
- Embedded Finance
- Multi-Currency

## Timestamps

- **Created:** 2025-02-17
- **Modified:** 2026-04-19

## APIs

### Airwallex Payment Acceptance API

The Airwallex Payment Acceptance API enables businesses to accept online payments globally. Supports credit and debit cards, local payment methods, and 3D Secure. Available as hosted checkout or embedded via Drop-in UI, Payment Elements, and mobile SDKs for iOS, Android, React Native, and Flutter.

- **Human URL:** [https://www.airwallex.com/docs/api#/Introduction](https://www.airwallex.com/docs/api#/Introduction)
- **Base URL:** `https://api.airwallex.com/api/v1`

#### Tags

- Payments
- Checkout
- Cards
- Online Payments

#### Properties

- [Documentation](https://www.airwallex.com/docs/api#/Introduction)
- [API Reference](https://www.airwallex.com/docs/api#/Payment_Acceptance)
- [Authentication](https://www.airwallex.com/docs/api#/Payment_Acceptance/Authentication)
- [SDK](https://github.com/airwallex/airwallex-payment-android)
- [SDK](https://github.com/airwallex/airwallex-payment-ios)
- [SDK](https://github.com/airwallex/airwallex-payment-react-native)
- [SDK](https://github.com/airwallex/airwallex-payment-flutter)
- [Postman Collection](collections/airwallex.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/airwallex.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Airwallex Global Accounts API

The Airwallex Global Accounts API enables businesses to create and manage multi-currency accounts. Supports account creation, balance management, account statements, and receiving funds in multiple currencies with local bank details.

- **Human URL:** [https://www.airwallex.com/docs/api#/Accounts](https://www.airwallex.com/docs/api#/Accounts)
- **Base URL:** `https://api.airwallex.com/api/v1`

#### Tags

- Accounts
- Multi-Currency
- Banking
- FX

#### Properties

- [Documentation](https://www.airwallex.com/docs/api#/Accounts)
- [API Reference](https://www.airwallex.com/docs/api#/Accounts)
- [Postman Collection](collections/airwallex.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/airwallex.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Airwallex Payouts API

The Airwallex Payouts API enables businesses to send cross-border payments to suppliers, contractors, and employees globally. Supports bank transfers to 150+ countries, bulk payouts, and beneficiary management.

- **Human URL:** [https://www.airwallex.com/docs/api#/Payouts](https://www.airwallex.com/docs/api#/Payouts)
- **Base URL:** `https://api.airwallex.com/api/v1`

#### Tags

- Payouts
- Cross-Border Payments
- Transfers
- International

#### Properties

- [Documentation](https://www.airwallex.com/docs/api#/Payouts)
- [API Reference](https://www.airwallex.com/docs/api#/Payouts)
- [SDK](https://github.com/airwallex/payouts-web-sdk)
- [Postman Collection](collections/airwallex.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/airwallex.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Airwallex FX API

The Airwallex FX API provides access to real-time foreign exchange rates and currency conversion. Supports spot conversions, rate quotes, and conversion history for 60+ currencies.

- **Human URL:** [https://www.airwallex.com/docs/api#/FX](https://www.airwallex.com/docs/api#/FX)
- **Base URL:** `https://api.airwallex.com/api/v1`

#### Tags

- Foreign Exchange
- Currency Conversion
- FX

#### Properties

- [Documentation](https://www.airwallex.com/docs/api#/FX)
- [API Reference](https://www.airwallex.com/docs/api#/FX)
- [Postman Collection](collections/airwallex.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/airwallex.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Airwallex Issuing API

The Airwallex Issuing API enables businesses to create and manage virtual and physical corporate cards for employee spending. Supports card issuance, spend controls, transaction management, and expense reporting.

- **Human URL:** [https://www.airwallex.com/docs/api#/Issuing](https://www.airwallex.com/docs/api#/Issuing)
- **Base URL:** `https://api.airwallex.com/api/v1`

#### Tags

- Cards
- Corporate Cards
- Issuing
- Expense Management

#### Properties

- [Documentation](https://www.airwallex.com/docs/api#/Issuing)
- [API Reference](https://www.airwallex.com/docs/api#/Issuing)
- [Postman Collection](collections/airwallex.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/airwallex.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Airwallex Platform API

The Airwallex Platform API enables businesses to embed financial services into their products. Supports merchant onboarding, sub-account management, platform payments, and split payouts for marketplace and SaaS platforms.

- **Human URL:** [https://www.airwallex.com/docs/api#/Platform](https://www.airwallex.com/docs/api#/Platform)
- **Base URL:** `https://api.airwallex.com/api/v1`

#### Tags

- Embedded Finance
- Platform
- Marketplace
- Split Payments

#### Properties

- [Documentation](https://www.airwallex.com/docs/api#/Platform)
- [API Reference](https://www.airwallex.com/docs/api#/Platform)
- [SDK](https://github.com/airwallex/platform-onboarding-sdk)
- [Postman Collection](collections/airwallex.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/airwallex.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/airwallex)
- [Portal](https://www.airwallex.com)
- [Getting Started](https://www.airwallex.com/docs/api)
- [Documentation](https://www.airwallex.com/docs/api#/Introduction)
- [Authentication](https://www.airwallex.com/docs/api#/Payment_Acceptance/Authentication)
- [Pricing](https://www.airwallex.com/pricing)
- [Terms of Service](https://www.airwallex.com/terms)
- [Privacy Policy](https://www.airwallex.com/privacy)
- [Blog](https://www.airwallex.com/blog)
- [GitHub Organization](https://github.com/airwallex)
- [C L I](https://github.com/airwallex/airwallex-cli)
- [SDK](https://github.com/airwallex/paymentacceptance-plugin-magento)
- [SDK](https://github.com/airwallex/airwallex-salesforce-commerce-cloud-cartridge)
- [Features](undefined)
- [Use Cases](undefined)
- [Integrations](undefined)
- [Spectral Rules](https://raw.githubusercontent.com/api-evangelist/airwallex/refs/heads/main/rules/airwallex-spectral-rules.yml)
- [Vocabulary](https://raw.githubusercontent.com/api-evangelist/airwallex/refs/heads/main/vocabulary/airwallex-vocabulary.yaml)
- [Integrations](https://www.airwallex.com/integrations)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
