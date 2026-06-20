# Mindset — accordion

When & WHY we choose/shape the **accordion** block. A decision log: for a given scenario, which component we
picked and the reasoning — so next time we design a accordion, we reuse the house's logic instead of guessing.
Collapsible/disclosure rows.

**StarCi blocks in this family:** `ContentMapRow` + HeroUI `Accordion`

> Grows automatically: at the END of each `/starci-fe-ux-apply`, the decision for this block (scenario →
> choice → why) is appended below. No manual command.

## Design baseline (from rules + design — 2026-06-21)

Distilled from `starci-navigation.md` (collapse-in-place law), `03-layout-archetypes.md` (curriculum/requirements accordions), and `07-modals.md` (joined-list pattern that accordions share).

**Collapse animates IN PLACE — never a Drawer.**
- A panel that collapses/expands (sidebar collapse, accordion/disclosure) animates in place via framer-motion; surrounding content reflows. A `Drawer` is ONLY for a context-separating overlay that covers content. Apply at every breakpoint and respect `useReducedMotion`.

**Where accordions appear (archetypes)**
- Course-detail left column: `Accordion` curriculum, each row + a count-chip (e.g. `12/8/3`). (`layouts/Course`, archetype A.)
- Challenge-detail: "Yêu cầu" (requirements) collapse into an `Accordion`. (`modals/ChallengeModal`, archetype C.)
- Module sidebar: built from `ModuleAccordion` / `ModulesSkeleton` (mirrors the accordion when loading — see skeleton journal).
- General: content gets gathered into rounded `Card` / `Accordion` containers; the grid only splits at a breakpoint (`md:` / `lg:`), mobile stacks vertically.

**Joined-list shape (shared with modals)** — when an accordion/group renders a list of options, bind them: round the OUTER edge (`overflow-hidden rounded-large`), items `rounded-none` + `Separator` between — NOT separate cards with gaps.

**Controlled when progress/auto-open is needed** (from the `one-progress-bar-at-a-time` draft): an accordion that shows one progress bar only for the OPEN group (collapsed groups show muted "n/m") must be controlled (`expandedKeys` / `onExpandedChange`, react-aria DisclosureGroup) so it knows which group is open; auto-open the group holding the active item; search opens every matching group.

## Decisions (newest first)
_(empty — each entry: **scenario** · **chose what** · **WHY** · which page · date)_

## Gotchas
_(empty)_
