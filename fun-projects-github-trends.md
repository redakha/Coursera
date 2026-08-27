# Fun Projects to Build — Inspired by GitHub Trends (August 2026)

A curated list of weekend-to-month-sized project ideas, based on what's actually trending
on GitHub right now. Each idea is something you can build yourself, learn a lot from, and
show off — not just another todo app.

## What's trending right now (the short version)

Looking at GitHub's trending charts this month, a few big themes dominate:

1. **AI agents with memory** — projects like `volcengine/OpenViking` (~34k stars),
   `akitaonrails/ai-memory`, and `TencentCloud/TencentDB-Agent-Memory` all tackle the same
   problem: agents forget everything between sessions.
2. **Agent "skills" and plugins** — `anthropics/claude-plugins-community`,
   `virgiliojr94/book-to-skill` (turns PDFs into agent skills), and Cursor's plugin spec.
   Raw agents aren't enough; people are packaging expertise around them.
3. **Small / local-first AI** — `cactus-compute/needle` (foundation model for phones),
   `apache/maka` (local-first agent workspace), local alternatives to cloud tools like
   `AprilNEA/OpenLogi`.
4. **Agent-driven browsers & automation** — `citrolabs/ego-lite` (a browser built for AI
   agents to drive with your logged-in state).
5. **Opinionated dev environments** — `basecamp/omarchy` ("Beautiful, Modern & Opinionated
   Linux", 32k stars) shows people love a strong point of view in tooling.
6. **AI gateways / routing** — `diegosouzapw/OmniRoute` (56k stars, 1200+ models behind one
   API) and `earendil-works/pi` (unified LLM toolkit, ~98k stars).

Below: project ideas riffing on each theme, roughly ordered from "one weekend" to
"a month of evenings."

---

## Weekend-sized (fun, fast wins)

### 1. GitHub Trends Time Machine 📈
Scrape or pull the GitHub API daily for trending repos, store snapshots, and build a small
dashboard answering: *how long does a repo stay trending? What languages are rising?*
This one is meta — a trending project about trending projects.
- **Stack:** Python + GitHub API + SQLite + a notebook or Streamlit.
- **You'll learn:** API pagination, scheduled jobs (GitHub Actions cron is free), simple
  time-series viz.
- **Nice touch:** publish the dataset — trend-history datasets get stars themselves.

### 2. "Awesome X" with automated freshness checks
Pick a niche you know, make an awesome-list — but with a twist: a CI job that checks every
listed repo weekly for staleness (last commit, open issues, archived status) and badges it.
Most awesome-lists rot; yours wouldn't.
- **Stack:** Markdown + one Python script + GitHub Actions.
- **You'll learn:** CI automation, and it's a genuinely low-effort way to get contributors.

### 3. Terminal dashboard for your life
The `omarchy` energy: an opinionated TUI that greets you with weather, calendar, GitHub
notifications, and today's tasks in one beautiful terminal screen.
- **Stack:** Python (`textual`/`rich`) or Rust (`ratatui`).
- **You'll learn:** TUI layout, working with several APIs, config-file design.

### 4. Email-footprint checker (OSINT-lite)
Inspired by `megadose/holehe` trending: a small tool that, given *your own* email, shows
which popular sites have an account registered — a personal "where am I signed up?" audit.
- **Stack:** Python + `httpx` + async.
- **You'll learn:** async requests, rate limiting, responsible-use design.

---

## One-to-two-week projects

### 5. Personal memory server for AI chats 🧠
The hottest theme this month. Build a tiny "memory hub": a local service that stores notes
and facts about your projects, embeds them, and exposes search over MCP so any AI assistant
(Claude Code, Cursor, etc.) can recall them across sessions.
- **Stack:** Python + FastAPI + SQLite + any embedding model + MCP (Model Context Protocol).
- **You'll learn:** vector search, MCP servers, the actual hard problem (what to remember
  and what to forget).
- **Why now:** three of the top-20 trending repos this month are agent-memory projects.

