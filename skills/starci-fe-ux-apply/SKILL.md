---
name: starci-fe-ux-apply
description: >
  Implement the layout direction the user chose from /starci-fe-ux-brainstorm into the FE source — built
  ON-CANON — and record the learning so the mindset compounds. This is B3 of the ux loop: take the picked
  widget direction + the legacy state (`<src>/.claude/memory/ux/legacy/<name>.md`) + the brainstorm doc,
  build the page/components following the FE code canon (defer code rules to starci-fe-cannon-apply /
  `../../cannon/CONTENT.md`), surface any MINOR backend delta as a separate proposal, then write the
  experience to `<src>/.claude/memory/ux/exp/<name>.md`. Use when the user says "/starci-fe-ux-apply",
  "chốt layout này", "apply layout", "dựng layout đã chọn", "build hướng này". After ~5 exp files,
  /starci-fe-update-mindset distills them into MINDSET.MD.
---

# /starci-fe-ux-apply — build the chosen layout (on-canon) + record experience (B3)

`<src>` = the FE app source (`D:/Repositories/starci-academy`). This closes the loop:
`/starci-fe-ux-brainstorm` (B1 legacy + B2 brainstorm 1–3 + widget) → **user picks** → this skill builds it
and banks the learning → after ~5, `/starci-fe-update-mindset` → `MINDSET.MD`.

## Step 1 — Confirm the chosen direction
- Identify `<name>` (the page slug) and which of the 1–3 brainstormed directions the user picked.
- Load context: `<src>/.claude/memory/ux/legacy/<name>.md` (current state) + the brainstorm doc
  (`<src>/src/components/features/<Feature>/UX-BRAINSTORM.md` if written) + the chosen direction's
  section→data table and ref anchors. If anything is ambiguous, ask once, then proceed.

## Step 2 — Build it ON-CANON (the code step)
Implement the chosen layout — sections, components, states — in `<src>/src`. **Defer every code-pattern
decision to the FE canon**: read `../../cannon/CONTENT.md` (or invoke the `starci-fe-cannon-apply`
mindset) and follow it:
- blocks props-only · features data-owner · `AsyncContent` for data regions · tokens + 3-tier layout +
  accent teal `#00a898` · HeroUI v3 compound · SWR/Redux/zustand/RHF per the canon's decision tree.
- Reuse existing blocks/features; create a NEW block only when the brainstorm proposed one (build it to
  the canon's block contract). Empty/loading/error + a11y + dark mode are part of "done", not later.
- Keep the diff scoped to the chosen page/feature. Run `npm run lint` / tsc before calling it done.

## Step 3 — ⚙️ Minor backend delta (propose, don't sneak)
If the layout needs data the BE doesn't expose, surface the delta the brainstorm flagged as a **clear,
small, separate proposal** (a GraphQL field on an ObjectType, a thin query/resolver, a projection tweak)
for the user to approve and apply in the backend repo. Never silently edit the backend from here. If the
data truly isn't available yet, build the UI behind a guard / with a graceful empty state.

## Step 4 — Record experience → `exp/<name>.md` (the learning)
Append/refresh `<src>/.claude/memory/ux/exp/<name>.md` — this is what makes the next brainstorm smarter:
- **Chosen direction** + a one-line gist of the layout.
- **WHY this one won** (the lens it served, the ref/archetype it leaned on, the trade-off accepted).
- **Repeat / avoid:** the durable move worth reusing on similar pages; what was rejected and why.
- **New convention discovered?** If building surfaced a reusable rule, stage it as a draft
  (`../../cannon/drafts/*` for code, `<src>/.claude/rules/drafts/*` for visual) — do NOT edit stable docs
  mid-build.
File shape: `# Exp — <name>` → chosen · why · repeat/avoid · refs used · BE delta (if any) · date.

## Step 5 — Close out
- Summarize in chat: what was built, the section→data mapping as shipped, the BE delta awaiting approval,
  and the exp lesson recorded.
- Remind: once `<src>/.claude/memory/ux/exp/` reaches ~5 files, run `/starci-fe-update-mindset` to distill
  them into `<src>/.claude/ux/MINDSET.MD`.

> Division of labor: `starci-fe-cannon-apply` = HOW to write any on-canon FE code (the rules).
> `starci-fe-ux-apply` = build a *specific chosen layout* end-to-end **and** bank the UX learning. Use this
> after a brainstorm; use cannon-apply for ad-hoc new code.
