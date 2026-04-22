# Before You Arrive

Complete all steps before the session. This takes 20–40 minutes depending on what you already have installed.

If you get stuck, open an issue in this repo or reach out beforehand — not on the day.

---

## Step 0 — Terminal (Windows only)

All commands in this guide run in a terminal. On macOS and Linux you already have one. On Windows you need to set one up first.

**Recommended: Windows Terminal + Git Bash**

1. Install [Git for Windows](https://git-scm.com/download/win) — this gives you Git Bash, which runs all the commands in this guide without modification
2. Install [Windows Terminal](https://aka.ms/terminal) from the Microsoft Store (optional but nicer)
3. Open Windows Terminal and select **Git Bash** as your shell

> **WSL2 also works** if you already have it set up. Run everything inside the Linux shell. If you don't have WSL2, Git Bash is simpler to get running quickly.

**Not recommended for this session:** PowerShell or Command Prompt — the copy commands in Step 3 use Unix-style paths that won't work there.

---

## Step 1 — Accounts

**GitHub account (required)**
You need a GitHub account to create a repository for your project.
→ Sign up at [github.com](https://github.com) if you don't have one.

**Agent subscription or API key**
You need access to at least one coding agent. See Step 2.

> **Cheapest path:** A Claude Pro subscription ($20/month) covers Claude Code with no API key management. If you don't have anything set up yet, this is the easiest option.

---

## Step 2 — Install a coding agent

Pick one. You only need one.

### Option A: Claude Code (recommended)

Claude Code runs in your terminal and works with any project.

1. Install Node.js 18+ if you don't have it: [nodejs.org](https://nodejs.org)
2. Install Claude Code:
   ```bash
   npm install -g @anthropic-ai/claude-code
   ```
3. Authenticate:
   ```bash
   claude
   ```
   Follow the login prompt. You need an Anthropic account with API access or a Claude Pro/Max subscription.

Verify:
```bash
claude --version
```

### Option B: OpenCode

1. Install from [opencode.ai](https://opencode.ai)
2. Open your project folder in OpenCode

### Option C: Codex (OpenAI)

1. Install:
   ```bash
   npm install -g @openai/codex
   ```
2. You need an OpenAI API key with credits — sign up and add credits at [platform.openai.com](https://platform.openai.com)
3. Set your key:
   ```bash
   export OPENAI_API_KEY=<your-key>
   ```
   On Windows (Git Bash), this syntax works as-is.

---

## Step 3 — Install The Conductor Model

This installs the workflows into your agent.

**Clone the library:**
```bash
git clone https://github.com/consid-agentic-engineering/conductor-model.git /tmp/conductor-model
cd /tmp/conductor-model
npm install
npm run build
```

**Install into your agent:**

| Agent | Command |
|---|---|
| Claude Code | `npm run install:global` |
| OpenCode | `cp -r dist/exports/opencode/.opencode <your-project>/` |
| Codex | `cp -r dist/exports/codex/.agents <your-project>/` |

For OpenCode and Codex, replace `<your-project>` with the path to your project folder.

> **Windows note:** These commands work in Git Bash. If you are using WSL2, run them inside the Linux shell.

**Verify it works:**

Open your agent in any folder and run:
```
/conductor
```

You should see a numbered menu asking what type of project this is. If you see that, you're ready.

---

## Step 4 — Have a project to bring

You need something to work on. It should be:

- Small enough to make meaningful progress in 90 minutes
- Something you're genuinely curious about — not a toy example you don't care about
- A GitHub repository (empty is fine — you'll set it up during the session)

If you don't have an idea, pick one from the project ideas list:
- [Developers](projects-developers.md)
- [Architects](projects-architects.md)
- [Presales](projects-presales.md)

---

## Checklist

- [ ] Terminal ready (Windows: Git Bash installed and working)
- [ ] GitHub account
- [ ] Coding agent installed and authenticated
- [ ] Conductor Model installed and `/conductor` shows a menu
- [ ] Project idea ready + empty GitHub repo created

If all five are checked, you're ready.