### 6. Book/PDF → cheat-sheet skill converter
Riff on `book-to-skill` (26k stars): feed it a PDF (course notes, a textbook chapter) and
get back a structured, searchable reference — summary, key formulas, worked examples — as
Markdown skills an agent (or you) can use.
- **Stack:** Python + a PDF library + an LLM API.
- **Perfect fit if you're doing Coursera courses** — turn every course you take into a
  permanent, queryable reference.

### 7. Tiny model, real device
Inspired by `needle`: run a small open model (1–3B) on a phone, Raspberry Pi, or old laptop
and build one genuinely useful offline tool around it — e.g. an offline recipe assistant or
flashcard tutor.
- **Stack:** llama.cpp / MLC, plus a minimal UI.
- **You'll learn:** quantization, latency/quality tradeoffs, why "small and local" is its
  own engineering discipline.

### 8. LLM router with a budget
A mini-OmniRoute: one API endpoint in front of 2–3 model providers that routes each request
by task difficulty and tracks spend. Cheap model for easy prompts, big model when needed.
- **Stack:** Python/TypeScript proxy + provider SDKs + a routing heuristic (start with
  regex/length, graduate to a classifier).
- **You'll learn:** API design, streaming responses, cost engineering — very employable.

---

## Month-of-evenings projects (portfolio pieces)

### 9. Agent that browses like you
`ego-lite`-inspired: a browser automation agent for ONE personal chore — checking a
booking site for cancellations, tracking a price, filling a recurring form — using
Playwright with your logged-in profile.
- **Stack:** Playwright + an LLM for page understanding + a scheduler.
- **You'll learn:** the messy reality of automation (selectors break, sites change) — and
  guardrails, since an agent with your cookies needs careful scoping.

### 10. Local-first workspace with an event log
`apache/maka`'s core idea is lovely: append-only event logging. Build a notes/tasks app
where every change is an immutable event and the UI is a replay of the log. Add sync later
and you've reinvented CRDTs the fun way.
- **Stack:** anything — the idea is the architecture, not the framework.
- **You'll learn:** event sourcing, sync, and why local-first is having a moment.

### 11. A hive-mind for your study group 🐝
`block/buzz` ("a hive mind communication platform", 31k stars) but tiny: a shared space
where each member's notes/questions get auto-summarized into one living document per topic,
with an LLM flagging contradictions between people's notes.
- **Stack:** web app + LLM summarization + webhooks from wherever notes live.

### 12. Data-science capstone, but make it live
Since this repo is a Coursera capstone: take a past course project and productionize it the
2026 way — data pulled on a schedule, model retrained in CI, predictions served behind a
small API, drift monitored, README with badges. "Notebook → living service" is the single
most convincing portfolio upgrade for a data person.
- **Stack:** what you already know + GitHub Actions + FastAPI + Docker.

---

## Picking one

If you want the highest fun-to-effort ratio: **#1 (Trends Time Machine)** this weekend.
If you want maximum career relevance: **#5 (memory server)** or **#8 (LLM router)** — agent
memory and routing are literally the two biggest trend clusters on GitHub right now.
If you want to build on this repo's data-science roots: **#12**, with **#6** as a study aid
along the way.

## Sources

- [GitHub Trending (monthly)](https://github.com/trending?since=monthly)
- [GitHub Trending Weekly Digest — Aug 17–22, 2026](https://www.tommyz.blog/blog/github-trending-weekly-2026-08-17-to-2026-08-22)
- [Best Trending GitHub Repositories for AI Developers in 2026 — Firecrawl](https://www.firecrawl.dev/blog/best-github-repos)
- [Top 15 GitHub Projects Every Developer Should Explore in 2026 — DEV](https://dev.to/ali-asghar/top-15-github-projects-every-developer-should-explore-in-2026-32o4)
- [This year's most influential open source projects — GitHub Blog](https://github.blog/open-source/maintainers/this-years-most-influential-open-source-projects/)
