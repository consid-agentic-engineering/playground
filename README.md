# Åben Legestue — Agentic Engineering

Welcome. This is the home page for the open playground sessions on agentic engineering.

## What this is

A hands-on session where you bring a project and work with AI agents using structured workflows. The goal is to experience what directed agentic delivery feels like in practice — not to watch demos, but to build something yourself.

We use **The Conductor Model** as the framework and either **OpenSpec** or **GSD** as the delivery method. Your choice.

Two session formats are available depending on how much introduction the group needs.

---

## Format A — Detailed introduction (2 × 3 hours)

For groups new to the Conductor Model. Spreads the content across two sessions — more depth in Session 1, more hands-on time in Session 2.

### Session 1 — Introduction and first steps

| Time | What happens |
|---|---|
| 0:00–0:30 | Introduction: The Conductor Model, the problem it solves, the three domains |
| 0:30–0:50 | The documentation model: lean vs governed, OpenSpec vs GSD |
| 0:50–1:20 | Live demo: `/conductor` → `/kickstart` → first change — with explanation |
| 1:20–2:30 | Hands-on — first session, reach `/kickstart` and start first change |
| 2:30–3:00 | Share back: what did you set up, what surprised you, open questions |

### Session 2 — Deliver, review, close

| Time | What happens |
|---|---|
| 0:00–0:15 | Recap from Session 1 — orient with `/conductor` |
| 0:15–2:30 | Hands-on — continue delivery, `/review`, `/version-close` |
| 2:30–3:00 | Share back + feedback + retrospective |

Between sessions, participants should have their project set up with a charter, architecture description, and at least one change in progress.

> **Don't have a project idea?** Pick one of these — each can be kicked off in under 10 minutes:
> - **Fruit explorer** — display fruit nutrition data using the [FruityVice API](https://www.fruityvice.com) (no key needed)
> - **Weather widget** — show current conditions for any city using the [Open-Meteo API](https://open-meteo.com) (no key needed)
> - **Recipe finder** — search and browse recipes using the [TheMealDB API](https://www.themealdb.com/api.php) (no key needed)
> - **ACME Order System** — explore architectural patterns and anti-patterns in a realistic Spring Boot application — [see details](#reference-projects)

---

## Format B — Fast path (3 hours)

For groups that have already been introduced to the Conductor Model. Minimal intro, maximum hands-on.

| Time | What happens |
|---|---|
| 0:00–0:10 | Recap and orientation |
| 0:10–0:25 | Live demo: `/conductor` → `/kickstart` → first change |
| 0:25–2:40 | Hands-on — you build, facilitator circulates |
| 2:40–3:00 | Share back + feedback |

The hands-on block is the session. Everything else is minimal.

---

## Before you arrive

**This is the most important page.** If you are not prepared, you will spend the first 45 minutes catching up instead of building.

→ [Prepare before the session](prepare.md)

## During the session

→ [Getting started — what to run when you sit down](getting-started.md)

## Reference Projects

### ACME Order Management System

A realistic Spring Boot application with 11 commits of history, showing architectural patterns and anti-patterns in practice. Use it to:
- Explore real codebase decisions (good and questionable)
- Walk through git history to understand how a project evolved
- Discuss refactoring approaches with your team

**Clone independently** (doesn't affect playground):
```bash
git clone https://github.com/consid-agentic-engineering/acme-order-system.git
cd acme-order-system
git log --oneline  # See the full history
```

Or explore it **here** in the playground at `playground/acme-order-system/` — each person can work in their own checkout.

---

## Background reading

→ [The Conductor Model — what it is and why it exists](the-conductor-model.md)
→ [OpenSpec — structured change management](openspec.md)
→ [Project ideas — developers](projects-developers.md)
→ [Project ideas — architects](projects-architects.md)
→ [Project ideas — presales](projects-presales.md)
