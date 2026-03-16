# Projects — Architects

You are working at the direction level — defining architecture that constrains future delivery rather than building features. These exercises use `/target-architecture`, `/technology-evaluation`, and `/platform-design`.

**Pick one scenario. One is enough for 90 minutes.**

Each scenario has a clear deliverable. Aim to have something shareable by the end of the session.

When `/conductor` asks for project type, choose **Direction**. This sets up the right folder structure and routes you to the direction-level workflows.

---

## Scenario A — Modernising a monolith

**Source material:**
- [architect-scenarios/scenario-a-monolith/cto-message.md](architect-scenarios/scenario-a-monolith/cto-message.md) — start here
- [architect-scenarios/scenario-a-monolith/current-state-notes.md](architect-scenarios/scenario-a-monolith/current-state-notes.md) — background detail

A 10-year-old e-commerce platform. Three teams work on it. Deployments take two hours. The test suite takes 45 minutes. Nobody touches the payment module. The CTO wants to start breaking it apart but has no clear picture of where to draw the boundaries or what to do first.

```
/conductor → /vision → /target-architecture
```

Give the agent the contents of `current-state-notes.md` as context when you start.

Work through:
- **Vision** — what does this platform look like in 3 years? What outcomes does the CTO actually want — faster deployments, team autonomy, lower risk? What is explicitly not the goal?
- **Target architecture** — given the vision, where should the system go structurally? Bounded contexts, team ownership, key decoupling points
- What are the critical decisions? Create 2–3 ADRs for the choices that would be expensive to reverse

**Deliverable:** a vision document with 3-year outcomes and guiding principles, a target architecture description with component boundaries and migration direction, and ADRs for the riskiest decisions.

**The interesting question:** does the vision change which decomposition path makes sense? And where are the hidden dependencies that would make any path painful?

---

## Scenario B — Internal developer platform

**Source material:** [architect-scenarios/scenario-b-platform/current-state-notes.md](architect-scenarios/scenario-b-platform/current-state-notes.md)

Five development teams at a scale-up are each maintaining their own CI/CD pipelines, deployment tooling, observability setup, and environment management. The teams spend 20% of their time on infrastructure that isn't their product. Leadership wants a platform team to take this over — but nobody has defined what the platform actually is or what it offers.

```
/conductor → /platform-design
```

Give the agent the contents of `current-state-notes.md` as context when you start `/platform-design`.

Work through:
- What capabilities does the platform provide? (deployment, environments, observability, secrets, onboarding)
- Who are the users and what is their self-service experience?
- What SLOs does the platform commit to?
- What is explicitly out of scope — what do product teams still own?

**Deliverable:** a platform definition with capabilities, self-service interfaces, SLOs, and a team topology description.

**The interesting question:** where does the platform end and the product team's responsibility begin?

---

## Scenario C — API strategy for a fragmented landscape

**Source material:** [architect-scenarios/scenario-c-api-strategy/current-state-notes.md](architect-scenarios/scenario-c-api-strategy/current-state-notes.md)

A mid-sized company has 14 internal APIs built by different teams over 8 years. Some are REST, some are RPC-style, some have no documentation, two have breaking changes pending. A new mobile app needs to consume six of them. The architecture team has been asked to define an API strategy before the mobile project starts.

```
/conductor → /technology-evaluation → /target-architecture
```

Give the agent the contents of `current-state-notes.md` as context when you start each workflow.

Work through:
- Evaluate the key strategic decision: API gateway vs BFF vs direct integration for the mobile app
- Define the target API landscape: what contracts should exist, how versioning should work, what governance is needed
- Identify the two or three decisions that need to be made before the mobile team can start

**Deliverable:** one EVAL-xxx artifact for the key decision plus a target architecture description covering the API layer.

**The interesting question:** what would you need to know about the existing APIs before you could commit to any of these options?
