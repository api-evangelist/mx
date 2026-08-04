# MX (mx)

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

MX Technologies is a privately held financial data platform headquartered in Lehi, Utah, operating as a B2B data aggregator and open-finance infrastructure provider — not a chartered bank or credit union. MX connects consumer and business accounts across tens of thousands of financial institutions and fintechs, then cleanses, categorizes, and enhances that data so banks and fintechs can build verification, aggregation, and personal-finance experiences. It is one of the major US open-finance aggregators alongside Plaid, Finicity, and Akoya.

Unlike most US banks, MX runs a real, self-documented developer surface with downloadable OpenAPI 3.0 specifications published at docs.mx.com.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/mx/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/mx/refs/heads/main/apis.yml)

## Tags

- Financial Services
- Banking
- United States
- Open Finance
- Data Aggregation
- FDX
- Fintech
- Financial Data

## Timestamps

- **Created:** 2026-07-23
- **Modified:** 2026-07-23

## APIs

### MX Platform API

The MX Platform API aggregates and enhances financial data, connecting apps and websites to tens of thousands of financial institutions. It covers users, members, accounts, transactions, categorization, insights, verification, and widgets. OpenAPI 3.0 (version v20250224), HTTP Basic authentication.

- **Human URL:** [https://docs.mx.com/api-reference/platform-api/reference/mx-platform-api](https://docs.mx.com/api-reference/platform-api/reference/mx-platform-api)
- **Base URL:** `https://api.mx.com`

#### Tags

- Financial Data
- Aggregation
- Data Enhancement
- Verification

#### Properties

- [OpenAPI](openapi/mx-platform-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.mx.com/api-reference/platform-api/overview/architecture-and-security)
- [API Reference](https://docs.mx.com/api-reference/platform-api/reference/mx-platform-api)
- [Authentication](https://docs.mx.com/resources/oauth-guide)

### MX Consent Management API

API for embedding the MX consent management dashboard into a customer-facing experience, letting consumers grant, modify, and revoke access to their financial data. OpenAPI 3.0, version 4.

- **Human URL:** [https://docs.mx.com/api-reference/consent-management](https://docs.mx.com/api-reference/consent-management)

#### Tags

- Consent
- Open Finance
- Data Sharing

#### Properties

- [OpenAPI](openapi/mx-consent-management-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [API Reference](https://docs.mx.com/api-reference/consent-management)

### MX Data Access

Data Access is MX's open-finance API platform for sharing an institution's financial data and accessing other institutions' data using FDX and OAuth standards, with tokenized, consumer-permissioned access that consumers can grant, modify, and revoke at any time.

- **Human URL:** [https://docs.mx.com/products/data/data-access](https://docs.mx.com/products/data/data-access)

#### Tags

- Open Finance
- FDX
- OAuth
- Data Access

#### Properties

- [Documentation](https://docs.mx.com/products/data/data-access)

## Open Finance Posture

MX documents FDX participation directly: its Data Access product "enables you to share your institution's financial data and access the data of other institutions using FDX and OAuth standards." No CFPB Section 1033 statement was found on the public site as of the review date. MX is an aggregator, so much US bank data flows through MX rather than through those banks' own first-party APIs.

## Common Properties

- [Website](https://www.mx.com/)
- [Developer Portal](https://developer.mx.com/)
- [Documentation](https://docs.mx.com/)
- [GitHub Organization](https://github.com/mxenabled)
- [LinkedIn](https://www.linkedin.com/company/425337)
- [Blog](https://www.mx.com/blog/)
- [Terms of Service](https://www.mx.com/terms/)
- [Privacy Policy](https://www.mx.com/privacy/)
- [Support](https://support.mx.com/)
- [Status Page](https://status.mx.com/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
