# Decision — overlay (modal · drawer · popover)

When & WHY we shape the overlay shell (Modal / Drawer / anchored Popover). A decision log so the next
overlay reuses the house's logic instead of guessing.

**StarCi shells:** HeroUI `Modal` (mounted in `ModalContainer`), `Drawer` (in `DrawerContainer`), `Popover`
(anchored). The shell rules live in `../cannon/CONTENT.md` SLICE 5.8.

## Decisions (newest first)

### 2026-06-21 — unified shell, NO header divider
- **Scenario:** Drawer and Modal looked different — the Drawer had a `border-b` line between header and body
  (cannon 5.8 mandated it), the Modal didn't. The same line showed up in the new content-AI chat popover.
- **Chose (direction A):** **one shell for both, NO divider.** Header (`CloseTrigger` + title via
  `Modal.Heading` / `Drawer.Heading`) ↔ body separated by **whitespace only** (header-wrapper padding + body
  padding). Removed `<div className="border-b" />` from all 6 drawers + the chat popover header.
- **WHY:** thầy chốt A — khớp gu nhà "content-first, whitespace > divider, design restraint"; modal + drawer
  giờ đồng bộ. Ref: modern modals (Linear / Vercel / Stripe) tách bằng khoảng trắng, không kẻ đường header.
- **Files:** `drawers/{ContentAiChatDrawer, E2eResultDrawer, MindMapContentDetailsDrawer,
  PersonalProjectTaskAttemptsDrawer, SubmissionAttemptsDrawer, UserCvSubmissionAttemptsDrawer}/index.tsx`,
  `features/learn/ContentAiFab/index.tsx` (popover header); `cannon/CONTENT.md` SLICE 5.8 updated.
- **Scope kept:** the 3 modal `border-b` left in place (`FeedbackCardSkeleton`, `GlobalSearchModal`
  input↔results, `MilestoneFeedbackCard`) — those are CONTENT dividers inside the body, not the header→body
  shell line.

## Gotchas
- An "overlay header divider" = a `border-b` line between header and body. Don't add one (cannon 5.8). For a
  scrollable body that needs a "stuck header" cue, use HeroUI `ScrollShadow` on the body (shadow appears only
  on scroll) — never a static line.
