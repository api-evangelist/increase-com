# Increase (increase-com)

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

Increase is a bank-grade payments and financial infrastructure platform that exposes a single REST API for moving and holding money in the United States - ACH transfers, real-time payments (RTP and FedNow), domestic and international wires, physical and mailed checks, deposit accounts and account numbers, card issuing and card acquiring, ledgering and bookkeeping, KYC/KYB entities, and lockboxes. Increase connects directly to the Federal Reserve and card networks through partner banks, and every state change is delivered as an Event over HTTP webhooks. The API is documented with a public OpenAPI 3.1 spec (`https://api.increase.com/openapi.json`) and Stainless-generated SDKs for Python, TypeScript, Java, Kotlin, Go, Ruby, PHP, and C#. Base URL `https://api.increase.com` with a sandbox at `https://sandbox.increase.com`.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/increase-com/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/increase-com/refs/heads/main/apis.yml)

## Tags

- Payments
- Banking
- Financial Infrastructure
- ACH
- Wire Transfers
- Real-Time Payments
- Cards
- Fintech

## Timestamps

- **Created:** 2026-07-02
- **Modified:** 2026-07-02

## Authentication

All requests are authenticated with a Bearer API key (`Authorization: Bearer YOUR_API_KEY`); keys are scoped to an environment (production vs sandbox). OAuth is supported for platform / Increase-for-platforms integrations. Mutating requests accept an `Idempotency-Key` header so retries never duplicate money movement. List endpoints use cursor-based pagination (1-100 per page).

## APIs

### Increase Accounts API

Create, retrieve, update, list, and close deposit Accounts held at Increase's partner banks, and read real-time available and current balances. The root container for all money movement, tied to an Entity and a Program.

