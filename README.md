# Airwallex

Airwallex is a financial technology company that specializes in providing global payment solutions for businesses. Their platform enables companies to accept payments, manage multi-currency accounts, convert currencies at competitive rates, send cross-border payments, issue corporate cards, and embed financial services into their own products. Airwallex serves businesses in over 150 countries with APIs for payment acceptance, FX, accounts, transfers, and embedded finance.

- **Portal:** https://www.airwallex.com
- **Getting Started:** https://www.airwallex.com/docs/api
- **Documentation:** https://www.airwallex.com/docs/api#/Introduction
- **Authentication:** https://www.airwallex.com/docs/api#/Payment_Acceptance/Authentication
- **Pricing:** https://www.airwallex.com/pricing
- **Terms of Service:** https://www.airwallex.com/terms
- **Privacy Policy:** https://www.airwallex.com/privacy
- **Blog:** https://www.airwallex.com/blog
- **GitHub Organization:** https://github.com/airwallex

## APIs

### Airwallex Payment Acceptance API

The Airwallex Payment Acceptance API enables businesses to accept online payments globally. Supports credit and debit cards, local payment methods, and 3D Secure. Available as hosted checkout or embedded via Drop-in UI, Payment Elements, and mobile SDKs for iOS, Android, React Native, and Flutter.

- **Documentation:** https://www.airwallex.com/docs/api#/Introduction
- **API Reference:** https://www.airwallex.com/docs/api#/Payment_Acceptance
- **Authentication:** https://www.airwallex.com/docs/api#/Payment_Acceptance/Authentication
- **Android SDK:** https://github.com/airwallex/airwallex-payment-android
- **iOS SDK:** https://github.com/airwallex/airwallex-payment-ios
- **React Native SDK:** https://github.com/airwallex/airwallex-payment-react-native
- **Flutter SDK:** https://github.com/airwallex/airwallex-payment-flutter

**Tags:** Payments, Checkout, Cards, Online Payments

### Airwallex Global Accounts API

The Airwallex Global Accounts API enables businesses to create and manage multi-currency accounts. Supports account creation, balance management, account statements, and receiving funds in multiple currencies with local bank details.

- **Documentation:** https://www.airwallex.com/docs/api#/Accounts
- **API Reference:** https://www.airwallex.com/docs/api#/Accounts

**Tags:** Accounts, Multi-Currency, Banking, FX

### Airwallex Payouts API

The Airwallex Payouts API enables businesses to send cross-border payments to suppliers, contractors, and employees globally. Supports bank transfers to 150+ countries, bulk payouts, and beneficiary management.

- **Documentation:** https://www.airwallex.com/docs/api#/Payouts
- **API Reference:** https://www.airwallex.com/docs/api#/Payouts
- **Payouts Web SDK:** https://github.com/airwallex/payouts-web-sdk

**Tags:** Payouts, Cross-Border Payments, Transfers, International

### Airwallex FX API

The Airwallex FX API provides access to real-time foreign exchange rates and currency conversion. Supports spot conversions, rate quotes, and conversion history for 60+ currencies.

- **Documentation:** https://www.airwallex.com/docs/api#/FX
- **API Reference:** https://www.airwallex.com/docs/api#/FX

**Tags:** Foreign Exchange, Currency Conversion, FX

### Airwallex Issuing API

The Airwallex Issuing API enables businesses to create and manage virtual and physical corporate cards for employee spending. Supports card issuance, spend controls, transaction management, and expense reporting.

- **Documentation:** https://www.airwallex.com/docs/api#/Issuing
- **API Reference:** https://www.airwallex.com/docs/api#/Issuing

**Tags:** Cards, Corporate Cards, Issuing, Expense Management

### Airwallex Platform API

The Airwallex Platform API enables businesses to embed financial services into their products. Supports merchant onboarding, sub-account management, platform payments, and split payouts for marketplace and SaaS platforms.

- **Documentation:** https://www.airwallex.com/docs/api#/Platform
- **API Reference:** https://www.airwallex.com/docs/api#/Platform
- **Platform Onboarding SDK:** https://github.com/airwallex/platform-onboarding-sdk

**Tags:** Embedded Finance, Platform, Marketplace, Split Payments

## Features

