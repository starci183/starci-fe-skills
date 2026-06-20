# Mindset — chip

When & WHY we choose/shape the **chip** block. A decision log: for a given scenario, which component we
picked and the reasoning — so next time we design a chip, we reuse the house's logic instead of guessing.
Status/difficulty/language chips.

**StarCi blocks in this family:** `StatusChip`, `DifficultyChip`, `LanguageChip`

> Grows automatically: at the END of each `/starci-fe-ux-apply`, the decision for this block (scenario →
> choice → why) is appended below. No manual command.

## Design baseline (from rules + design — 2026-06-21)

- **Core principle: a chip is ONE SOFT COLOR BLOCK, no border.** Soft tint background of one color, text + dot/icon in the same color but darker. NEVER use `border` to draw a chip (that reads as "outline", noisy). Separate by tint + text color, not by lines.
  - Formula: `bg = color @ 10%` · `text = color @ 100%` · `dot = color @ 100%` · `border = none`.
- **Token colors (success/danger/warning/accent/default) → HeroUI `Chip variant="soft"`** via existing blocks, don't hand-roll:
  - `StatusChip tone="success|danger|warning|accent|neutral"` — wraps `Chip color={token} variant="soft"` + `Chip.Label` (soft = tint bg + matching text, auto no border).
  - `DifficultyChip` — beginner/intermediate/advanced/**insane** (insane → `accent` because Chip `color` is an enum; the data-driven difficulty BAR uses purple `--difficulty-insane` instead — accepted divergence).
  - Need a new token chip → add a tone to those blocks, never `<span className="border …">` in a feature.
- **Programming language → `LanguageChip`** (`blocks/chips/LanguageChip`), GitHub-style: **brand dot + name, NO bg/box**. NOT `StatusChip`/pill. Color/name from `src/modules/utils/language.ts` (`getLanguageColor`/`getLanguageLabel`; `csharp→C#`, `cpp→C++`). Brand color = valid "no hex" exception (external brand identity), kept in `language.ts`, not globals tokens.
- **Runtime hex color (rank tier — gray/bronze/silver/gold, dynamic outside tokens)** → can't force into `Chip color`; build a span in a reuseable (pattern `RankBadge`) mimicking soft: `backgroundColor: color-mix(in srgb, ${color} 10%, transparent)`, `color`, dot `bg = color`. `color-mix` works for ANY color string (hex 3/6/8, rgb…) where Tailwind `bg-[..]/10` only builds with literals. Still no border.
- **Default look (design inventory):** `Chip` + `Chip.Label`, usually `size="sm" variant="soft" color="accent"` (or `color="danger"` for disabled). Accent chip = `color="accent" variant="soft"`.
- **Accent is for ACTION:** metadata chips (topic/tag/skill) = neutral/`--default`, NOT accent (accent on data is noise).

## Decisions (newest first)
_(empty — each entry: **scenario** · **chose what** · **WHY** · which page · date)_

## Gotchas
_(empty)_
