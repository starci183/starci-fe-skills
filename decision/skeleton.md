# Decision — skeleton

When & WHY we choose/shape the **skeleton** block. A decision log: for a given scenario, which component we
picked and the reasoning — so next time we design a skeleton, we reuse the house's logic instead of guessing.
Skeleton loaders.

**StarCi blocks in this family:** `Skeleton`, `CourseCardSkeleton`

> Grows automatically: at the END of each `/starci-fe-ux-apply`, the decision for this block (scenario →
> choice → why) is appended below. No manual command.

## Design baseline (from rules + design — 2026-06-21)

Distilled from `06-skeleton.md`.

**Primitive**
- Only HeroUI `Skeleton` (`import { Skeleton } from "@heroui/react"`, v3), called with `className` only (don't use the `isLoaded` / wrap-children API). No shared skeleton wrapper in the repo.
- Each feature writes its own `XSkeleton/index.tsx` next to the real component, MIRRORING the real layout (same size, rounded, spacing) so nothing jumps when data lands. Name `*Skeleton` (not `LoadingState`); export via barrel.
- No `loading.tsx` (App Router) anywhere → no instant skeleton on navigation; loading is handled client-side after hydrate. (Canonical suggestion: consider route-level `loading.tsx` for heavy pages like learn/content.)

**When skeleton shows = a CODE pattern, not a UI choice** — show iff `isLoading || !data || error` (NOT `isValidating`). The skeleton doc only governs SHAPE. Many rows via `Array.from({ length: N }).map(...)` or a `count` prop (e.g. `ModulesSkeleton`).

**Breadcrumb + header are NOT skeleton-ized.** Static chrome (breadcrumbs, page header) depends on i18n/router, not SWR data → render real, outside the gate, immediately. So `XSkeleton` mirrors ONLY the content (grid/list/detail), never breadcrumb/header skeletons.

**Shape metric — skeleton bar height = font-size**, leftover line-height split evenly into `my` (top+bottom) to fill the real text line-box. `h = font-size`, `my = (line-height − font-size) / 2` (1rem = 16px). Examples: `text-sm` → `h-[14px] my-[3px] rounded-sm`; `text-base` → `h-[16px] my-[4px] rounded`; `text-2xl` → `h-[24px] my-[4px] rounded`; `text-4xl` → `h-[36px] my-[2px] rounded`.
- Text lines = `rounded-sm` (xs/sm) or `rounded` (base+) — NEVER `rounded-full` for text. `rounded-full` is ONLY for pill/avatar/badge; `rounded-xl` for card/image.
- Component: `components/reuseable/SkeletonText` (wraps HeroUI `Skeleton`, takes `size` token + `width` class, default `w-full`); `SkeletonParagraph` = N lines with descending width (default 3 = `w-full` / `w-3/4` / `w-1/2`, last line shortest). Match typography: use the same `size` as the text it replaces (title `text-2xl` → `size="2xl"`).
- Use a `Spinner` ONLY for short actions (button mid-submit, mutation), NEVER for loading page/list content.

**Mirror, don't blob.** Copy the real container's class (best example: `MilestoneSidebar/MilestoneSidebarSkeleton` copies `lg:sticky lg:top-16…`). Good copies: `Course/Modules/ModulesSkeleton` (rebuilds the whole `Accordion` + `count` prop), `Content/ChallengeBody/ChallengeCardSkeleton`. Avoid coarse single-block skeletons (`h-48`/`h-64`) when content can be mirrored.

**Content/learn archetype** — `isLoading = useQueryContentSwr().isLoading || !content`; while loading render `ContentHeaderSkeleton` + the REAL `ContentTabBar` (tab bar shows immediately) + a body placeholder; each tab body keeps its own loading branch (ContentBody Skeleton rows, ChallengeBody `ChallengeCardSkeleton`×2, LessonBody `LessonCardSkeleton`).

**Known gaps to fix when touched** — raw `animate-pulse` divs → `Skeleton` (Content/Code*Body, attempt drawers); `Spinner` → skeleton in list/detail (Practice, Quiz tabs); `ModuleSidebar` renders empty `ModuleAccordion modules={[]}` → use `ModulesSkeleton`; `rounded-*` drift in skeletons → follow canonical radius. (Intentional `animate-pulse` in `AIProcessing*` / `MethodologySection` stays.)

## Decisions (newest first)

### 2026-06-21 — Skeletons for content + personal-project; "draw the widget FIRST" rule
- **Scenario:** teacher: "skeleton cho trang content và personal project" + "update rules là skeleton apply
  **phải vẽ widget**". Recon: LessonReader (content) already mirrors well (Header/Body/Challenge/Code
  skeletons via inline ternary — the endorsed *content archetype*); PersonalProject only had a left-column
  `TaskSkeleton`, the right panel popped in unskeletoned.
