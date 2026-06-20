# gap — the spacing rhythm (flex/grid `gap-*` + `space-*`)

Grounded from a full scan of `src/**.tsx` (2026-06-21):
**`gap-2` ×440 · `gap-3` ×423 · `gap-6` ×197** are the spine; `gap-0` ×61 and `gap-4` ×36 are the edges;
**`gap-1.5` ×194 is the biggest drift** to snap out. Allowed values: **`0 · 2 · 3 · 4 · 6`** only.

## The rule — pick by RELATIONSHIP, never by "size feel"
| `gap` | Relationship | Use for | seen |
|---|---|---|---|
| **`gap-0`** | a component's **title + its description** (one tight pair) | title ↔ desc | 61 |
| **`gap-2`** | **coupled** — two things that read as ONE | **label ↔ input** · icon ↔ label · avatar ↔ name · chip ↔ chip in a row | 440 |
| **`gap-3`** | **SAME function** — different components of one group | items of one kind in a list · **the gap INSIDE a card** · header ↔ meta-row | 423 |
| **`gap-6`** | **DIFFERENT function** — two unrelated blocks | **section ↔ section · card ↔ card** · grid of cards · header ↔ body · form ↔ aside | 197 |

`gap-4` = one roomy single group (rare — 36). Default to `0 / 2 / 3 / 6`.

> **The one question that decides it:** *"Are these two the SAME function or DIFFERENT?"*
> Same group → **`gap-3`**. Different blocks → **`gap-6`**. (`space-y-*`/`space-x-*` use the exact same scale.)

## DO
- title + description → `gap-0`
- label + input → `gap-2`
- a list of cards / a stack of sections → `gap-6` (`flex flex-col gap-6`, `grid gap-6`)
- the contents inside one card → `gap-3` (`flex flex-col gap-3 … p-6`)

## DON'T (off-scale → snap out)
- **`gap-1.5` → `gap-2`** (194 uses — the #1 cleanup)
- `gap-1` → `gap-2` · `gap-5` → `gap-6` · `gap-2.5` / `gap-0.5` → nearest step
- faking a gap with `margin` on children (use the flex/grid `gap`)

## VIOLATION (what `/starci-fe-layout-apply` flags)
any `gap`/`space` not in `{0,2,3,4,6}`; `gap-3` between two unrelated sections (→ `6`); `gap-6` inside one
card (→ `3`); `gap-2` where it's actually two different blocks (→ `6`).
