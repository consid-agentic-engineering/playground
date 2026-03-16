# The Conductor Model

*Above the Algorithm. Directed Agentic Delivery.*

---

## The problem

AI-assisted development is producing code faster than ever. Prototypes appear in hours. Features materialize from a few prompts. The barrier between a high-level idea and working code continues to shrink.

There is a problem with this. When development relies primarily on conversational AI, decisions rarely become shared artifacts. Each developer prompts differently. Reasoning ends up buried in personal chat histories rather than documented in the project itself.

Three things tend to break:

**Erosion of traceability** — when a stakeholder asks why a particular design decision was made, the answer is difficult to reconstruct. The code exists, but the reasoning behind it often does not.

**Architectural drift** — without explicit structural intent guiding implementation, AI-generated code tends to accumulate in whichever direction the prompts happen to push it. Coherence slowly degrades.

**Onboarding failure** — new developers inherit a codebase whose decisions were produced in conversations they never saw. They must reverse-engineer reasoning that was never written down.

> The problem is not that AI is being used. The problem is that AI is being used without a system that preserves intent.

---

## The opportunity

When execution becomes cheap, the relative importance of decisions increases. The role of the engineer shifts as the boundary between thinking and building moves.

There are two futures:

**Below the algorithm** — engineers become operators of AI systems that determine how software is built while humans supervise the output.

**Above the algorithm** — humans define intent, architecture, and direction while AI systems execute within those boundaries. The algorithm becomes a mechanism for amplifying human decisions rather than replacing them.

The difference between these two futures is not technological capability. It is **structure**.

---

## The metaphor

In an orchestra, many highly capable performers operate simultaneously. Each musician knows how to play their instrument and can produce impressive output individually. Without coordination, the result would not be music but noise.

What makes the orchestra coherent is the existence of both a score and a conductor.

| | |
|---|---|
| **The Score** | The human-defined foundation for delivery. Architecture, specifications, capability boundaries, and constraints that shape the system. These artifacts function as a contract that guides execution. |
| **The Orchestra** | The AI agents operating within that framework. Different agents assist with exploration, architecture validation, implementation, or review — each within the boundaries defined by the score. |
| **The Conductor** | The human. Engineers set direction, resolve ambiguity, coordinate execution, and remain accountable for outcomes. As AI increases the speed of implementation, this coordinating role grows rather than diminishes. |

> Without a conductor, acceleration produces chaos. With one, acceleration becomes leverage.

---

## Two principles

**Architecture-driven delivery** — architecture functions as a living contract rather than a static diagram. Engineers maintain architectural descriptions that capture the intended structure of the system. AI agents operate within those boundaries, and proposed changes are validated against architectural intent before integration.

**Specification-driven execution** — humans invest in defining clear specifications before implementation begins. Specifications establish scope, expected behavior, constraints, and acceptance criteria. AI systems then implement changes against these specifications rather than relying on loosely defined prompts.

---

## What changes

| | Without structure | With structure |
|---|---|---|
| AI usage | Developers prompt independently | Teams share agents, workflows, and vocabulary |
| Architecture | Becomes implicit and undocumented | Becomes explicit and reviewable |
| Reviews | Depend on individual opinion | Evaluate alignment with intent |
| Decisions | Disconnected from capabilities | Remain connected to the capabilities they support |
| Outcome | AI speeds up implementation only | AI amplifies the entire delivery lifecycle |

---

## How it works in practice

The Conductor Model is delivered as a library of **agents**, **playbooks**, and **skills** that run inside your coding agent (Claude Code, OpenCode, Codex, etc.).

You start with `/conductor`. It sets up the project, creates the documentation structure, and routes you to the right workflow for where you are.

For a new project the fast path is:
```
/conductor → /kickstart → build → /review → /version-close
```

The model supports two delivery methods:
- **OpenSpec** — spec-first, structured change management with proposals and a full implementation order
- **GSD** — Get Things Done. Lightweight, minimal ceremony. Just build.

Full getting-started guide → [getting-started.md](getting-started.md)
