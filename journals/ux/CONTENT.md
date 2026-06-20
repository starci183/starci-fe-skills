# journals/ux/ — page-level UX decisions + UX patterns (fetched live from the web)

Two things live here (the old separate `refs/` is folded in):
1. **Per-page UX decisions** — the layout/flow we settled on for a page, and why.
2. **UX pattern lessons** — what the best course websites do, **fetched LIVE from the web** during
   brainstorm; the durable takeaways accumulate here. No static teardowns.

## Design foundations (from the design system — 2026-06-21)
Distilled from the (now-deleted) design-system docs + `rules/main.md`. The house foundations — real values, grounded in code.

### North-star / mindset
- **Content-first, clean, lots of whitespace.** Big-radius cards, soft `default/40` surfaces, secondary text `text-muted`.
- **Accent teal-green** (logo StarCi `#00a898` ≈ token `--accent`) for every emphasis: active link, chip, primary button, "Save %".
- **Light + Dark first-class** (`next-themes`, default **dark** + `enableSystem`). Every component must look right in both → use semantic tokens (`bg-default`, `text-foreground`), never hardcode color. No route forces a theme.
- **HeroUI v3 first** (`@heroui/react` + `@heroui/styles`) — don't hand-roll primitives. Icons: Phosphor `*Icon` (`weight="duotone"`); brand logos `react-icons/fa6`.
- **Constraints liberate:** lock the choices (fixed variants, 5-step spacing, 3 radii) → less dithering, faster + prettier. **Design in GRAY first** (layout + hierarchy before color); one primary action per screen.
- **Each decision lives in exactly ONE layer; style flows one way — features only COMPOSE, never paint.** 4 layers: Tokens (`globals.css`) → HeroUI + globals → Blocks (own all style, props-only) → Features (read store/SWR, placement classes only).
- **Empty/Loading/Error are real states**, designed from the start (every fetch → `AsyncContent`). **Text IS the interface** — clear labels beat pretty icons. **Consistency > cleverness; a11y is #1** (contrast ≥4.5:1, focus ring, touch ≥44px).

### Design tokens (oklch, from `globals.css`)
| Token | Light | Dark | Use |
|---|---|---|---|
| `--accent` | `oklch(62.04% 0.1950 185.90)` | (same) | Brand teal-green ≈ logo `#00a898`; links/chips/primary/"Save %" |
| `--accent-foreground` | `oklch(99.11% 0 0)` | | Text on accent |
| `--background` | `oklch(97.02% 0.0033 185.90)` (off-white, teal-tinted) | `oklch(12% …)` | Page background |
| `--foreground` | `oklch(21.03% …)` | `oklch(99.11% …)` | Primary text → `text-foreground` |
| `--muted` | `oklch(55.17% …)` | | Secondary text → `text-muted` (⚠️ NOT `text-foreground-500`) |
| `--default` | `oklch(94% …)` | `oklch(27.40% …)` | Soft card/chip surface (`bg-default`, `bg-default/40`) |
| `--success` | `oklch(73.29% 0.1948 142.66)` | | Green state |
| `--danger` | `oklch(65.32% 0.2343 17.59)` | | Error/disabled |
| `--warning` | `oklch(78.19% 0.1595 64.18)` | | Callout / input-required |

- Neutrals share hue **185.90** (teal) → the whole app reads subtly teal. Logo `#00a898` (StarC teal) + `#6c8aa3` (slate "academy").
- **Difficulty palette:** Easy = cyan-500 · Medium = yellow-500 · Hard = red-500 · Insane = purple-500 (`--difficulty-insane`, light+dark).
- **Color rule:** chips/badges = soft color blocks, NO border (`variant="soft"` / `bg-[c]/10` + same-color text). Categorical colors map to success/warning/danger/accent. Language brand colors are the one valid "no-hex" exception (`modules/utils/language.ts`).

### Radius & spacing
- **Radius:** form/modal container `rounded-3xl`; content card `rounded-xl`; code block `rounded-xl`; chip/pill `rounded-full`. Concentric `rounded-2xl` (frame) → `rounded-xl` (field) → `rounded-full`; child < parent; components don't hand-roll frame radius. Tokens: `--radius: 0.5rem`, `--field-radius: 0.75rem`. Shadow is flat (overlay only).
- **Spacing scale `0 / 2 / 3 / 4 / 6`** (4px grid, gap AND padding — `gap-1.5`/`gap-1`/`p-1/5/8/11` banned). Pick by **semantic relationship**, not size feel:
  - `0` — one tight block.
  - `2` — coupled (icon↔text, label↔input).
  - `3` — same function (items of one kind, gap inside a card).
  - `4` — roomy container.
  - `6` — different function (text block↔CTA, section↔section, card↔card, section padding).
