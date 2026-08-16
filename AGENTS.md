# Portfolio Website — Project Context

> This file and `AGENTS.md` must always contain identical content.
> `CLAUDE.md` is read by Claude Code. `AGENTS.md` is read by Codex.
> When any rule below changes, update both files in the same commit.

---

## Project
A personal portfolio website showcasing graphic design work, built to attract clients and hiring managers.

## Tech stack
- Framework: Next.js (App Router)
- Styling: Tailwind CSS
- Hosting: Vercel (free Hobby tier)
- Version control: GitHub

Do not introduce additional frameworks, UI kits, or CSS-in-JS libraries without asking first.

## Who I am
- Name: [fill in]
- Discipline: [e.g. Graphic Designer — branding, packaging, UI]
- One-sentence positioning: [what you do + for whom]

## Target audience
- Primary: [e.g. hiring managers, agencies, direct clients]
- What they need to see: [e.g. brand identity work with real outcomes]
- Desired action: [e.g. email me, book a call]

## Design tokens (the hard rules)
- **Colors**: primary `#007c7a` (teal), secondary `#000000`, text `#000000` on light backgrounds / `#ffffff` on dark backgrounds. Never add a fourth core color. Accent usage must reuse these.
- **Typography**: Thai text uses Prompt, English text uses Switzer. Defined scale only: H1, H2, H3, Body, Caption. No arbitrary sizes.
- **Spacing**: base unit 8px. Only use multiples: 8, 16, 24, 32, 48, 64. Never arbitrary pixel values.
- **Breakpoints**: desktop 1440px, tablet 810px, mobile 390px. Every page must be checked at all three.

## Page structure
**Homepage**: Hero (name + one-sentence value prop) → Selected Work (3–6 projects) → About (short) → Contact CTA

**Project card component**: thumbnail, project name, category tag, one-line description, hover state. Build once as a shared component and reuse — never duplicate and edit.

**Case study page**: hero image → project meta (role, timeline, tools) → body written in STAR structure (Situation, Task, Action, Result) → project imagery → CTA to next project.

## Animation rules
- **Allowed**: page-load fade/stagger on entry, hover transitions 200–400ms
- **Forbidden**: parallax on every section, scroll-jacking, 3D text effects, auto-playing video
- Rule of thumb: if a visitor would remember the animation more than the work, it's too much

## Content rule
Content comes before design. Never build a page with placeholder/lorem text — write the real copy first, then lay it out.

## Agent coordination
Two agents work on this repo: Claude Code and Codex.
- Claude Code: design system, shared components, multi-file refactors, design/accessibility review
- Codex: implementing new pages from established patterns, repetitive build work
- One agent per branch at a time. Never run both against the same branch simultaneously.
- The agent that builds a feature is not the agent that approves it.

## Requires my approval before doing (ask first, always)
- Deploying to production / promoting a preview to the live domain
- Changing domain or Vercel project settings
- Deleting pages, components, or files that already exist
- Changing the design tokens above once they're set
- Adding a new dependency or framework
- Force-pushing or rewriting git history

## Free to do without asking
- Creating and editing components, pages, and styles on a working branch
- Writing and revising content files
- Running builds, linters, and accessibility checks
- Committing to a working branch (not main)
