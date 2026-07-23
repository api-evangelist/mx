---
name: Connect a user and aggregate their financial data
description: >-
  Create an MX user, connect them to a financial institution (member),
  aggregate their data, then read the resulting accounts and transactions.
api: openapi/mx-platform-api-openapi.yml
operations:
  - createUser
  - listInstitutions
  - createMember
  - aggregateMember
  - readMemberStatus
  - listMemberAccounts
  - listTransactionsByMember
---

# Connect a user and aggregate their financial data

Use the MX Platform API to onboard an end user, connect them to their bank, and
pull cleansed accounts and transactions.

## Auth & conventions
- HTTP Basic auth over TLS: `client_id` = username, `api_key` = password (Base64
  in the `Authorization` header). Get both from the Client Dashboard
  (dashboard.mx.com). See `authentication/mx-authentication.yml`.
- Send `Accept: application/json` and `Accept-Version: v20250224` on every
  request. See `conventions/mx-conventions.yml`.
- Test against `https://int-api.mx.com` with the MX Bank / MXCU test
  institutions (`sandbox/mx-sandbox.yml`); production is `https://api.mx.com`.

## Steps
1. **Create the user** — `createUser`. Persist the returned user `guid`.
2. **Find the institution** — `listInstitutions` (paginate with `page` /
   `records_per_page`, up to 1000). Capture the `institution_code`.
3. **Create the member** — `createMember` under the user, supplying the
   `institution_code` and required credentials (or use an OAuth institution).
   Persist the member `guid`.
4. **Aggregate** — `aggregateMember` to fetch fresh data. A `202 Accepted`
   means a same-type job is already running — do not re-trigger.
5. **Poll status** — `readMemberStatus` until the member reaches a completed
   connection status (or subscribe to the `Aggregation` / `Initial Data Ready`
   webhooks instead of polling — `asyncapi/mx-webhooks.yml`).
6. **Read results** — `listMemberAccounts`, then `listTransactionsByMember`.

## Error handling
- `409 Conflict`: a conflicting aggregation is already running — wait.
- `400` with `error.type` starting `institution_`: institution is blocked/in
  maintenance — display `error.message` to the user (`errors/mx-problem-types.yml`).
- `404` immediately after a create is data-propagation lag — retry after ~500ms.
- `429`: back off and retry after the rate-limit window (`rate-limits/mx-rate-limits.yml`).
