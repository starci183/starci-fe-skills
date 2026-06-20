---
name: starci-fe-ux-apply
description: >
  Build the layout the user chose from /starci-fe-ux-brainstorm into the FE source (ON-CANON) AND record
  what the user decided so the skill self-learns. Step 2 of the loop. Implements the page/components per
  the FE code canon, proposes any MINOR backend delta separately, then — the key step — WRITES every
  decision/feedback as a draft (`journal/drafts/` for block-design gu, `refs/drafts/` for UX lessons,
  `cannon/drafts/` for code conventions) so `/starci-fe-update-mindset` can fold it into the house
  knowledge. Use when the user says "/starci-fe-ux-apply", "chốt layout này", "apply layout", "build hướng
  này", "dựng cái này". Run with MAX effort.
---

# /starci-fe-ux-apply — build the chosen layout + RECORD the decision (this is how the skill learns)

Step 2 of the loop. `<src>` = the FE app (`D:/Repositories/starci-academy`); skill paths `../../cannon`,
`../../journal`, `../../refs`.

## 1. Build it ON-CANON
Implement the chosen layout — sections, components, states — in `<src>/src`. **Defer every code decision to
the canon**: read `../../cannon/CONTENT.md` and follow it — blocks props-only · features data-owner ·
`AsyncContent` · tokens + 3-tier + accent teal `#00a898` · HeroUI v3 compound · SWR/Redux/zustand/RHF per the
decision tree. Reuse existing blocks; build a NEW block to the canon's contract if the brainstorm proposed
one. Empty/loading/error + a11y + dark mode are part of "done". Keep the diff scoped; run `npm run lint` /
tsc before calling it done.

## 2. ⚙️ Minor backend delta — propose, don't sneak
If the layout needs data the BE doesn't expose, surface the small delta (GraphQL field / thin query /
projection tweak) as a clear separate proposal for the backend repo. Never silently edit the BE. If the data
isn't there yet, build behind a guard / graceful empty state.

## 3. RECORD the decision → `drafts/` (MANDATORY — the self-learning step)
**Every time the user picks or gives feedback, write it down** so it's never lost and the skill compounds.
Pick the right home and drop a short dated draft:

| The feedback is about… | Write a draft to | Folds into |
|---|---|---|
| how a **block** should look/behave (card spacing, sidebar density, chip color…) | `../../journal/drafts/<block>-<note>.md` | `journal/journal-<block>.md` |
| a reusable **UX pattern** lesson (from the web ref that won) | `../../refs/drafts/<topic>.md` | `refs/CONTENT.md` |
| a **code** convention discovered while building | `../../cannon/drafts/<name>.md` | `cannon/CONTENT.md` |

Each draft is tight: **what was decided · why · which page/block · date.** Don't edit the stable knowledge
files directly here — stage as drafts; the merge step hardens them.

## 4. Close out
Summarize: what was built, the section→data mapping shipped, the BE delta awaiting approval, and the
draft(s) recorded. Remind: run **`/starci-fe-update-mindset`** to fold the drafts into `journal/cannon/refs`
— after that, the next `/starci-fe-ux-brainstorm` is smarter.
