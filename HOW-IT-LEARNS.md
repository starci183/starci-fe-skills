# How these skills self-learn

The whole point: **force the AI to get better over time** at designing StarCi's FE — by recording what the
teacher decides and folding it back into the skill. One loop, three knowledge stores. That's it.

## The house knowledge (3 stores — they GROW)
Each is the same shape: a main file + a `drafts/` staging folder.

| Store | Holds | Filled from |
|---|---|---|
| **`cannon/`** | FE **code rules** (`CONTENT.md`) | scanning real `src/` |
| **`journal/`** | **design gu** per block (`journal-<block>.md`: card, sidebar, tabs, chip, stat…) | the teacher's design feedback |
| **`refs/`** | **UX patterns** from the best course websites (`CONTENT.md`) | live web search, distilled |

## The loop (4 steps)
```
1. /starci-fe-ux-brainstorm   read journal + cannon + refs  +  SEARCH THE WEB
                              → propose 1–3 layouts + widget mockups
        │  teacher picks one + gives FEEDBACK
        ▼
2. /starci-fe-ux-apply        build it on-canon
                              + RECORD every decision → drafts/        ← the learning happens here
        │
        ▼
3. /starci-fe-update-mindset  fold drafts/ → journal / cannon / refs   ← knowledge hardens
        │
        ▼
4. next brainstorm reads the now-richer knowledge → the skill is smarter
```

- **Web search** lives in step 1 (refs are fetched live, never stale).
- **"Record experience when the teacher feedbacks"** is step 2 — `apply` MUST write each decision as a draft
  (a component look → `journal/drafts/`, a UX lesson → `refs/drafts/`, a code rule → `cannon/drafts/`).
- **"Self-improve"** is step 3 — `update-mindset` merges the drafts (newest-wins) and deletes them.

## The other two skills (code side, same knowledge)
- **`/starci-fe-cannon-audit`** — check existing code against `cannon/CONTENT.md`, report drift.
- **`/starci-fe-cannon-apply`** — write new code already on-canon.

## Publish
Edit the skills/knowledge in the FE source `.claude/`, then `pwsh .claude/sync-skills.ps1 "msg"` pushes the
new version to this repo so anyone can `/plugin install`. No hidden memory folders — the knowledge IS
`cannon/` + `journal/` + `refs/`, and it only ever gets richer.
