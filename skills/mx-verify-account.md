---
name: Verify a member's account and read account numbers
description: >-
  Run account verification on a connected member and read the verified account
  and routing numbers for funding/ACH use cases.
api: openapi/mx-platform-api-openapi.yml
operations:
  - createMember
  - verifyMember
  - readMemberStatus
  - listMemberAccounts
  - listAccountNumbersByMember
---

# Verify a member's account and read account numbers

Use MX verification (instant account verification) to confirm account/routing
numbers for a connected member.

## Auth & conventions
- HTTP Basic auth (`client_id` / `api_key`); send `Accept-Version: v20250224`.
  See `authentication/mx-authentication.yml`.
- Verification is a premium job; the institution must support it (check the
  `supported_products` array, which includes `account_verification`).

## Steps
1. **Ensure a connected member** — from the connect flow, or `createMember` with
   a verification-capable institution.
2. **Trigger verification** — `verifyMember`. A `202 Accepted` means a
   verification (or conflicting job) is already running.
3. **Poll status** — `readMemberStatus` until verification completes, or listen
   for the `Verification` webhook (`asyncapi/mx-webhooks.yml`).
4. **List accounts** — `listMemberAccounts` to get the verified account `guid`s.
5. **Read account numbers** — `listAccountNumbersByMember` to retrieve account
   and routing numbers for the verified accounts.

## Error handling
- `400` `institution_prevent_verification_error`: verification is blocked at
  this institution — surface `error.message`.
- `409 Conflict`: another job (e.g. a standard aggregation) is running — wait
  before retrying. See `errors/mx-problem-types.yml`.
