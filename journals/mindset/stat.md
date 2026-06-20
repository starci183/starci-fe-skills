# Mindset — stat

When & WHY we choose/shape the **stat** block. A decision log: for a given scenario, which component we
picked and the reasoning — so next time we design a stat, we reuse the house's logic instead of guessing.
Metrics, progress, charts, roadmaps.

**StarCi blocks in this family:** `MetricCard`, `ProgressMeter`, `StatPair`, `SegmentBar`, `LanguageDonut`, `MilestoneRoadmap`

> Grows automatically: at the END of each `/starci-fe-ux-apply`, the decision for this block (scenario →
> choice → why) is appended below. No manual command.

## Design baseline (from rules + design — 2026-06-21)

- **Metric row (KPI):** row of `MetricCard` in `grid grid-cols-2 gap-3 sm:grid-cols-4` (large value + muted label). Not a big hero `StatPair` for multi-cell KPIs. **MetricCard sits TOP-LEVEL, NOT inside `LabeledCard`** (no card-in-card); breakdown cards go below. Optional cells (rank/percentile/xp) auto-hide when null (push to the stats array only when `!= null`). Use `MetricCard.hint` to spell out ambiguous short labels. `StatPair` has `size` (`md`=h4 default, `lg`=h2) for hero numbers elsewhere. Merge count + breakdown of the SAME dataset into one card ("N items, split by X").
- **`SegmentBar` / `Legend`:** `SegmentBar` = multi-slice ratio bar + legend (dot + label + count). Slice color = **data-driven `color = var(--…)` token, NOT hex**. Skeleton = `Skeleton.SegmentBar legendItems={n}` (incl. legend). Progress vs total → set `max={total}`, remainder = `bg-default` track, summary `{done}/{total}`. Many bars sharing one scale in a card → ONE shared `Legend` at the bottom (`hideLegend` per bar); a lone bar renders its own. `Legend` block (`blocks/stats/Legend`): `items: Array<{key,label,color}>`.
- **Categorical breakdown → `SegmentBar`, AVOID pie/donut (STRICT):** part-to-whole (language, difficulty, status) → `SegmentBar` (horizontal 100% + `label · count` legend) or ranked bar-per-row. Reason: eyes compare length/position > angle/area (Cleveland–McGill); CSS bar is light + token-driven + dark-mode correct, no chart lib. By number of categories: few FIXED buckets (difficulty 4, a few langs) → `SegmentBar`; OPEN/large set (topic/tag/skill, 10–20+) → chip/tag-cloud with count (LeetCode/GitHub style), NOT a stacked bar (slivers like confetti). Metadata chips = neutral/`--default`, NOT accent; print the count clearly (don't rely on color, a11y). Donut only when very few categories AND a single center total is the main point (rare); `LanguageDonut` block kept for legacy (thickness = px via `thickness`, default 8 = h-2; `size` ~128) but not the default.
- **Difficulty color scale (4 data-driven tones):** easy → `var(--success)` · medium → `var(--warning)` · hard → `var(--danger)` · insane/expert → `var(--difficulty-insane)` (purple token, light+dark). Used for difficulty SegmentBar/bar via `color`. `DifficultyChip` maps insane→`accent` (enum can't take an arbitrary token) so chip ≠ bar purple — accepted divergence. Score color bands: `≥90 → text-success` · `≥70 → text-warning` · `<70 → text-danger`.
- **Language (GitHub style):** chip = `LanguageChip` (brand dot + name, no box). Single source of color/name = `src/modules/utils/language.ts` (`getLanguageColor`/`getLanguageLabel`; GitHub-linguist colors; `csharp→C#`, `cpp→C++`, `php→PHP`). Brand colors = valid "no hex" exception, kept in `language.ts` not globals. "By language" breakdown = `SegmentBar`, not donut.
- **Snapshot/teaser stays in sync with the full tab:** SAME metric → SAME chart + SAME legend (label + color) everywhere; snapshot inherits the full tab's viz (just leaner), never picks its own chart/label/color. When editing a metric viz, grep EVERY render site (snapshot + tab + overview) and sync.
- **Community comparison:** percentile ("hơn X% học viên") + rank #N (`userCodingRank`/`userChallengeStrength`) as metric cells. BE = derived metric (path A): add to projection, return `{percentile, rank, xp}`, don't touch points/XP/league. **XP ≠ sum of raw `score`** — real XP = ledger `xp_histories.amount` from BE, never summed on FE.
- **Badge/achievement:** meta = ONE line `{rank} · {secondary}` (`·`-separated). Earned → `{rank}` in data-driven ring color (`getRank().ring`) · `{rarityPercent}%` muted; locked → `currentValue/threshold` muted. Same for tooltip. Wall density: mascot ~48 (not 64), grid `gap-4`, cell ~`minmax(72px,1fr)`.
- **Consistency (STRICT):** 3 dot+label spots (difficulty legend, donut legend, `LanguageChip`) must share size: dot `size-3` + label `body-xs` muted. One highlighted color per cluster, rest muted. Skeleton mirrors the real layout.

## Decisions (newest first)
_(empty — each entry: **scenario** · **chose what** · **WHY** · which page · date)_

## Gotchas
_(empty)_