- **Human URL:** [https://increase.com/documentation/api/accounts](https://increase.com/documentation/api/accounts)
- **Base URL:** `https://api.increase.com`

#### Tags

- Accounts
- Balances
- Banking

#### Properties

- [Documentation](https://increase.com/documentation/api/overview)
- [API Reference](https://increase.com/documentation/api/accounts)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Increase Account Numbers API

Generate and manage Account Numbers (routing + account number pairs) that can receive ACH, wire, and check deposits, configure inbound controls, and register External Accounts and look up Routing Numbers for counterparties.

- **Human URL:** [https://increase.com/documentation/api/account-numbers](https://increase.com/documentation/api/account-numbers)
- **Base URL:** `https://api.increase.com`

#### Tags

- Account Numbers
- Routing
- External Accounts

#### Properties

- [API Reference](https://increase.com/documentation/api/account-numbers)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Increase Cards API

Issue and manage virtual and physical commercial Cards - create, update, list, retrieve sensitive card details via a secure iframe, set PINs, and order Physical Cards fulfilled by Increase's print vendors.

- **Human URL:** [https://increase.com/documentation/api/cards](https://increase.com/documentation/api/cards)
- **Base URL:** `https://api.increase.com`

#### Tags

- Cards
- Card Issuing
- Physical Cards

#### Properties

- [API Reference](https://increase.com/documentation/api/cards)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Increase Card Payments API

Follow the full lifecycle of a card authorization and settlement via Card Payments and Card Purchase Supplements, approve or decline authorizations in real time through Real-Time Decisions, and manage Card Disputes.

- **Human URL:** [https://increase.com/documentation/api/card-payments](https://increase.com/documentation/api/card-payments)
- **Base URL:** `https://api.increase.com`

#### Tags

- Card Payments
- Authorizations
- Real-Time Decisions

#### Properties

- [API Reference](https://increase.com/documentation/api/card-payments)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Increase ACH Transfers API

Originate credit and debit ACH Transfers over the FedACH network, approve or cancel pending transfers, handle Inbound ACH Transfers with returns and notifications of change, and validate routing details with ACH Prenotifications.

- **Human URL:** [https://increase.com/documentation/api/ach-transfers](https://increase.com/documentation/api/ach-transfers)
- **Base URL:** `https://api.increase.com`

#### Tags

- ACH
- Transfers
- FedACH

#### Properties

- [API Reference](https://increase.com/documentation/api/ach-transfers)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Increase Wire Transfers API

Send domestic Fedwire Wire Transfers, approve or cancel them, receive and reverse Inbound Wire Transfers, and request funds from counterparties with Wire Drawdown Requests.

- **Human URL:** [https://increase.com/documentation/api/wire-transfers](https://increase.com/documentation/api/wire-transfers)
- **Base URL:** `https://api.increase.com`

#### Tags

- Wires
- Fedwire
- Drawdowns

#### Properties

- [API Reference](https://increase.com/documentation/api/wire-transfers)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Increase Real-Time Payments API

Send and receive instant, 24/7 payments over The Clearing House RTP network via Real-Time Payments Transfers and Inbound Real-Time Payments Transfers, with irrevocable, immediately-settled credit transfers.

- **Human URL:** [https://increase.com/documentation/api/real-time-payments-transfers](https://increase.com/documentation/api/real-time-payments-transfers)
- **Base URL:** `https://api.increase.com`

#### Tags

- Real-Time Payments
- RTP
- FedNow

#### Properties

- [API Reference](https://increase.com/documentation/api/real-time-payments-transfers)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Increase Checks API

Print and mail physical Check Transfers (or send them electronically), place stop payments, deposit images of received checks with Check Deposits, and process Inbound Check Deposits with decline and return controls.

- **Human URL:** [https://increase.com/documentation/api/check-transfers](https://increase.com/documentation/api/check-transfers)
- **Base URL:** `https://api.increase.com`

#### Tags

- Checks
- Check Deposits
- Lockbox

#### Properties

- [API Reference](https://increase.com/documentation/api/check-transfers)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Increase Transactions API

Read the immutable ledger of settled Transactions, in-flight Pending Transactions (holds), and Declined Transactions, each with a typed source object explaining exactly what moved money in an Account.

- **Human URL:** [https://increase.com/documentation/api/transactions](https://increase.com/documentation/api/transactions)
- **Base URL:** `https://api.increase.com`

#### Tags

- Transactions
- Ledger
- Pending

#### Properties

- [API Reference](https://increase.com/documentation/api/transactions)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Increase Entities API

Onboard the people and businesses that own Accounts - create, update, archive, and list Entities (natural persons, corporations, trusts), manage Beneficial Owners, and attach Supplemental Documents for KYC/KYB compliance.

- **Human URL:** [https://increase.com/documentation/api/entities](https://increase.com/documentation/api/entities)
- **Base URL:** `https://api.increase.com`

#### Tags

- Entities
- KYC
- KYB

#### Properties

- [API Reference](https://increase.com/documentation/api/entities)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Increase Events and Webhooks API

Subscribe to state changes across every Increase resource. Every change emits an Event; Event Subscriptions deliver those Events to your HTTPS endpoint as signed (Standard Webhooks HMAC-SHA256) webhooks, and the List Events API lets you poll or backfill up to 30 days of history.

- **Human URL:** [https://increase.com/documentation/webhooks](https://increase.com/documentation/webhooks)
- **Base URL:** `https://api.increase.com`

#### Tags

- Events
- Webhooks
- Notifications

#### Properties

- [Documentation](https://increase.com/documentation/webhooks)
- [API Reference](https://increase.com/documentation/api/events)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Increase Bookkeeping API

Build a double-entry sub-ledger on top of Increase money movement. Create Bookkeeping Accounts, post transactionally-applied Bookkeeping Entry Sets, read individual Bookkeeping Entries, and reconcile balances against real Transactions.

- **Human URL:** [https://increase.com/documentation/api/bookkeeping-accounts](https://increase.com/documentation/api/bookkeeping-accounts)
- **Base URL:** `https://api.increase.com`

#### Tags

- Bookkeeping
- Ledgering
- Accounting

#### Properties

- [API Reference](https://increase.com/documentation/api/bookkeeping-accounts)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Increase Card Profiles and Digital Wallets API

Control the appearance and provisioning of issued cards - Digital Card Profiles (Apple Pay / Google Pay branding), Physical Card Profiles (print artwork), and Digital Wallet Tokens representing cards added to mobile wallets.

- **Human URL:** [https://increase.com/documentation/api/digital-card-profiles](https://increase.com/documentation/api/digital-card-profiles)
- **Base URL:** `https://api.increase.com`

#### Tags

- Digital Wallets
- Card Profiles
- Tokenization

#### Properties

- [API Reference](https://increase.com/documentation/api/digital-card-profiles)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Increase Lockboxes API

Receive paper checks and mail at a physical Lockbox address tied to an Account. Create and manage Lockboxes, and retrieve scanned Inbound Mail Items for automated receivables processing.

- **Human URL:** [https://increase.com/documentation/api/lockboxes](https://increase.com/documentation/api/lockboxes)
- **Base URL:** `https://api.increase.com`

#### Tags

- Lockboxes
- Mail
- Receivables

#### Properties

- [API Reference](https://increase.com/documentation/api/lockboxes)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Increase Simulations API

Drive the sandbox deterministically. Simulation endpoints let you trigger inbound ACH/wire/RTP/check activity, settle or decline card authorizations, advance transfer states, and generate statements so you can test every code path without real money.

- **Human URL:** [https://increase.com/documentation/api/simulations-account-transfers](https://increase.com/documentation/api/simulations-account-transfers)
- **Base URL:** `https://api.increase.com`

#### Tags

- Simulations
- Sandbox
- Testing

#### Properties

- [API Reference](https://increase.com/documentation/api/simulations-account-transfers)
- [OpenAPI](openapi/increase-com-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/increase-com.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/increase-com.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/Increase)
- [LinkedIn](https://www.linkedin.com/company/increase)
- [Website](https://increase.com)
- [Documentation](https://increase.com/documentation)
- [Plans](plans/increase-com-plans-pricing.yml)
- [Rate Limits](rate-limits/increase-com-rate-limits.yml)
- [Fin Ops](finops/increase-com-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
