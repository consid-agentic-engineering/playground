# DevOps at Velo — Current State Notes

*Compiled from Confluence, Slack threads, and a workshop we did in January. A mess, but honest.*

---

## The company

Velo is a SaaS company, ~120 employees, 5 product development teams. Series B funded. Growing fast. The engineering org went from 15 to 45 engineers in 18 months.

Teams:
- **Team Ride** — core product (ride booking, tracking)
- **Team Pay** — payments and invoicing
- **Team Fleet** — vehicle management and telematics
- **Team Insights** — analytics and reporting dashboard
- **Team Growth** — experiments, onboarding, referrals

Each team has 6–9 engineers. All teams run their own infrastructure. There is no platform team yet.

---

## Current infrastructure (per team, roughly)

Every team built their own setup when they joined or when they needed something. Nobody copied anyone else.

**Deployments:**
- Team Ride: GitHub Actions → ECS (Fargate). Works. Fragile YAML nobody wants to touch.
- Team Pay: CircleCI → ECS. Different from Ride. Pay team inherited it from a contractor.
- Team Fleet: GitHub Actions → EC2 (not containers). "We'll migrate eventually."
- Team Insights: Vercel for frontend, GitHub Actions → Lambda for backend jobs.
- Team Growth: Heroku. Yes, still Heroku. It works, they say.

**Environments:**
- Most teams have prod and staging. Some have dev environments, some don't.
- Spinning up a new environment takes anywhere from 2 hours (Insights) to 2 days (Fleet).
- There is no consistent naming convention for environments across teams.

**Observability:**
- Team Ride: Datadog (full APM). Expensive. €4,200/month.
- Team Pay: Datadog (logs only).
- Team Fleet: CloudWatch. Nobody looks at it proactively.
- Team Insights: Sentry for errors, nothing else.
- Team Growth: Heroku metrics + a custom dashboard in Retool.
- There is no cross-team alerting. If Ride has a problem that cascades into Pay, nobody knows until a customer complains.

**Secrets management:**
- Three teams use AWS Secrets Manager.
- One team has secrets in GitHub Actions secrets.
- One team has a `.env.production` file in a private S3 bucket. (Yes, really.)

**Onboarding a new engineer:**
- Average time to first deploy: 3.5 days (we measured this once).
- There is a Confluence page with setup instructions that was last updated 14 months ago.
- Most engineers get a buddy who walks them through it manually.

---

## Time spent on "platform work"

We did a rough survey in January. Engineers estimate:
- Team Ride: ~15% of time on infra/DevOps
- Team Pay: ~25% (they're dealing with PCI compliance overhead)
- Team Fleet: ~30% (EC2, lots of manual things)
- Team Insights: ~10% (Vercel does a lot for them)
- Team Growth: ~8% (Heroku does a lot for them, but they're worried about costs)

CTO's reaction: "We're paying for a platform team's worth of work spread across five teams, and getting inconsistency in return."

---

## What has been tried

- Six months ago, Team Ride's lead started writing shared Terraform modules. Two other teams adopted them partially. It stalled when he went on paternity leave.
- There was a proposal for a "golden path" document. It was written, debated, never adopted.
- Pay team asked DevOps consultants to help with PCI compliance last year. They produced a report. Most recommendations are unimplemented.

---

## What leadership wants

The CTO wants to announce a "Platform Team" at the next company all-hands (6 weeks away). He wants to be able to say what the platform team will own and what it will offer. He does not want to hire more than 2–3 people for it initially.

The VP Engineering is worried about team autonomy — she doesn't want a platform that becomes a bottleneck. "Teams should be able to deploy without filing a ticket."

There is no agreement yet on what the platform team should actually own.

---

## Open questions

- Should the platform team own production infrastructure or just provide tooling?
- What happens to the Heroku setup? Force migration or let it run?
- How do you handle the PCI compliance requirements for Pay without making everything PCI-scoped?
- What is the minimum viable platform that 2–3 people can actually maintain?
- How do you avoid the platform becoming a dependency that blocks product teams?
