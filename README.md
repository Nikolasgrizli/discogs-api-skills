# Discogs API Skills

A collection of **Agent Skills** for working with the **Discogs API** (`api.discogs.com`).

These skills are model-agnostic: they are plain Markdown and work with **any LLM or agent runtime that supports the "skills" pattern** (progressive-disclosure reference docs loaded on demand) — Claude Code / Claude agents, or any other framework that can read skill folders.

## What this is

This repository bundles a set of focused, self-contained skills — one per area of the Discogs API. Each skill is a folder containing:

- **`SKILL.md`** — a short, always-loaded description telling the agent *when* to use the skill and the key facts to keep in mind.
- **`reference.md`** — the detailed reference: endpoints, parameters, request/response shapes, auth requirements, and gotchas.

When loaded into an agent environment, the model picks the right skill based on the task and pulls in the matching Discogs documentation on demand, instead of guessing endpoint behaviour.

## What it covers

Together these skills cover the **entire public Discogs API documentation as it currently stands**:

| Skill | Area |
|-------|------|
| `discogs-overview` | Cross-cutting conventions: `User-Agent`, rate limiting, pagination, API versioning, status codes, JSONP |
| `discogs-authentication` | User token, Consumer Key/Secret (Discogs Auth) and full OAuth 1.0a flow; building the `Authorization` header |
| `discogs-database` | Read-only catalog: Releases, Masters, Artists, Labels, ratings, videos, `/database/search` |
| `discogs-images` | How signed image URLs work and why they require authentication |
| `discogs-marketplace` | Listings, orders, order messages, selling fees, price suggestions, release market stats |
| `discogs-inventory-export` | Asynchronous export of a seller's inventory to CSV (request → poll → download) |
| `discogs-inventory-upload` | Bulk add / change / delete listings via CSV upload |
| `discogs-user-identity` | `oauth/identity`, user profiles, submissions and contributions |
| `discogs-user-collection` | Collection folders, instances, ratings, custom fields, collection value |
| `discogs-user-wantlist` | Listing, adding, updating and removing wantlist entries |
| `discogs-user-lists` | User-curated Lists of database items |

> Scope note: the skills document the **public Discogs HTTP API**. They are reference/knowledge skills — they do not ship a client library or execute requests themselves, so they are usable from any language or stack.

## How to use

### With an agent / LLM that supports skills

1. Clone this repository:
   ```bash
   git clone https://github.com/Nikolasgrizli/discogs-api-skills.git
   ```
2. Make the skill folders available to your agent by copying (or symlinking) them into the directory your runtime scans for skills. Examples:
   - **Claude Code — project scope:** `<your-project>/.agents/skills/`
   - **Claude Code — user scope:** `~/.claude/skills/`
   - **Other runtimes:** whichever folder your framework loads skills from.
   ```bash
   cp -R discogs-api-skills/discogs-* /path/to/your/skills/
   ```
3. Start your agent and describe your Discogs task in natural language (e.g. *"fetch a release by id"*, *"set up OAuth for Discogs"*, *"export my inventory to CSV"*). The relevant skill is matched and loaded on demand.

If your runtime expects a different layout or manifest, you can still feed the `SKILL.md` / `reference.md` contents to the model as context — the files are intentionally plain Markdown with no tool-specific dependencies.

### As plain documentation

You don't need an agent to benefit from this. Each `reference.md` is readable on its own and works as a concise, task-oriented reference for the corresponding part of the Discogs API.

## Layout

```
discogs-api-skills/
├── discogs-overview/
│   ├── SKILL.md
│   └── reference.md
├── discogs-authentication/
│   ├── SKILL.md
│   ├── reference.md
│   └── evals/evals.json
├── discogs-database/
├── discogs-images/
├── discogs-marketplace/
├── discogs-inventory-export/
├── discogs-inventory-upload/
├── discogs-user-identity/
├── discogs-user-collection/
├── discogs-user-wantlist/
└── discogs-user-lists/
```

(Every skill folder follows the same `SKILL.md` + `reference.md` structure.)

## Source

The authoritative Discogs API documentation lives at <https://www.discogs.com/developers>. These skills distill that documentation into an agent-friendly, model-agnostic format.
