# design/ — page-level UX: layout, flow + UX patterns (fetched live from the web)

What lives here:
1. **Per-page UX decisions** — the layout/flow we settled on for a page, and why.
2. **Layout foundations** — the page recipe + the 3-tier law (how a page is composed).
3. **UX pattern lessons** — what the best course websites do, **fetched LIVE from the web** during
   brainstorm; the durable takeaways accumulate here. No static teardowns.

Siblings: `../ui/CONTENT.md` (the visual system — tokens/typography/spacing), `../decision/<block>.md`
(per-block decision logs), `../../cannon/CONTENT.md` (code rules).

## Layout foundations (page recipe + 3-tier law — from the design system)
To build a page that looks native: (1) pick the nearest **archetype** (Course detail / Course learn /
Challenge split); (2) reuse the frame — `max-w-[1280px]` container, `grid md:grid-cols-5` (3/2) or
`grid-cols-4` (sidebar), breadcrumbs on top; (3) build with **HeroUI v3**, no hand-rolled primitives;
(4) semantic tokens only (`bg-default/40`, `text-muted`, `color="accent"`) — good in both themes;
(5) reuse patterns (count/meta-chip `Chip size="sm" variant="soft" color="accent"` + Phosphor icon; outline
rail active = `text-accent bg-accent/10`; price VND primary + USD `text-muted` secondary; `MarkdownContent` +
Shiki); (6) i18n every string (next-intl); (7) data via GraphQL `query-*`/`mutation-*` + SWR hook.
**Don't:** hardcode hex, hand-roll button/modal/accordion, hardcode copy, px-locked layout, or forget dark.

**3-tier content layout (law):** every content page = Breadcrumb → Header (`Heading level={3}` H3 +
description `body-sm muted`, via block `PageHeader`) → Content. Same `h-3` spacer between tiers + same
`gap-3` within a tier; all three tiers share one width cap (`max-w-3xl` for reading columns) + `mx-auto` so
they align left. Personal home/profile pages instead use the 2-column shell (bare identity left,
`LabeledCard` sections right) — NOT a 3-rail layout.

## Per-page decisions
`<page>.md` (e.g. `lesson-reader.md`, `dashboard.md`) — the archetype chosen, the section order, the flow,
and **why**. Added/updated automatically at the end of `/starci-fe-ux-apply`.

## UX pattern lessons (from the web)
During brainstorm: **read this section first**, then `WebSearch`/`WebFetch` only what's missing, and append
the new lesson here at the end of the task.

### Which platforms to fetch, by page type
| Page type | Fetch |
|---|---|
| Catalog / discovery / cards | Coursera, Udemy, Skillshare |
| Lesson reader / player / code editor | Codecademy, Udemy, Khan Academy, Frontend Masters |
| Gamification (XP/streak/league/badge) | Duolingo, Brilliant, Khan Academy |
| Onboarding / activation | Duolingo, Codecademy |
| Pricing / paywall / upgrade | Coursera, Brilliant, Duolingo |
| Dashboard / home / mobile | Codecademy, Coursera |
| Trust / certificate / serious-dev tone | edX, Frontend Masters, freeCodeCamp |

### Accumulated lessons
_(empty — each: pattern · who does it well · the takeaway for StarCi · what NOT to copy · source URL · date)_
