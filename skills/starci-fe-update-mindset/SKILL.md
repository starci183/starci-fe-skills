---
name: starci-fe-update-mindset
description: >
  Fold pending StarCi FE "draft" notes — new conventions, patterns, or UX principles jotted down
  mid-coding — into the STABLE knowledge: the code canon (`cannon/CONTENT.md`), the app's visual/UX
  rules (`<app>/.claude/rules/`), and the ux-brainstorm playbook. Keeps the canon/skills fresh and
  grounded without editing stable files mid-build: you stage a concept as a draft, later run this to
  merge it home (newest-wins), then it deletes the merged draft. Use when the user says "merge drafts",
  "cập nhật mindset", "update canon", "fold rules", "gộp draft", "/merge", or after accumulating draft
  notes during a coding session. Pairs with the drafts concept used across StarCi skills.
---

# /starci-fe-update-mindset — fold drafts into the stable canon/rules

The mindset stays fresh through a **draft → merge** loop, never by editing stable files mid-build:
1. While coding, a new convention / pattern / UX principle is jotted into a **draft** file.
2. This skill later reviews every draft, merges each into its correct stable home, reconciles
   conflicts (**newest wins**), then **deletes** the merged draft.

`<app>` = the FE app repo (`D:/Repositories/starci-academy`). Skill paths below are relative to this
skill file inside the `starci-fe-skills` repo.

## Step 1 — Gather drafts (two staging areas)
| Draft location | Holds | Merges INTO |
|---|---|---|
| `../../cannon/drafts/*.md` | new **code-pattern** rules (structure, components, data, state, forms, types, styling, routing) | `../../cannon/CONTENT.md` — the matching SLICE |
| `<app>/.claude/rules/drafts/*.md` | new **visual / UX** rules + brainstorm principles | `<app>/.claude/rules/starci-*.md` or design docs; brainstorm-only principles → `../starci-fe-ux-brainstorm/CONTENT.md` |

Read every draft in both folders. If both are empty, say so and stop.

## Step 2 — Classify each draft → pick its home
For each draft, decide where it belongs and the EXACT target section:
- **Code law / violation** (a `RULE` + `DO/DON'T` + `VIOLATION`) → `cannon/CONTENT.md`, the right **SLICE**
  (1 Structure · 2 Components · 3 Data · 4 State · 5 Forms · 6 Types · 7 Styling · 8 Routing). If it adds
  a new known-drift, also append a row to **Appendix A** (the inconsistency ledger).
- **Visual / element styling** (button/card/chip/spacing/token) → the app's `starci-<element>.md` rule
  file or `.claude/design/` doc.
- **Brainstorm / UX-method principle** (how to think about a layout, a new ref takeaway) →
  `starci-fe-ux-brainstorm/CONTENT.md`.
- A draft naming the destination explicitly (e.g. "File/§ đích khi /merge: …") → obey it.

## Step 3 — Merge concisely (do NOT bloat)
- Integrate the rule in the canon's voice: **RULE · EXAMPLE (real file path) · DO/DON'T · VIOLATION**.
  Keep it tight — fold into an existing rule when it's a refinement; add a new numbered rule only when
  it's genuinely new.
- **Reconcile conflicts: newest draft wins.** If a draft contradicts an existing stable rule, update the
  stable rule and note nothing about the draft (the stable doc is the single source of truth afterward).
- Keep every claim grounded — cite a real `src/...` path. If a draft is an unproven hunch with no
  in-repo evidence, leave it as a draft and flag it instead of merging.

## Step 4 — Delete merged drafts + report
- `git rm` (or delete) each draft that was successfully merged. Leave un-mergeable drafts in place.
- Report: a table of `draft → destination section`, what changed, any conflicts resolved (and which side
  won), and the drafts left behind with why.
- **Do NOT push.** Stage the changes and let the user review + `git push` (their publish step).

## Notes
- This is the **canon/skills** counterpart of the lighter `merge` skill (which only folds visual rule
  drafts). When both apply, prefer this one — it covers `cannon/` + the skills too.
- The `.claude/memory/` folders (`ux/`, `audits/`) are **persisted analysis**, not drafts — never merge
  or delete those here; they are owned by `starci-fe-ux-brainstorm` / `starci-fe-cannon-audit`.