- **Rule change (the headline):** `starci-fe-skeleton-apply` SKILL.md now has a **Step 1 — draw a widget
  mockup of the skeleton FIRST** (`show_widget`, module `mockup`) before writing any `*Skeleton`. The widget
  is the reviewable artifact of the loading shape — same role the layout widget plays in
  `/starci-fe-ux-brainstorm`. Renumbered scope/apply→Step 2, report→Step 3; description updated.
- **Content fix (ChallengeBody):** gate was `isLoading || isValidating` → **dropped `isValidating`** (gate =
  `queryChallengesSwr.isLoading` only). WHY: the known law — a background revalidate on page change kept
  flashing the 2 `ChallengeCardSkeleton`s over the current cards; first-load-only gate keeps them on screen.
- **Personal-project (the real gap):** `TaskResults` returned `null` until the latest attempt landed → a
  pop-in. **Chose:** wrap it in **`AsyncContent`** (`isLoading={attemptsSwr.isLoading}`,
  `skeleton={<TaskResultsSkeleton/>}`, `isEmpty={!latestAttempt}` → self-hides when the learner has no
  attempt). New **`TaskResultsSkeleton`** mirrors 1:1: title row (`base` label + AI-badge pill) +
  `rounded-3xl bg-default/40` surface holding a `text-4xl` score bar + 2 feedback lines. Also rebuilt
  **`TaskSkeleton`** to mirror the real `Task`: dropped the stray leading `<Separator/>` + `bg-surface`
  criteria block (didn't match V2); now `gap-6` → (H3 `2xl` title + 2 `sm` desc lines) + a `h-[220px]
  rounded-xl` brief card.
- **AsyncContent vs inline:** used `AsyncContent` for the NEW region (law-compliant, matches
  `careers/.../ConsultantGrid` usage); left the content page's established **inline ternary archetype**
  untouched (the decision baseline endorses it for content). Full content→AsyncContent migration = a
  separate, larger follow-up, not this scoped pass.
- **Files:** `LessonReader/ChallengeBody/index.tsx`; `PersonalProject/TaskResults/index.tsx` (+ `AsyncContent`
  wrap, `latestAttempt?.score` guard); NEW `PersonalProject/TaskResultsSkeleton/index.tsx`;
  `PersonalProject/TaskSkeleton/index.tsx` (rebuilt). Skill: `skills/starci-fe-skeleton-apply/SKILL.md`.
- **Verify:** eslint EXIT 0 on all four. Route is auth+enrollment-gated → not browser-verified here (cwd is
  the backend repo); shape confirmed against the real components + the widget mockup.

## Gotchas
- **`AsyncContent` children are built eagerly.** The `children` JSX is constructed *before* `AsyncContent`
  decides which branch to render — so any field access inside it runs even while `isLoading`/`isEmpty`. Guard
  optional data (`latestAttempt?.score`, not `latestAttempt.score`) or it throws during the loading/empty
  render. Same trap as any conditional-render wrapper that takes children as a prop, not a render-fn.