| Feature | Description |
|---|---|
| Global Payment Acceptance | Accept payments in 180+ currencies via cards and local payment methods. |
| Multi-Currency Accounts | Hold, manage, and convert funds in 60+ currencies. |
| Cross-Border Payouts | Send payments to 150+ countries with competitive FX rates. |
| FX Conversion | Real-time currency conversion at competitive exchange rates. |
| Corporate Card Issuing | Issue virtual and physical Visa cards for employee spending. |
| Embedded Finance | Embed Airwallex financial services into your own platform. |
| Mobile SDKs | iOS, Android, React Native, and Flutter SDKs for in-app payments. |
| Webhooks | Real-time event notifications for payment status changes. |
| Risk Management | Built-in fraud detection and risk scoring via the Airwallex Risk SDK. |

## Use Cases

| Use Case | Description |
|---|---|
| E-Commerce Checkout | Accept global payments on e-commerce stores and marketplaces. |
| Cross-Border B2B Payments | Pay international suppliers and contractors efficiently. |
| Employee Expense Management | Issue cards and track employee spending globally. |
| Multi-Currency Treasury | Manage treasury operations across multiple currencies. |
| Marketplace Split Payments | Collect and distribute payments to marketplace sellers. |
| SaaS Platform Monetization | Embed payment processing into SaaS platforms. |
| Freelancer Payouts | Pay remote workers and freelancers in their local currencies. |

## Integrations

| Integration | Description |
|---|---|
| Magento | Airwallex payment plugin for Magento/Adobe Commerce stores. |
| Salesforce Commerce Cloud | Airwallex payment cartridge for Salesforce Commerce Cloud. |
| WooCommerce | Payment gateway plugin for WooCommerce stores. |
| Xero | Sync Airwallex transactions with Xero accounting software. |
| QuickBooks | Accounting integration for Airwallex transactions. |
| NetSuite | ERP integration for Airwallex payment data. |

## Tooling

### Spectral Rules

Airwallex API governance rules for linting and validating OpenAPI specifications.

- **Rules:** [airwallex-spectral-rules.yml](rules/airwallex-spectral-rules.yml)

### Naftiko Capabilities

Workflow-oriented capability definitions for AI agent and MCP tool integration.

- **Shared API:** [airwallex-api.yaml](capabilities/shared/airwallex-api.yaml)
- **Payments Management Workflow:** [payments-management.yaml](capabilities/payments-management.yaml)

### Vocabulary

Domain vocabulary for Airwallex resources, actions, workflows, and personas.

- **Vocabulary:** [airwallex-vocabulary.yaml](vocabulary/airwallex-vocabulary.yaml)

## Schemas

JSON Schema definitions for Airwallex domain objects.

| Schema | Description |
|---|---|
| [airwallex-payment-intent-schema.json](json-schema/airwallex-payment-intent-schema.json) | Payment intent for collecting customer payment. |
| [airwallex-transfer-schema.json](json-schema/airwallex-transfer-schema.json) | Cross-border transfer to a beneficiary account. |
| [airwallex-account-schema.json](json-schema/airwallex-account-schema.json) | Global multi-currency business account. |
| [airwallex-fx-quote-schema.json](json-schema/airwallex-fx-quote-schema.json) | Foreign exchange rate quote. |

### JSON Structure

JSON Structure (json-structure.org) definitions for Airwallex schemas.

| Structure | |
|---|---|
| [airwallex-payment-intent-structure.json](json-structure/airwallex-payment-intent-structure.json) | |
| [airwallex-transfer-structure.json](json-structure/airwallex-transfer-structure.json) | |
| [airwallex-account-structure.json](json-structure/airwallex-account-structure.json) | |
| [airwallex-fx-quote-structure.json](json-structure/airwallex-fx-quote-structure.json) | |

### JSON-LD Context

- [airwallex-context.jsonld](json-ld/airwallex-context.jsonld)

## Examples

| Example | |
|---|---|
| [airwallex-payment-intent-example.json](examples/airwallex-payment-intent-example.json) | |
| [airwallex-transfer-example.json](examples/airwallex-transfer-example.json) | |
| [airwallex-account-example.json](examples/airwallex-account-example.json) | |
| [airwallex-fx-quote-example.json](examples/airwallex-fx-quote-example.json) | |

---

*Maintained by [API Evangelist](https://apievangelist.com)*
