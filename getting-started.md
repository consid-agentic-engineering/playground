# Getting Started — During the Session

You're sitting down, agent is open, project folder is ready. Here's what to run.

**Not prepared yet?** Go to [prepare.md](prepare.md) first. You need the Conductor Model installed and `/conductor` working before continuing here. The Conductor Model includes OpenSpec — no separate install needed.

---

## Step 1 — Initialize the project

Run in your agent:

```
/conductor
```

Walk through the numbered menu:

1. **Project type** → Product or Delivery
2. **Documentation mode** → Lean (simplest) or Governed
3. **Implementation method** → OpenSpec
4. **Project name and description** → one sentence

When asked how to start, choose **1. Kickstart**.

---

## Step 2 — Generate your docs in 3 questions

Run:

```
/kickstart
```

The kickstart asks three questions and suggests answers at each step — you mostly confirm rather than type:

1. **What is this project and for whom?** — one sentence, write your own
2. **Capabilities** — the agent suggests 3–5, you confirm or adjust
3. **Tech stack and components** — the agent suggests based on your description, you confirm or adjust

After the three questions the agent writes:
- A draft project charter
- A draft architecture description
- (OpenSpec) A full implementation order and one proposal per change

When kickstart finishes, choose **1. Continue as-is** and start building.

---

## Step 3 — Build

Open `openspec/implementation-order.md` and work through the changes in order.

For each change:

1. Implement it — use your agent, keep the scope tight
2. Review it:
   ```
   /review change <change-name>
   ```
3. Merge the PR

> **Tip:** Consider using two separate agent conversations — one for implementation, one for review and governance. Keeps the architecture context clean. Not required for small projects.

---

## Step 4 — Close the version

When you've finished as many changes as time allows:

```
/version-close
```

---

## Orienting at any time

Lost track of where you are? Run:

```
/conductor
```

It reads the project state and tells you what exists, what's missing, and what to do next.

---

## Need more detail?

Full fast-path guide with examples: [conductor-model getting-started](https://github.com/consid-agentic-engineering/conductor-model/blob/main/builder/model/getting-started.md)
