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
- Studio name: JB Design
- Team: 2 คน — กษิณธิป ลิ้มวิไลกุล (Kasinthip Limvilaikul) และ พิทวัส ทาบุญ (Pitavat Tabun)
- Discipline: Brand & Packaging Designer — อัตลักษณ์แบรนด์ โลโก้ และบรรจุภัณฑ์
- One-sentence positioning: ช่วยแบรนด์อาหาร เครื่องดื่ม คาเฟ่ และบิวตี้/เวลเนส สร้างอัตลักษณ์ที่จำง่ายและใช้งานได้จริงในทุกจุดสัมผัส ตั้งแต่โลโก้ไปจนถึงบรรจุภัณฑ์
- Language: ใช้ทั้งภาษาไทยและอังกฤษสลับกันตามความเหมาะสมของแต่ละส่วนเนื้อหา (ชื่อคน/ชื่อโปรเจกต์คงชื่อเดิมตามที่เจ้าของแจ้ง ไม่แปล)

## Target audience
- Primary: เจ้าของธุรกิจ F&B / คาเฟ่ / บิวตี้-เวลเนส ขนาดเล็ก-กลางในกรุงเทพฯ ที่กำลังสร้างแบรนด์ใหม่หรือรีแบรนด์ รวมถึง agency/hiring manager ที่มองหา freelance brand designer
- What they need to see: งานที่ไปได้ไกลกว่าโลโก้ — เห็นระบบแบรนด์ที่ใช้งานได้จริงบน packaging, สื่อหน้าร้าน, social media (ไม่ใช่แค่ concept สวยๆ)
- Desired action: ทัก LINE หรืออีเมลเพื่อคุยงาน

## Design tokens (the hard rules)
- **Colors**: primary `#007c7a` (teal), secondary `#000000`, text `#000000` on light backgrounds / `#ffffff` on dark backgrounds. Never add a fourth core color. Accent usage must reuse these.
- **Typography**: Thai text uses Prompt, English text uses Switzer. Defined scale only: H1, H2, H3, Body, Caption. No arbitrary sizes.
- **Spacing**: base unit 8px. Only use multiples: 8, 16, 24, 32, 48, 64. Never arbitrary pixel values.
- **Breakpoints**: desktop 1440px, tablet 810px, mobile 390px. Every page must be checked at all three.

## Page structure
**Homepage**: Hero (name + one-sentence value prop) → Selected Work (3–6 projects) → About (short) → Contact CTA

**Project card component**: thumbnail, project name, category tag, one-line description, hover state, status badge (see "Project status & disclaimer" below). Build once as a shared component and reuse — never duplicate and edit.

**Case study page**: hero image → project meta (role, timeline, tools) → body written in STAR structure (Situation, Task, Action, Result) → project imagery → CTA to next project.

## Project status & disclaimer
- Selected Work แสดงผลงานทั้ง 6 ชิ้น (ไม่ตัดเหลือ 4)
- โปรเจกต์ที่ยังไม่เสร็จสมบูรณ์ (ปัจจุบันคือ BHAVANA และ UNPOLISHED) ต้องมี **status badge ที่มองเห็นชัดเจน** ทั้งบน Project card และบนหัวของ Case study page — ใช้ข้อความ "In Progress" หรือ "Concept in Development" ให้ตรงกับสถานะจริงของแต่ละโปรเจกต์ อย่าปนกับโปรเจกต์ที่เสร็จแล้ว
- ทุก Case study ต้องมี **disclaimer สั้น ๆ** ระบุว่าเป็นงาน concept/speculative project ไม่ได้อ้างอิงลูกค้าหรือธุรกิจที่มีอยู่จริง (ยกเว้นในอนาคตเมื่อมีงานลูกค้าจริงเข้ามา ให้ระบุแยกจากกลุ่มนี้อย่างชัดเจน) — วางไว้บริเวณ project meta หรือท้ายหน้า ไม่ต้องเด่นจนรบกวนการนำเสนองาน แต่ต้องหาเจอง่าย

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
