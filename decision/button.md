# Decision — button

When & WHY we choose/shape the **button** block. A decision log: for a given scenario, which component we
picked and the reasoning — so next time we design a button, we reuse the house's logic instead of guessing.
FAB / rating / input-like buttons.

**StarCi blocks in this family:** `FloatingActionButton`, `RatingBar`, `InputButtonLike`

> Grows automatically: at the END of each `/starci-fe-ux-apply`, the decision for this block (scenario →
> choice → why) is appended below. No manual command.

## Design baseline (from rules + design — 2026-06-21)

- **Variant = SEMANTICS, never hand-colored.** Color comes from the variant (which maps tokens per theme). Forbidden: color `className` (`bg-*`, `text-accent`…) to "recolor" a button.
  - `primary` — the ONE main forward action per context (Liên hệ tuyển dụng · Lưu · Nộp bài · Ghim).
  - `secondary` — equal-rank alternative (Follow · Chỉnh sửa · Xem tất cả).
  - `tertiary` — low-emphasis / icon-only in a bar (gear · bell · avatar trigger).
  - `ghost` — lightest, transparent bg (accordion toggle · button in list/popover/drawer · "Xem thêm").
  - `outline` — bordered, field/select style (filters · segmented).
  - `danger` — destructive (Xóa · Gỡ · Đăng xuất · Hủy đăng ký).
- **One `primary` per context / action cluster.** Everything else secondary/tertiary/ghost. Never two primaries side by side.
- **Order & placement:** dialog/form horizontal → secondary LEFT, primary RIGHT (`[Hủy (tertiary/ghost)] … [Xác nhận (primary)]`). Narrow column/sidebar/drawer vertical → primary on top, then secondary, then share/aux; use `fullWidth`. **Destructive separated from primary** (`danger` never adjacent to primary — push to other group or overflow menu; delete-account/logout always isolated).
- **Size & touch:** default `size="md"` (≥44px touch); `size="sm"` for aux in popover/row/header-action. Icon-only → `isIconOnly` + **mandatory `aria-label`**, hit-area ≥44px. Full-bleed → `fullWidth` prop (not ad-hoc `w-full`). **Save/submit in a WIDE settings form = SHORT** (`className="self-start"`, NOT `fullWidth`); fullWidth only for the main CTA in a narrow column/modal/card.
- **State:** button that calls a mutation/fetch → **`isPending`** (auto spinner + blocks double-submit); never a stateless button. Disable via `isDisabled`. Use **`onPress` (NOT `onClick`)**.
- **Icon:** phosphor `*Icon`, `aria-hidden focusable="false"`, BEFORE the label, `size-4`. Brand icons (GitHub…) = `@icons-pack/react-simple-icons`.
- **Anti-patterns (forbidden):** multiple primaries · danger next to primary · icon-only without `aria-label` · color via className · `<button>` from scratch (use HeroUI `Button`) · **a row of pill `Button`s as a SELECTOR** (use `Select`/`Tabs primary`) · `fullWidth` save in a wide settings form.

## Decisions (newest first)
_(empty — each entry: **scenario** · **chose what** · **WHY** · which page · date)_

## Gotchas
_(empty)_
