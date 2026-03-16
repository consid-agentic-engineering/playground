# Projects — Developers

New to the workflow? Start with [getting-started.md](getting-started.md).

Run `/conductor` → `/kickstart` → implement 2–3 changes → `/review` → `/version-close`.

That is the full loop. Pick a project where the domain is familiar — the session is about the workflow, not learning a new problem space at the same time.

Each project includes a **suggested start description** — paste this (or something close) when `/kickstart` asks "What is this project and for whom?" Then let the model suggest the rest.

Each project is scoped to fit within **90 minutes** of hands-on time.

---

## Level 1 — No backend, no database (recommended for first session)

---

**FruitNutritionInsight**
API: [fruityvice.com/api/fruit/all](https://www.fruityvice.com/api/fruit/all) — no API key required

> *"A read-only web app for health-conscious consumers who want to look up and compare nutrition facts for fruits. Uses the FruityVice public API."*

---

**FitGuide**
API: [ExerciseDB via RapidAPI](https://rapidapi.com/justin-WFnsXH_t6/api/exercisedb) — free tier, requires a free RapidAPI account

> *"A read-only exercise browser for people who want to find exercises for a specific muscle group, with descriptions and illustrations. Uses the ExerciseDB API."*

---

**Recipe Finder**
API: [TheMealDB](https://www.themealdb.com/api/json/v1/1/search.php?s=chicken) — no API key required

> *"A read-only recipe search app for home cooks who want to find meal ideas by ingredient or dish name, and see full recipes with instructions. Uses TheMealDB public API."*

---

**GitHub Profile Explorer**
API: [api.github.com](https://api.github.com/users/octocat) — no API key required for public read

> *"A read-only developer profile viewer for engineers who want to quickly look up a GitHub user's repositories, languages, and recent activity. Uses the public GitHub API."*

---

**Weather Dashboard**
API: [Open-Meteo](https://api.open-meteo.com/v1/forecast?latitude=55.68&longitude=12.57&current_weather=true) — no API key required

> *"A read-only weather dashboard for everyday users who want to check current conditions and a 5-day forecast for any city. Uses the Open-Meteo API."*

---

## Level 2 — Simple backend or local storage

Good if you're comfortable with the stack and want to practice full-stack delivery.

---

**VacationPlanner**

> *"A vacation planning tool for small teams who want to register planned time off, see team availability at a glance, and avoid booking conflicts. No external API — data stored locally."*

Stack suggestion: TypeScript / Next.js or Express + SQLite

---

**Personal Bookmarks**

> *"A personal bookmarking tool for developers who want to save, tag, and search URLs without relying on a browser or a third-party service. No external API — data stored locally."*

Stack suggestion: TypeScript / Next.js or Node + React

---

**Simple Kanban Board**

> *"A lightweight kanban board for solo developers or small teams who want to track tasks across three stages (To do / In progress / Done) without signing up for anything. State persisted in the browser."*

Stack suggestion: TypeScript / React

---

**Daily Standup Logger**

> *"A standup logging tool for developers who want to record what they did, what they plan to do, and any blockers — and be able to look back at past entries by date."*

Stack suggestion: TypeScript / Next.js or Express + SQLite
