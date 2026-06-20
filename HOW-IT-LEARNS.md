# How these skills self-learn

The whole point: **force the AI to get better over time** at designing StarCi's FE — by recording what the
teacher decides into the **journal** and reading it back next time. One short loop, three knowledge stores.

## The house knowledge (3 stores — they GROW)
| Store | Holds | Filled from |
|---|---|---|
| **`cannon/`** | FE **code rules** (`CONTENT.md`) | scanning real `src/` |
| **`journal/`** | **design gu** per block (`journal-<block>.md`: card, sidebar, tabs, chip, stat…) | the teacher's design feedback |
| **`refs/`** | **UX patterns** from the best course websites (`CONTENT.md`) | live web search, distilled |

## The loop (3 steps — no separate merge command)
```
1. /starci-fe-ux-brainstorm   read journal + cannon + refs  +  SEARCH THE WEB
                              → propose 1–3 layouts + widget mockups
        │  teacher picks one + gives FEEDBACK
        ▼
2. /starci-fe-ux-apply        build it on-canon
                              → at the END of the task, AUTOMATICALLY write what was decided
                                into the journal (journal-<block>.md / refs / cannon)   ← the learning
        ▼
3. next brainstorm reads the now-richer journal → the skill is smarter
```

- **Web search** is in step 1 (refs fetched live, never stale).
- **"Record experience when the teacher feedbacks"** is step 2 — `apply` updates the **journal** itself at the
  end of the task. **The teacher never runs a merge command; it just happens.**
- **"Self-improve"** = the journal grew, so the next brainstorm starts smarter.

## The other two skills (code side, same knowledge)
- **`/starci-fe-cannon-audit`** — check existing code against `cannon/CONTENT.md`, report drift.
- **`/starci-fe-cannon-apply`** — write new code already on-canon.

## Publish
Edit the skills/knowledge in the FE source `.claude/`, then `pwsh .claude/sync-skills.ps1 "msg"` pushes the
new version to this repo so anyone can `/plugin install`. No hidden memory, no "mindset" — the knowledge is
just `cannon/` + `journal/` + `refs/`, and the **journal** only ever gets richer.
