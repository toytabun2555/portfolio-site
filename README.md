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

## Claude Code skills

Installed under `.claude/skills/` via [`npx skills`](https://skills.sh):

| Skill | Source | What it does |
|---|---|---|
| `shadcn` | [shadcn-ui/ui](https://github.com/shadcn-ui/ui) | Add, search, fix, style, and compose shadcn/ui components in this project |
| `migrate-radix-to-base` | shadcn-ui/ui | Migrate components/projects from Radix UI primitives to Base UI |
| `accessibility` | [addyosmani/web-quality-skills](https://github.com/addyosmani/web-quality-skills) | WCAG 2.2 accessibility audits — screen reader support, keyboard nav, ARIA |
| `best-practices` | addyosmani/web-quality-skills | Modern web dev best practices — security, compatibility, code quality |
| `core-web-vitals` | addyosmani/web-quality-skills | Optimize LCP, INP, and CLS for page experience and search ranking |
| `performance` | addyosmani/web-quality-skills | General web performance audits — faster loads, smaller bundles |
| `seo` | addyosmani/web-quality-skills | Search engine visibility — meta tags, structured data, sitemaps |
| `web-quality-audit` | addyosmani/web-quality-skills | Combined performance + accessibility + SEO + best-practices audit |
| `vercel-react-best-practices` | [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills) | React/Next.js performance patterns from Vercel Engineering (rendering, data fetching, bundle size) |
| `vercel-optimize` | vercel-labs/agent-skills | Vercel cost/performance optimization for deployed Next.js apps — Core Web Vitals, caching, function invocations |

Only the React/Next.js performance-relevant skills were kept from `vercel-labs/agent-skills`; skills unrelated to this project (React Native, view transitions, Vercel CLI auth, deploy automation, writing/design guidelines) were removed after install.

## Agent permissions

`.claude/settings.json` encodes the approval rules from `CLAUDE.md`:

- **Free to do without asking:** editing components/pages/styles/content on a working branch, running dev/build/lint, committing to a working branch
- **Requires approval first:** deploying to production, changing Vercel/domain settings, installing dependencies, deleting existing files, force-pushing or rewriting history, pushing directly to `main`

## Deployment

Hosted on Vercel. Production deploys require explicit approval — see [`CLAUDE.md`](./CLAUDE.md).
