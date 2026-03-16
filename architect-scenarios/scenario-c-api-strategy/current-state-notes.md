# API Landscape at Nordia Group — Current State Notes

*Pulled together from various sources. Not authoritative. Contains guesses.*

---

## The company

Nordia Group is a mid-sized financial services company. ~800 employees. They run three main business lines: personal banking, business banking, and insurance. Each business line has its own IT department with its own development teams. There is a central IT department that owns shared infrastructure.

A new mobile app is being planned — a unified "Nordia" app for personal customers that will show account balances, insurance policies, and support chat. It needs to talk to systems from all three business lines.

The mobile project starts in 10 weeks.

---

## The APIs (what we know)

We did an inventory in February. This is what we found. There are probably more.

| # | Name | Owner | Style | Docs | Version | Notes |
|---|---|---|---|---|---|---|
| 1 | Customer Profile API | Central IT | REST | OpenAPI (outdated) | v2 | Used by everything. ~200 consumers. |
| 2 | Account Balance API | Personal Banking | REST | Confluence page | v1 | Works fine. Rate limited to 100 req/min per client. |
| 3 | Transaction History API | Personal Banking | REST | None | v1 | Returns different date formats depending on account type. |
| 4 | Card Management API | Personal Banking | SOAP | WSDL (2016) | — | Nobody wants to touch it. Requires IP whitelisting. |
| 5 | Business Account API | Business Banking | REST | OpenAPI | v3 | Clean. Not relevant for the personal app. |
| 6 | Insurance Policy API | Insurance | REST | Postman collection | v1 | Returns 200 for errors with error details in body. |
| 7 | Claims API | Insurance | REST | None | v1 | Only used by one internal tool. May be decommissioned. |
| 8 | Support Ticket API | Central IT | gRPC | Proto files (incomplete) | v1 | Brand new. Only the support team uses it. |
| 9 | Notification API | Central IT | REST | OpenAPI | v2 | Sends SMS/email/push. Push is broken for iOS since last month. |
| 10 | Authentication API | Central IT | REST + OAuth2 | OpenAPI | v2 | SSO for internal tools. Mobile will need a separate OAuth flow. |
| 11 | Fraud Detection API | Central IT | REST | None | v1 | Async — submits a job, poll for result. Average 800ms. |
| 12 | Document Storage API | Central IT | REST | Swagger (v2 format) | v1 | Returns presigned S3 URLs. Credentials expire after 15 minutes. |
| 13 | Product Catalogue API | Marketing IT | REST | None | v1 | Returns pricing and product descriptions. Updated manually. |
| 14 | Analytics Ingestion API | Data Team | REST | README in GitLab | v1 | Write-only. For sending events. |

**APIs the mobile app definitely needs:** 1, 2, 3, 6, 8 or 9 (TBD), 10

**APIs the mobile app probably needs:** 11, 12

**APIs the mobile app might need:** 13

---

## Known problems

**No consistency**
Authentication varies: some APIs use the central OAuth2 server, some use API keys, Card Management uses mutual TLS with IP whitelisting. The mobile app will need to handle all of these or something needs to standardise them.

**Error handling**
At least three different error response formats across the APIs. Insurance Policy API returns 200 for errors. Transaction History API returns 500 for "no transactions found."

**Rate limits**
Account Balance API is rate limited. We don't know if the limits will hold under mobile traffic. We don't know the rate limits for most other APIs.

**The SOAP problem**
Card Management API is SOAP from 2016. The mobile app team has said they won't consume it directly. Someone needs to wrap it.

**Breaking changes pending**
Customer Profile API v3 is in development. The team said they'll deprecate v2 "sometime this year." No migration guide exists yet. Transaction History API has a known breaking change being discussed — the date format inconsistency is going to be fixed, which will break current consumers.

**The gRPC/REST mismatch**
Support Ticket API is gRPC. The mobile team has never worked with gRPC. They've asked whether it can be exposed as REST.

---

## What the mobile team wants

They want a single endpoint to talk to. They don't want to know about SOAP, gRPC, IP whitelisting, or three different OAuth flows. They want consistent error formats. They want it ready in 10 weeks.

They suggested: "Can we just have a BFF?"

---

## What central IT wants

They don't want to build and maintain a BFF for the mobile team. They have two teams and 40 open tickets already. They suggested: "Just use our APIs directly, they work fine."

---

## Open questions

- Who owns the integration layer for the mobile app — mobile team, central IT, or a new team?
- Do we need an API gateway, a BFF, or both?
- What do we do about Card Management API? Wrap it, or block that feature for mobile v1?
- How do we handle the pending breaking changes before mobile launch?
- What does API governance look like going forward — who approves new APIs, who enforces standards?
- Is 10 weeks realistic given the current state?
