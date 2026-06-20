---
name: starci-fe-ux-brainstorm
description: >
  Brainstorm 1–3 new layouts for a StarCi Academy page, then draw widget mockups for the user to choose.
  The loop: B1 — read the page's CURRENT state from the FE source and save it to
  `<src>/.claude/memory/ux/legacy/<name>.md`; B2 — load accumulated experience from
  `<src>/.claude/memory/ux/exp/` + the distilled `<src>/.claude/ux/MINDSET.MD`, FETCH course-website UX
  LIVE from the web (capturing lessons into `refs/`), distill them, and brainstorm 1–3 fresh layouts (components, functionality, optional
  MINOR backend deltas) + render widget mockups. The user then picks via `/starci-fe-ux-apply` (which
  records experience to `.claude/memory/ux/exp/<name>.md`); after ~5 exp files, `/starci-fe-update-mindset`
  merges them into MINDSET.MD. NO production code here. Run with MAX effort (Opus). Trigger on
  `/starci-fe-ux-brainstorm`, "đề xuất layout", "brainstorm trang/layout", "thiết kế lại trang",
  "design layout", "bố cục trang", "nghĩ ux".
---

# /starci-fe-ux-brainstorm — brainstorm 1–3 layouts from legacy state + accumulated mindset + refs (Opus · MAX)

Two repos in play:
- **shared skills repo** = `https://github.com/starci183/starci-fe-skills` (this repo) — holds `cannon/`,
  `journal/`, `refs/`, and these skills. **Refs are FETCHED LIVE from the web** each brainstorm; the durable
  lessons accumulate in `../../refs/CONTENT.md` (+ `refs/drafts/`) — no static teardowns.
- **`<src>` = the FE app source** (`D:/Repositories/starci-academy`) — where you read state and where the
  `.claude/memory/` + `.claude/ux/` learning files live.

This skill **does NOT write production code** — it captures state, brainstorms 1–3 layouts, and draws
widget mockups. Applying a chosen layout is `/starci-fe-ux-apply`.

## The loop (B1 → B2 → B3 → merge)

```
B1  read current state   ──►  <src>/.claude/memory/ux/legacy/<name>.md      (this skill)
B2  load exp + MINDSET + refs  ──►  brainstorm 1–3 layouts + widget         (this skill)
B3  user picks → apply   ──►  /starci-fe-ux-apply + write exp/<name>.md      (apply skill)
    every ~5 exp files   ──►  /starci-fe-update-mindset → .claude/ux/MINDSET.MD
```

## Five goal lenses (chốt mục tiêu trước)
UX-only · Marketing · Strategic communication · Component design · Page layout. Một yêu cầu có thể chạm
nhiều lens — nêu rõ lens chính trước khi brainstorm.

---

## B1 — Read current state → save to `legacy/<name>.md`
Capture the page's CURRENT UX once, persist it, reuse it.
1. `<name>` = the page slug (e.g. `lesson-reader`, `dashboard`, `course-catalog`).
2. Open `<src>/.claude/memory/ux/legacy/<name>.md`.
   - **Exists & still accurate** → read it, use as baseline (don't re-derive).
   - **Missing / stale** → rebuild from the real source, then WRITE it.
3. When (re)building, read `<src>/src` and record:
   - **Route** (`app/[locale]/…/page.tsx`) + the feature/blocks that render it.
   - **Data shown** = GraphQL op (`modules/api`, `hooks/swr`) + Postgres entity (which fields are used;
     which the BE exposes but the UI ignores = opportunity).
   - **Layout & sections**, the **states** (loading/empty/error), and the **pain points**.
4. File shape: `# Legacy UX — <name>` → route · components · data (GraphQL + entity) · sections · states ·
   pain points. This is the saved baseline B2 builds on.

## B2 — Load experience + mindset + refs → brainstorm 1–3 layouts + widget
Pull together THREE knowledge sources, then diverge:
1. **Accumulated experience** — read every `<src>/.claude/memory/ux/exp/*.md` (past applied-layout
   learnings) **and** the distilled `<src>/.claude/ux/MINDSET.MD` (the merged mindset). These encode "what
   worked / what the teacher chose / house taste" — weight them heavily.
2. **Course-UX refs — FETCH LIVE (no static files):** read `../../refs/CONTENT.md` first for lessons already
   captured, then use **WebSearch/WebFetch** to pull CURRENT UX from the relevant learning platforms (see the
   page-type → platforms table below). Lift what they do well; note what NOT to copy. **Then capture the
   durable takeaway** into `../../refs/drafts/<topic>.md` so it accumulates into `../../refs/CONTENT.md` over
   time (via `/starci-fe-update-mindset`) — next brainstorm reads it instead of re-fetching.
3. **Design system** — `../../cannon/CONTENT.md` (FE code canon: blocks/features, buildable) +
   `<src>/.claude/design/` (tokens, archetypes, accent teal `#00a898`, 3-tier layout).

Then **brainstorm 1–3 new layouts**, each:
- a distinct direction anchored to a specific ref + an exp/MINDSET lesson + an archetype;
- **components** (reuse StarCi blocks/features; propose a NEW block if needed — name its API + tier);
- **functionality** (new interactions/features the layout enables);
- **⚙️ minor BE change (allowed, proposed only):** if the layout needs data the BE doesn't expose, propose
  a small delta — a GraphQL field on an ObjectType, a thin query/resolver, a projection tweak. Scope it
  small (no architecture rework, no heavy migration). Propose, never write BE here.
- section → data table; empty/loading/error + a11y + dark mode considered from the start.

**Draw the widget (mandatory for new layouts):** `read_me` module `mockup` → `show_widget` rendering the
1–3 layouts side by side (CSS vars, accent teal), each labelled; mark the recommended one. The user looks
and chooses.

## B3 — Handoff to apply (not this skill)
The user picks a layout and runs **`/starci-fe-ux-apply`**, which builds the FE for the chosen direction
and records the learning to `<src>/.claude/memory/ux/exp/<name>.md` (what was chosen, why, what to repeat).
Any `⚙️ minor BE change` is reviewed/applied separately. **This brainstorm skill stops at the widget.**

## Merge cadence
After ~5 files accumulate in `<src>/.claude/memory/ux/exp/`, run **`/starci-fe-update-mindset`** to distill
them into `<src>/.claude/ux/MINDSET.MD` — so B2 keeps getting smarter without re-reading every exp file.

---

## Which platforms to FETCH, by page type (then capture lessons to refs/)
- Catalog / homepage / discovery / search / cards → Coursera, Udemy, Skillshare
- Lesson reader / video / transcript / notes / 3-pane code editor → Codecademy, Udemy, Khan Academy, Frontend Masters
- XP / streak / league / badge / progress → Duolingo, Brilliant, Khan Academy
- Onboarding / signup / activation / empty states → Duolingo, Codecademy
- Pricing / paywall / freemium gate / upgrade CTA / AI credit gate → Coursera, Brilliant, Duolingo
- Dashboard / home / "continue" card / mobile / bottom-nav → Codecademy, Coursera
- AI co-pilot panel / Socratic tutor / hint ladder → Coursera, Udemy, Khan Academy, Codecademy, Brilliant
- Trust / credential / certificate / "serious dev" tone → edX, Frontend Masters, freeCodeCamp

> Always read `../../refs/CONTENT.md` first (captured lessons); fetch live only what's missing, then write
> the new lesson back into `refs/drafts/`. The library grows; you re-fetch less over time.
