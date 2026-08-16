# Portfolio Site

A personal portfolio website showcasing graphic design work, built to attract clients and hiring managers.

## Tech stack

- **Framework:** Next.js (App Router)
- **Language:** TypeScript
- **Styling:** Tailwind CSS
- **Linting:** ESLint
- **Hosting:** Vercel (free Hobby tier)

## Project rules

This repo is worked on by two AI coding agents — Claude Code and Codex — plus the site owner. Before making changes, read:

- [`CLAUDE.md`](./CLAUDE.md) — project context, design tokens, and rules (read by Claude Code)
- [`AGENTS.md`](./AGENTS.md) — identical content, read by Codex
- [`skills/claude-codex-collaboration/SKILL.md`](./skills/claude-codex-collaboration/SKILL.md) — how the two agents divide work and hand off

`CLAUDE.md` and `AGENTS.md` must always stay identical. Update both in the same commit whenever a rule changes.

## Getting started

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to view the site.

## Available scripts

```bash
npm run dev     # start the dev server
npm run build   # production build
npm run start   # run the production build locally
npm run lint    # run ESLint
```

## Agent permissions

`.claude/settings.json` encodes the approval rules from `CLAUDE.md`:

- **Free to do without asking:** editing components/pages/styles/content on a working branch, running dev/build/lint, committing to a working branch
- **Requires approval first:** deploying to production, changing Vercel/domain settings, installing dependencies, deleting existing files, force-pushing or rewriting history, pushing directly to `main`

## Deployment

Hosted on Vercel. Production deploys require explicit approval — see [`CLAUDE.md`](./CLAUDE.md).
