# Journal — per-block design knowledge that compounds

This folder LEARNS how to design every **block** in the StarCi system. **One file per block family,
`journal-<block>.md`** (card, sidebar, accordion, tabs, chip, …) holding the accumulated design knowledge
for that block — what we choose, why, the gotchas — GROWN from thầy's feedback during
`/starci-fe-ux-apply`, brainstorms, and reviews.

Three layers, don't confuse them:
| Layer | Where | Kind |
|---|---|---|
| Code rules | [`../cannon/CONTENT.md`](../cannon/CONTENT.md) | hard "you MUST" code law |
| Element styling | [`../rules/`](../rules/) | how to style a HeroUI element |
| **Block design (this)** | `journal-<block>.md` | **how we DESIGN/compose a block — learned taste** |

## Files (one per block family)
| File | Block family (`src/components/blocks/…`) |
|---|---|
| [`journal-card.md`](journal-card.md) | cards — Course/Pricing/Media/Continue/Labeled/Flip/Pressable |
| [`journal-sidebar.md`](journal-sidebar.md) | navigation — CollapsibleSidebar + groups/items |
| [`journal-tabs.md`](journal-tabs.md) | navigation — TabsCard / ExtendedTabs |
| [`journal-accordion.md`](journal-accordion.md) | navigation — ContentMapRow + HeroUI Accordion |
| [`journal-chip.md`](journal-chip.md) | chips — Status/Difficulty/Language |
| [`journal-button.md`](journal-button.md) | buttons — FAB / Rating / InputButtonLike |
| [`journal-list.md`](journal-list.md) | lists — ListRow / PaginatedList |
| [`journal-feed.md`](journal-feed.md) | feed — Activity/Chat/Timeline/Reaction |
| [`journal-stat.md`](journal-stat.md) | stats — Metric/Progress/Chart/Roadmap |
| [`journal-page-header.md`](journal-page-header.md) | layout — PageHeader/Container/StickyBar |
| [`journal-empty-state.md`](journal-empty-state.md) | async + feedback — loading/empty/error |
| [`journal-skeleton.md`](journal-skeleton.md) | skeleton loaders |
| [`journal-avatar.md`](journal-avatar.md) | identity — avatars/user cells/uploads |
| [`journal-banner.md`](journal-banner.md) | marketing — heroes/pitch/manifesto |
| [`journal-media.md`](journal-media.md) | media — cover images |

> A new block in the system? Add a `journal-<block>.md`. Grounding: `src/components/blocks/`.

## How it grows (draft → merge)
1. Design a block / get thầy's feedback → capture the lesson.
2. Stage it in [`drafts/<name>.md`](drafts/), or add a dated entry straight into the right `journal-<block>.md`.
3. `/starci-fe-update-mindset` folds `drafts/` into the matching `journal-<block>.md` (**newest wins**), deletes the draft.
4. `/starci-fe-ux-brainstorm` + `/starci-fe-ux-apply` READ these, so each new design starts from the house's real taste — the skill gets smarter the more you use it.
