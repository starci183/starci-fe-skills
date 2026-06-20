# Decision — sidebar

When & WHY we choose/shape the **sidebar** block. A decision log: for a given scenario, which component we
picked and the reasoning — so next time we design a sidebar, we reuse the house's logic instead of guessing.
Collapsible nav rail + its groups/items.

**StarCi blocks in this family:** `CollapsibleSidebar`, `SidebarNavGroup`, `SidebarNavItem`

> Grows automatically: at the END of each `/starci-fe-ux-apply`, the decision for this block (scenario →
> choice → why) is appended below. No manual command.

## Design baseline (from rules + design — 2026-06-21)

Distilled from `starci-navigation.md` + `03-layout-archetypes.md`.

**Nav row primitive**
- Each nav/menu/sidebar row = HeroUI `Link` (`onPress` for client-route / `href`) — text-with-action = Link. NEVER wrap each row in a 1-item `ListBox selectionMode="single"` + single `ListBox.Item`.
- Why: `ListBox.Item` carries its own hover/focus/selected grey chrome (`bg-default`); a focused/hovered item shows grey that competes with the accent active highlight → "fake consistency" (looks clean only because nothing is focused yet). Wrong primitive drags its own state chrome along.
- The ONLY filled state = `isActive` → `bg-accent/10 text-accent`. Hover = faint tint `hover:bg-default/40`; focus = ring `focus-visible:outline`, NOT a fill. Don't let the primitive add its own selected/focus fill.
- A real `ListBox` is only for ONE multi-select list → one `ListBox` wraps ALL items (+`Section`); don't split into one-listbox-per-row.
- Block: `blocks/navigation/SidebarNavItem` (Link, only-active-filled).

**Collapsible rail (block `CollapsibleSidebar`)**
- Collapse = ICON-ONLY rail (ALWAYS render nav, never unmount): item drops label, keeps centered icon, `aria-label` keeps a11y. Collapsed item = `p-0!` (override HeroUI `list-box-item` padding recipe so icon sits flush — same specificity needs `!`, Tailwind v4 suffix `!`).
- Collapse state shared down to rows via block-family React context (`CollapsibleSidebar/context` → `useSidebarCollapsed`) — block-internal chrome, NOT a store. Collapsed row → `justify-center gap-0`, drop label.
- Separate groups with FULL-WIDTH `Separator` (`SidebarNavGroup divider`), NOT an uppercase caption group-label as the divider. Group label = optional, hidden when collapsed.
- A 1-item group does NOT get its own divider (looks like crumbs) → merge stray items into one trailing group (e.g. bookmarks + membership).
- Rail width ≥4rem (icon centering); padding shrinks on collapse (`pr-2` vs `pr-6`).
- Collapse/expand animates IN PLACE via framer-motion (NOT a Drawer — Drawer is only for context-separating overlays that cover content); respect `useReducedMotion`; persist to localStorage.

**Shell "sidebar + content" = ONE scroll context, sidebar STICKY**
- One page = one scroll context = body/page. App-shell (`InnerLayout`) already lets the body scroll → do NOT build a viewport-locked region (`h-[calc(100dvh-…)] overflow-hidden`) with an inner `overflow-y-auto` pane. Two nested scroll containers = overscroll-chain / jitter (esp. trackpad); excess body height = stray scrollbar.
- Sidebar = `position: sticky`, NOT own-scroll of the whole region: `shrink-0 md:sticky md:top-16 md:h-[calc(100dvh-4rem)]` (sticks below the 4rem navbar). Content `flex-1` floats in page scroll (no own `overflow`). If the nav itself is longer than the viewport → scroll just the nav internally via `ScrollShadow`, don't lock the whole page. (GitHub/Linear settings pattern.)

**No per-page back arrow when sidebar + breadcrumb exist**
- A page inside a layout WITH sidebar + breadcrumb → do NOT add a per-page back arrow. Header = just title + subtitle (`Typography`). One clear escape beats two duplicates (back "to Profile" ≡ the breadcrumb's "Profile" link).
- Per-page back only fits a linear flow WITHOUT a sidebar (or mobile when sidebar is hidden). If truly needed: `onBack` → a FIXED parent (not `router.back()`) + clear `aria-label`, and drop the breadcrumb to avoid duplication.
- `reuseable/SubPageHeader` = LEGACY broken-rule (`@gravity-ui`, `<div>+text-class`, `gap-1.5`) → replace with a clean block when touched, eventually delete.

**Learn-shell sidebar (archetype B)** — `ListBox` + `ScrollShadow`, active row `text-accent bg-accent/10`; this view often renders dark.

## Decisions (newest first)
_(empty — each entry: **scenario** · **chose what** · **WHY** · which page · date)_

## Gotchas
_(empty)_
