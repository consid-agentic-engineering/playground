# OpenSpec

OpenSpec is a structured change management approach for AI-assisted delivery. Instead of asking an agent to "implement feature X" in one open-ended prompt, you break work into small, clearly scoped changes — each with a proposal, a spec, and a review before it is integrated.

---

## Why it exists

When AI implements a large, vaguely scoped task, several things happen:

- The change is hard to review — too much changed at once
- Mistakes propagate before they are caught
- The reasoning behind implementation decisions is not recorded
- It is difficult to trace what was built back to what was intended

OpenSpec keeps changes small and explicit. Each change has a defined scope before implementation starts. This makes reviews faster, mistakes cheaper to catch, and the change history readable.

---

## The change loop

Each change follows the same loop:

```
Proposal → Specification → Implementation → Review → Integration
```

**Proposal** — one paragraph describing what this change delivers and why it belongs at this point in the sequence. Written before any code is touched.

**Specification** — acceptance criteria, affected components, and constraints. Detailed enough that the agent can implement without guessing.

**Implementation** — the agent implements against the spec.

**Review** — `/review change <name>` checks quality and traces the change back to capabilities (CAP-xxx) and the architecture description.

**Integration** — merge the PR. One change, one PR.

---

## How it fits with The Conductor Model

When you run `/kickstart` with OpenSpec selected, the model generates:

- A full **implementation order** (`openspec/implementation-order.md`) — a sequenced list of all changes needed to deliver the capabilities, in logical dependency order
- A **proposal** for each change (`openspec/changes/<slug>/proposal.md`)

You don't have to plan the change sequence yourself. The model reasons about what to build first based on the architecture and capabilities it just created.

During delivery, for each change:
1. Open the proposal — understand the scope
2. Let the agent implement it
3. Run `/review change <name>`
4. Merge

---

## When to use GSD instead

OpenSpec adds overhead. It is the right choice when:

- You are working in a team and changes need to be reviewable by others
- The project will run for more than a few weeks
- Architectural drift or scope creep is a real risk

Use **GSD** (Get Things Done) when:

- You are working alone on a small project
- Speed matters more than traceability
- The project is exploratory or throwaway

You choose between OpenSpec and GSD when you run `/conductor` to set up the project. You can change your mind — the model does not enforce the method mechanically.

---

## Getting started with OpenSpec

When running `/conductor`, select:
- Implementation method: **OpenSpec**

Then run `/kickstart`. The model will generate the full change backlog automatically.

The first thing to open after kickstart:
```
openspec/implementation-order.md
```

That is your roadmap for the session.