- Page shell padding `p-3`; container `max-w-[1280px] mx-auto`; section `gap-6`; page-level gutters `gap-8/10/12` (exception). Card padding `px-4 py-3` fixed (in `.card` globals). Vertical scroll regions → HeroUI `ScrollShadow`, not raw `overflow-y-auto`.

### Typography (Open Sans; type scale)
Font is **Open Sans** (`next/font`). ⚠️ Known drift: `globals.css` sets `--font-sans: var(--font-inter)` but `--font-inter` is undefined → empty font var; the old doc said "Inter" (wrong). Per-role canonical classes (map to HeroUI `Typography type`):

| Role | Class | Notes |
|---|---|---|
| Display / page hero | `text-4xl font-bold` | `text-3xl md:text-4xl` on mobile |
| Subpage / modal title | `text-2xl font-bold` | |
| Section heading | `text-lg font-semibold` | ONE spec |
| Card / sub heading | `text-base font-semibold text-foreground` | → HeroUI `Label` for sub-section labels |
| Body | `text-sm` | default text |
| Description / muted | `text-sm text-muted` | canonical muted = `text-muted` (⚠️ `text-foreground-500/400/600` don't exist in the project) |
| Label / eyebrow | `text-xs text-muted` | **normal case**, not all-caps; uppercase only for a deliberate accent badge |
| Meta / hint / chip | `text-xs text-muted` | |

Weights: title `bold`, heading/card `semibold`, sub-label/price `medium`. No thin/light/extrabold. In code, prefer HeroUI `Typography` (`type` ∈ `body|body-sm|body-xs|code|h1..h6`, `color` only `default|muted`) over `<div>`+text classes; `PageHeader` title = `Heading level={3} weight="bold"`.

### Page recipe + 3-tier layout law
To build a page that looks native: (1) pick the nearest **archetype** (Course detail / Course learn / Challenge split); (2) reuse the frame — `max-w-[1280px]` container, `grid md:grid-cols-5` (3/2) or `grid-cols-4` (sidebar), breadcrumbs on top; (3) build with **HeroUI v3**, no hand-rolled primitives; (4) semantic tokens only (`bg-default/40`, `text-muted`, `color="accent"`) — looks good in both themes; (5) reuse patterns (count/meta-chip `Chip size="sm" variant="soft" color="accent"` + Phosphor icon; outline rail active = `text-accent bg-accent/10`; price VND primary + USD `text-muted` secondary; `MarkdownContent` + Shiki); (6) i18n every string (next-intl), no hardcoded text; (7) data via GraphQL `query-*`/`mutation-*` + singleton SWR hook. **Don't:** hardcode hex, hand-roll button/modal/accordion, hardcode copy, px-locked layout, or forget the dark state.

**3-tier content layout (law):** every content page = Breadcrumb → Header (`Heading level={3}` H3 + description `body-sm muted`, via block `PageHeader`) → Content. Same `h-3` spacer between tiers + same `gap-3` within a tier; all three tiers share one width cap (`max-w-3xl` for reading columns) + `mx-auto` so they align left. Personal home/profile pages instead use the 2-column shell (bare identity left, `LabeledCard` sections right) — NOT a 3-rail layout.

### Form & tooltip conventions
- **Forms:** `TextField` children must be valid slots — descriptions/counters/hints use `slot="description"` (never a bare `<Typography>`/`<div>`, React Aria throws). Checkbox = HeroUI `Checkbox` compound (no bare `<input>`). Small 1-of-few selectors = `Select` dropdown (`w-fit min-w-48`) or `Tabs variant="primary"` — NEVER a row of pill buttons. Single-cluster form sections stay flat (no extra `Card`). Save button = `self-start` (width hugs text), not `fullWidth`. Image/avatar upload = block `ImageDropzone` opened in a modal via a zustand overlay store.
- **Secrets** (API key/token): encrypted at rest in BE, plaintext never returned to FE; input is write-only (`type="password"`, no prefill); stored value shown masked `••••{last4}` (BE returns a `*_last4` column) with "Replace"/"Remove" actions — no "reveal" button.
- **Tooltips:** for any hard term (rank, tier, KPI, streak, league, p99…) use block `InfoTooltip` (never raw HeroUI `Tooltip` in a feature). Content is plain-language, 1–3 sentences, **personalized when data allows** ("why YOU are at this level" + "what's needed to level up") over generic definitions; text via i18n. `Tooltip.Content` already pads — no extra `p-*` wrapper.

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

> Sibling: `journals/mindset/<block>.md` (per-component decision logs). Code rules: `../../cannon/CONTENT.md`.
