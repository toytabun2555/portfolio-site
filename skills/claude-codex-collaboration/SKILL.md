---
name: claude-codex-collaboration
description: Use this skill when working on the coded portfolio website with both Claude and Codex — deciding which agent handles a task, setting up shared context files, coordinating work across branches, or reviewing work produced by the other agent. Triggers on requests about splitting work between agents, agent handoffs, or reviewing Codex output.
---

# Claude + Codex Collaboration

## Purpose
Coordinate two AI coding agents (Claude Code and OpenAI Codex) building the same portfolio website, so each does what it's genuinely best at and neither drifts from the design rules or overwrites the other's work.

## Division of labour
| Task type | Agent | Why |
|---|---|---|
| Planning, content, case study writing, design decisions | Claude Chat | Reasoning and writing, not code execution |
| Design system setup, tokens, shared components, multi-file refactors | Claude Code | Stronger at architecture and cross-file consistency |
| Building new pages/sections from an existing pattern, repetitive implementation | Codex | Faster generation, reads whole codebase for connections |
| Design quality review, accessibility check, brand consistency | Claude Code | Has the design skill library (frontend-design, brand-guidelines, accesslint, web-design-guidelines) |

**Core rule: one agent builds, the other reviews.** Never let the same agent implement a feature and then be the sole judge of whether it's correct — self-review misses the errors that come from its own assumptions.

## Shared context files (the foundation)
Both agents must read the same rules. Maintain two files at the repo root with **identical content**:
- `CLAUDE.md` — read automatically by Claude Code
- `AGENTS.md` — read automatically by Codex

When design rules change, update BOTH files in the same commit. If they drift apart, the two agents will produce inconsistent work and the cause will be hard to trace.

What belongs in these files: design tokens (colors, fonts, spacing scale), page structure conventions, component patterns, tech stack, out-of-scope items, and anything the agent must never do without asking.

## Avoiding collisions
1. **One agent per branch.** Never run both agents against the same branch simultaneously — they will overwrite each other's changes.
2. **Or one agent per file/page.** If working on the same branch, assign clearly separate scopes (e.g. Codex builds `/work` page, Claude Code handles `components/`).
3. Commit and push before handing off to the other agent, so the next agent starts from the current state.
4. Keep each agent session narrow in scope — one page or one component per session, reviewed before moving on.

## Handoff pattern
1. **Plan** in Claude Chat → write the decision into `CLAUDE.md`/`AGENTS.md` if it's a lasting rule
2. **Scaffold** with Claude Code → design system, shared components, folder structure
3. **Implement** with Codex → new pages following the established patterns
4. **Review** with Claude Code → check design quality, accessibility, consistency with tokens
5. Repeat from step 1 for the next feature

When handing off, be explicit about what was just done and what the next agent should NOT touch.

## Review checklist (when Claude Code reviews Codex output)
- Does it use the design tokens defined in the shared context files, or did it invent new values?
- Is spacing on the defined scale (multiples of the base unit), not arbitrary pixels?
- Are there more colors or font families than the rules allow?
- Does it work at all three breakpoints (desktop/tablet/mobile)?
- Are interactive elements accessible (contrast, focus states, semantic HTML)?
- Does the animation stay within the restraint rules, or did it add decorative motion?

## Anti-patterns to avoid
- Running both agents on the same branch at the same time
- Letting `CLAUDE.md` and `AGENTS.md` drift out of sync
- Having one agent both build and approve its own work
- Giving an agent a vague scope ("build the site") instead of one page/component at a time
- Skipping the review step because the output "looks fine" in the preview
