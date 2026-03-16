# Request for Proposal — Shipment Tracking Modernisation

**Issued by:** TransNord A/S
**Date:** March 2026
**Response deadline:** April 14, 2026
**Contact:** procurement@transnord.dk

---

## 1. About TransNord

TransNord A/S is a Danish logistics company founded in 1987. We operate regional distribution across Denmark, southern Sweden, and northern Germany. We employ approximately 350 people across our head office in Aarhus and three regional hubs (Copenhagen, Malmö, Hamburg).

In 2025 we handled 2.1 million shipments. Approximately 60% are B2B customers; 40% are B2C (primarily e-commerce fulfilment).

---

## 2. Background and motivation

Our current shipment tracking system was implemented in 2014 as part of a larger ERP project. The tracking module was custom-built by an external vendor who is no longer operating. The system runs on-premise at our Aarhus data centre.

Over the past three years we have identified the following problems:

**Customer experience**
B2C customers expect real-time tracking updates via SMS and email. We currently send manual notifications from our operations team — typically one update when a shipment is picked up and one when it is delivered. Customers frequently contact our support line for status updates. Support volume related to shipment status represents 34% of all inbound support contacts.

**Operational visibility**
Our operations team cannot see the live location of shipments in transit. We rely on drivers calling in at scheduled points. When a shipment is delayed, we often find out from the customer rather than from our own system.

**Data gaps**
Approximately 8% of shipments have incomplete tracking records. These gaps are caused by a combination of driver error, connectivity issues at some hubs, and integration failures between our tracking system and our warehouse management system.

**Integration limitations**
Our current system has no API. Integration with our ERP (SAP S/4HANA, implemented 2021) is done via a nightly batch export. Real-time data exchange is not possible with the current architecture.

---

## 3. Scope of this RFP

We are seeking proposals for a modernised shipment tracking solution. The solution must:

- Provide real-time tracking visibility for operations staff
- Enable automated customer notifications (SMS, email, and optionally push)
- Expose an API for integration with our SAP S/4HANA ERP
- Be accessible to B2B customers via a web portal or API
- Reduce shipment data gaps to below 1%
- Be GDPR compliant (shipment data includes recipient names, addresses, and phone numbers)

The solution may be a commercial product, a custom-built system, or a hybrid. We are open to SaaS solutions if they meet our data residency requirements (EU only).

**Out of scope for this RFP:**
- Replacement of our ERP or warehouse management system
- Driver mobile applications (we have an existing driver app we wish to retain)
- Route optimisation or planning tooling

---

## 4. Technical context

| System | Details |
|---|---|
| ERP | SAP S/4HANA (cloud, implemented 2021) |
| Warehouse management | Custom system, runs on-premise, REST API available |
| Driver app | Third-party (FleetComplete), limited API access |
| Current tracking system | Custom PHP application, on-premise, no API |
| Infrastructure | Primarily on-premise; open to cloud migration for new systems |
| Data residency | EU only |

Our IT department has 6 staff. Two have experience with SAP integrations. The team has limited capacity for large internal development projects.

---

## 5. Evaluation criteria

Proposals will be evaluated on:

| Criterion | Weight |
|---|---|
| Functional fit to requirements | 30% |
| Integration approach (SAP, warehouse system, driver app) | 25% |
| Total cost of ownership (3 years) | 20% |
| Implementation approach and timeline | 15% |
| References from similar logistics implementations | 10% |

---

## 6. Proposal requirements

Please provide:

1. **Executive summary** — your understanding of our situation and your proposed approach
2. **Solution description** — architecture overview, key components, hosting model
3. **Integration plan** — how you will integrate with SAP, our warehouse system, and our driver app
4. **Implementation plan** — phases, milestones, and timeline
5. **Team** — key roles and relevant experience
6. **Investment** — total cost of ownership for 3 years, broken down by implementation, licences/SaaS fees, and ongoing support
7. **References** — at least two references from logistics customers with similar scope

---

## 7. Constraints and notes

- Our operations director, Mette Sørensen, is leading this evaluation. She has approval authority up to DKK 2M. Larger investments require board sign-off.
- Our IT manager, Rasmus Lund, must approve the technical architecture. He has concerns about cloud dependency and vendor lock-in.
- We have had one failed IT project in the last five years (a mobile app for B2C customers that was abandoned after 8 months). There is internal scepticism about large IT projects.
- We expect implementation to begin no later than September 2026.
- We are evaluating three vendors in parallel.

---

*Questions regarding this RFP should be directed to procurement@transnord.dk by March 31, 2026.*
