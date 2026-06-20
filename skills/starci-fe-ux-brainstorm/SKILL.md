---
name: starci-fe-ux-brainstorm
description: >
  Brainstorm 1–3 new layouts for a StarCi Academy page, then draw widget mockups for the user to choose.
  Step 1 of the self-learning loop. It READS the house knowledge that has been decided so far —
  `journal/journal-<block>.md` (how each block should look/behave), `cannon/CONTENT.md` (code rules),
  `refs/CONTENT.md` (UX lessons) — and FETCHES fresh course-website UX from the web (WebSearch/WebFetch),
  then proposes 1–3 layouts (components, functionality, optional MINOR backend delta) + renders widget
  mockups. The user picks → `/starci-fe-ux-apply` builds it AND records the feedback. NO production code.
  Run with MAX effort (Opus). Trigger on `/starci-fe-ux-brainstorm`, "đề xuất layout", "brainstorm trang",
  "thiết kế lại trang", "design layout", "bố cục trang", "nghĩ ux".
---

# /starci-fe-ux-brainstorm — propose layouts from house knowledge + live web refs (Opus · MAX)

Step 1 of the loop: `BRAINSTORM → (pick + feedback) → /starci-fe-ux-apply → /starci-fe-update-mindset`.
Two repos: the **skills repo** (this — holds `cannon/`, `journal/`, `refs/`) and **`<src>` = the FE app**
(`D:/Repositories/starci-academy`). Skill-relative paths are `../../cannon`, `../../journal`, `../../refs`.

This skill **does NOT write code** — it reads, fetches, proposes, draws widgets. Apply is a separate skill.

## 1. Read the house knowledge (what we've already decided — it grows over time)
- **`../../journal/journal-<block>.md`** — the design gu for each block (card, sidebar, tabs, chip, stat…).
  Open the ones relevant to the page. `../../journal/CONTENT.md` is the index.
- **`../../cannon/CONTENT.md`** — FE code rules, so every proposal is buildable (blocks props-only, features
  data-owner, tokens, accent teal `#00a898`, 3-tier layout).
- **`../../refs/CONTENT.md`** — UX lessons already captured from the web (read before re-fetching).

## 2. Fetch fresh refs from the web (live)
For the page's job (catalog · lesson player · gamification · onboarding · paywall · dashboard), use
**WebSearch/WebFetch** to pull CURRENT UX from the relevant learning platforms (table in
`../../refs/CONTENT.md`: Coursera, Udemy, Duolingo, Khan, Brilliant, Codecademy, edX, …). Lift what they do
well; note what NOT to copy. **Capture the durable takeaway** → `../../refs/drafts/<topic>.md` (so next time
is faster).

## 3. Read the page's current source
Route (`app/[locale]/…/page.tsx`) + the feature/blocks rendering it + the data it shows (GraphQL op in
`modules/api`/`hooks/swr` + Postgres entity — note fields the BE exposes but the UI ignores = opportunity).

## 4. Brainstorm 1–3 layouts
Each direction: anchored to a **journal decision** + a **fetched ref** + a design-system archetype.
- **components** — reuse StarCi blocks; propose a NEW block if needed (name its API + tier, per cannon).
- **functionality** — new interactions the layout enables.
- **⚙️ minor BE delta (propose only):** if the layout needs data the BE doesn't expose, propose a small
  GraphQL field/query/projection. Scope small. Never write BE here.
- section → data table; empty/loading/error + a11y + dark mode from the start.

## 5. Draw the widget (mandatory)
`read_me` module `mockup` → `show_widget` rendering the 1–3 layouts side by side (CSS vars, accent teal),
each labelled, recommended one marked. The user looks and picks → hands off to **`/starci-fe-ux-apply`**.

> No separate memory files. The house knowledge IS `journal/` + `cannon/` + `refs/` — they get richer every
> loop, so each brainstorm starts smarter than the last.
