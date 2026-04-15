# Playground — Directed Agentic Engineering

An open space to explore, experiment, and practice Directed Agentic Engineering in a hands-on way.

## What's here

This playground is a collection of projects, reference implementations, and guides for learning how to work with AI agents using structured workflows. It's designed for:

- **Architects** — exploring how to design systems with agentic capabilities
- **Developers** — understanding how to build and refactor codebases with AI assistance
- **Presales** — demonstrating capabilities and workflows to clients
- **Teams** — learning the Conductor Model and OpenSpec together

## How to start

Pick a direction based on what you want to practice:

### 1. Learn the framework
- → [**The Conductor Model**](the-conductor-model.md) — what it is and why it exists
- → [**OpenSpec**](openspec.md) — structured change management for agentic delivery

### 2. Start your own project
Pick an idea that interests you:

**Quick-start API projects** (under 10 minutes to first working version):
- **Fruit explorer** — nutrition data from [FruityVice API](https://www.fruityvice.com)
- **Weather widget** — conditions from [Open-Meteo API](https://open-meteo.com)
- **Recipe finder** — recipes from [TheMealDB API](https://www.themealdb.com/api.php)

**Real codebase exploration**:
- **ACME Order System** — realistic Spring Boot app showing patterns and anti-patterns
  - 11 commits of history to explore
  - Intentional design issues to discuss and refactor
  - Clone from [GitHub](https://github.com/consid-agentic-engineering/acme-order-system.git)

**Your own project**:
- Use `/conductor` to set up a new charter and architecture
- Use `/kickstart` to create the initial structure
- Use `/brownfield-explore` to understand the structure you just created
- Use `/openspec-new-change` to start your first improvement

See [Project ideas by role](projects-developers.md), [architects](projects-architects.md), [presales](projects-presales.md).

### 3. Explore a real codebase
- → [**Brownfield Exploration**](brownfield-exploration.md) — understand, assess, and improve an existing system using the ACME Order System
  - Practice `/health-assessment` to understand current state
  - Use `/brownfield-explore` to map the architecture
  - Design improvements with `/architect` or `/target-architecture`
  - Implement changes with OpenSpec workflows

### 4. Work through a workflow
Once you have a project:

1. **Understand** the current state — run `/health-assessment` or `/health-scan`
2. **Explore** the architecture — use `/brownfield-explore` or `/architect`
3. **Plan** improvements — create an OpenSpec change with `/openspec-new-change`
4. **Implement** — use `/openspec-apply-change` to write code
5. **Verify** — check with `/openspec-verify-change`
6. **Close** — archive the change with `/openspec-archive-change`

## Preparation

Before starting:
- → [**Prepare before you start**](prepare.md) — environment setup and tools
- → [**Getting started**](getting-started.md) — what to run first

## Background

- [The Conductor Model — framework and philosophy](the-conductor-model.md)
- [OpenSpec — structured workflow for changes](openspec.md)
- [Project ideas — developers](projects-developers.md)
- [Project ideas — architects](projects-architects.md)  
- [Project ideas — presales](projects-presales.md)

## Reference Projects

### ACME Order Management System

A realistic Spring Boot application with intentional design patterns and anti-patterns.

Use it to explore:
- How architectural decisions compound over time
- Real code with mixed patterns and technical debt
- How to assess and improve a codebase with agentic workflows

**Get started:**
```bash
git clone https://github.com/consid-agentic-engineering/acme-order-system.git
cd acme-order-system
```

Then follow the workflows in → [**Brownfield Exploration**](brownfield-exploration.md)
