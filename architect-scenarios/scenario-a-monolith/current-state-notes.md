# ShopCore — Current State Notes

*Rough notes from the architecture team. Not a formal document. Updated sporadically.*

---

## What we know

ShopCore has been running since 2013. Originally built by a 4-person team in PHP/Laravel. Now maintained by ~25 developers across 3 teams. Nobody fully understands the whole system.

Teams:
- **Team Catalog** — products, categories, search, pricing rules
- **Team Orders** — checkout, order management, fulfilment status
- **Team Platform** — infrastructure, deployments, shared services, "everything else"

The three teams were created two years ago when we tried to split up ownership. It hasn't worked very well. Everyone still ends up touching the same database tables.

---

## The system

Single Laravel monolith. One MySQL database. ~480 tables. The schema has never been cleaned up — there are tables from features that were removed years ago still sitting there.

Frontend: mostly Blade templates with jQuery. Some newer parts use Vue 3 but it's inconsistent.

Background jobs: Laravel queues. Mix of Redis and database-backed queues. Nobody is sure which jobs use which.

Deployments: full app deploy every time. Takes ~110 minutes including tests. We deploy once a week on Wednesdays. Hotfixes go out manually.

Test suite: ~4200 tests. Takes 47 minutes on CI. Coverage is uneven — core checkout has reasonable coverage, catalog search has almost none.

---

## Known problem areas

**Payment module**
Integrated with three payment providers (Stripe, Klarna, MobilePay). The code is from 2015 and has been patched many times. Nobody wants to touch it. There was a production incident in 2022 that took 6 hours to resolve. No one who was there at the time still works here.

**Pricing engine**
~8000 lines of code in a single service class. Customer-specific pricing, campaign pricing, volume discounts, B2B vs B2C rules, VAT handling for 6 countries. There are unit tests but they don't cover all the edge cases. We discovered a bug in Danish B2B VAT calculations last year that had been there since 2018.

**Search**
Currently using MySQL full-text search. It's slow and the relevance is poor. We've talked about moving to Elasticsearch or Algolia for two years. Never happened.

**Order fulfilment integration**
Three warehouse integrations (two external, one in-house). Each was built separately by different people. One uses SOAP, one uses a REST API, one uses SFTP file drops. The SFTP one fails silently sometimes.

---

## What we'd like to do

The CTO said at the last all-hands that we need to "modernise the platform." There's no formal plan yet. Ideas that have been floated:

- Split into microservices (nobody agrees on where the boundaries should be)
- Event-driven architecture (suggested by one of the senior engineers, others are sceptical)
- "Just" replace the frontend with a React SPA (argued by the frontend team)
- Strangler fig pattern starting with search (suggested by Team Platform)
- Rewrite in a new language/framework (suggested by a new hire, not taken seriously)

No decision has been made. The CTO wants a recommendation before Q3.

---

## Constraints

- We cannot take the system down for migration. It runs 24/7, ~40k orders/day.
- The payment module is essentially frozen — any changes need sign-off from the CFO and legal.
- We have a contract with one of the warehouse providers that locks us in until end of 2026.
- The team doesn't have experience with Kubernetes or distributed systems at scale. We run on dedicated servers managed by Team Platform.
- Budget for the modernisation is unconfirmed. The CTO mentioned "significant investment" but nothing concrete.

---

## Open questions nobody has answered

- Do we have a single source of truth for product data? (probably not)
- What does the actual traffic pattern look like? (we have some Datadog metrics but nobody has analysed them)
- Which parts of the system are genuinely coupled vs just sharing a database?
- If we pulled search out first, what else would break?
- What does "done" look like for the modernisation? Nobody has defined success criteria.
