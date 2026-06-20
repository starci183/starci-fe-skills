---
name: starci-fe-update-mindset
description: >
  Distill accumulated StarCi FE learning into the stable knowledge. Two jobs: (1) UX MERGE — when
  `<src>/.claude/memory/ux/exp/` has ~5+ experience files (recorded by /starci-fe-ux-apply), merge them
  into `<src>/.claude/ux/MINDSET.MD` so /starci-fe-ux-brainstorm keeps getting smarter; (2) DRAFT MERGE —
  fold pending code/visual rule drafts (`cannon/drafts/*`, `<src>/.claude/rules/drafts/*`) into the stable
  canon (`cannon/CONTENT.md`) / app rules, newest-wins, then delete the merged drafts. Use when the user
  says "merge mindset", "cập nhật mindset", "gộp kinh nghiệm ux", "merge exp", "merge drafts", "update
  canon", "fold rules", "/merge", or after ~5 exp files accumulate.
---

# /starci-fe-update-mindset — distill experience + drafts into stable knowledge

`<src>` = the FE app repo (`D:/Repositories/starci-academy`). Skill-relative paths (`../../cannon/…`)
point inside the shared `starci-fe-skills` repo.

Two independent merges — do whichever the user asks for (or both):

---

## JOB 1 — UX experience → `MINDSET.MD` (the main loop)
The brainstorm/apply loop drops one experience file per applied layout into
`<src>/.claude/memory/ux/exp/<name>.md`. After ~5 accumulate, distill them so the mindset stays sharp.

1. **Read** every `<src>/.claude/memory/ux/exp/*.md` + the current `<src>/.claude/ux/MINDSET.MD` (if any).
2. **Distill, don't concatenate.** Extract the durable LESSONS that recur across exp files — what layout
   moves the teacher keeps choosing, what gets rejected, house taste, which refs/archetypes win for which
   page type, gamification/paywall/AI-panel preferences. Drop one-off specifics.
3. **Write** `<src>/.claude/ux/MINDSET.MD` as a tight, organized mindset (by page-type / by lens), each
   principle phrased as a reusable rule with a one-line "why" + the exp file(s) it came from.
   **Newest exp wins** on conflict.
4. **Archive the merged exp.** Move the consumed `exp/*.md` to `exp/_merged/` (or delete) so the folder
   re-accumulates toward the next ~5. Keep any exp that wasn't distilled and say why.
5. Report: which exp files were merged, the new/changed mindset principles, what was dropped as one-off.

> `MINDSET.MD` lives in the app at `.claude/ux/MINDSET.MD` (NOT under `memory/`). The `legacy/` and `exp/`
> inventories under `.claude/memory/ux/` are raw material — only this skill rolls them up into the mindset.

---

## JOB 2 — Rule drafts → stable canon / rules
Stage new conventions as drafts mid-coding (never edit stable files in place); this folds them home.

| Draft location | Holds | Merges INTO |
|---|---|---|
| `../../cannon/drafts/*.md` | new **code-pattern** rules | `../../cannon/CONTENT.md` — the matching SLICE (+ Appendix A ledger) |
| `<src>/.claude/rules/drafts/*.md` | new **visual / UX** rules | `<src>/.claude/rules/starci-*.md` or `.claude/design/`; brainstorm principles → `../starci-fe-ux-brainstorm/CONTENT.md` |

1. Read every draft in both folders (if empty, say so).
2. Classify each → exact target section. Code law (RULE · EXAMPLE real `src/...` path · DO/DON'T ·
   VIOLATION) → the right `cannon/CONTENT.md` SLICE. Visual → the element rule / design doc.
3. Merge concisely in the canon's voice — fold into an existing rule when it's a refinement; add a new
   numbered rule only when genuinely new. **Newest draft wins** on conflict; keep claims grounded in a
   real `src/...` path (un-evidenced hunches stay as drafts).
4. `git rm` each merged draft; leave un-mergeable ones with a note.

---

## Always
- **Do NOT push.** Stage changes; the user reviews + `git push` (their publish step).
- Report a table: source (exp file / draft) → destination → what changed → conflicts resolved (winner).
- This is the canon/skills counterpart of the lighter `merge` skill — prefer this when `cannon/` or the
  UX mindset is involved.
