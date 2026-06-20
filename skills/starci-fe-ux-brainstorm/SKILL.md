---
name: starci-fe-ux-brainstorm
description: >
  Re-imagine / propose the UX of a StarCi Academy page from first principles. Two-phase: (1) read the
  page's CURRENT UX from the source app and PERSIST it to the app's `.claude/memory/ux/` so it's saved,
  not re-derived; (2) when a new layout is needed, propose it by combining that saved memory + the
  competitor `refs/` library + the StarCi design system — brainstorming layout, components, and
  functionality, and proposing MINOR backend tweaks (a GraphQL field/query/projection) when the UX goal
  needs data the backend doesn't yet expose. Five goal lenses: UX-only, marketing, strategic
  communication, component design, page layout. Output = a brainstorm doc + recommendation (+ widget
  mockup). NO production code (backend deltas are proposed, not written). Run with MAX effort (Opus).
  Trigger on `/starci-fe-ux-brainstorm`, "đề xuất layout", "brainstorm trang/layout", "thiết kế lại
  trang", "thiết kế component", "design layout", "bố cục trang", "nghĩ ux", "góc marketing trang".
---

# /starci-fe-ux-brainstorm — propose a StarCi layout from saved UX memory + course-UX refs (Opus · MAX effort)

Đề xuất / thiết kế LẠI một trang·khối·luồng của StarCi từ **first principles**, neo vào **3 nguồn**:
1. **UX HIỆN CÓ của chính app**, đã capture + lưu ở `<source>/.claude/memory/ux/` (xem Phase 1).
2. **Cách các website học/khoá học đầu ngành** giải bài toán đó (`../../refs/` — xem `../../refs/CONTENT.md`).
3. **Design system StarCi** (`../../cannon/CONTENT.md` + `<source>/.claude/design/`).

`<source>` = repo app FE (`D:/Repositories/starci-academy`). **KHÔNG viết production code** — brainstorm + chốt
hướng (+ widget mockup); backend chỉ **đề xuất chỉnh nhẹ**, không tự sửa ở đây.

## Năm "goal lens" (chốt mục tiêu trước khi brainstorm)
- **UX-only** — luồng, trạng thái, friction, information architecture của trang.
- **Marketing** — trang/khối bán cái gì, conversion lever, trust signal, social proof, value-gate.
- **Strategic communication** — trang nói gì với ai, thứ tự thông điệp, tone, primary message.
- **Component design** — 1 component cụ thể (card, paywall modal, league row, streak widget, AI panel…).
- **Page layout** — bố cục tổng (archetype, cột, rail, spacing rhythm, 3 tầng).
Một yêu cầu có thể chạm nhiều lens; nêu rõ lens chính.

## Quy trình (MAX effort)

### Phase 0 — Khoanh vùng + chốt lens (≤30s)
Trang·khối nào, goal lens chính, ai dùng, mục tiêu là gì.

### Phase 1 — Đọc UX hiện có → **LƯU vào `.claude/memory`** (bắt buộc)
Mục tiêu: KHÔNG đào lại hiện trạng mỗi lần — capture một lần, persist, tái dùng.
1. Mở `<source>/.claude/memory/ux/<page-slug>.md`.
   - **Có rồi & còn đúng** → đọc, dùng làm baseline (đừng dựng lại).
   - **Chưa có / đã cũ** → dựng lại từ source rồi GHI vào file đó.
2. Khi (re)build, đọc source thật và ghi lại **bộ nhớ UX hiện trạng**:
   - **Route** (`app/[locale]/…/page.tsx`) + feature/blocks render nó.
   - **Dữ liệu trang đang hiện** = GraphQL op (`modules/api`, `hooks/swr`) + Postgres entity tương ứng
     (field nào dùng, field nào BE có mà UI chưa dùng = cơ hội).
   - **Layout & sections hiện tại**, các **state** (loading/empty/error), và **pain points**.
3. Format file `.claude/memory/ux/<page-slug>.md`: `# UX hiện trạng — <page>` → route · components · data(GraphQL+entity)
   · sections · states · pain points · (cuối) "đề xuất hiện tại" (điền ở Phase 4). Đây là **bộ nhớ chung**, các
   lần brainstorm sau đọc thẳng.

### Phase 2 — Nạp refs + design system
- Đọc `./CONTENT.md` (playbook) → nó chỉ đúng `../../refs/<slug>.md` nào cần (hoặc tra `../../refs/CONTENT.md`).
- Mở **2–4 `../../refs/<slug>.md`** liên quan (trích cái LÀM TỐT + cái ĐỪNG copy — KHÔNG đoán từ trí nhớ).
- Map design system: archetype gần nhất + block tái dùng (`../../cannon/CONTENT.md` + `<source>/.claude/design/`).

### Phase 3 — Đề xuất layout mới (khi có layout mới)
Kết hợp **(memory UX hiện có) + (refs) + (design system)** → brainstorm:
- **Layout** — chọn archetype, cột/rail, spacing 3 tầng.
- **Components** — block/feature tái dùng; **đề xuất block MỚI** nếu thiếu (mô tả API + thuộc tầng nào).
- **Chức năng** — feature/tương tác mới (vd filter, hover-preview, streak widget…).
- **Minor backend (được phép):** nếu mục tiêu UX cần dữ liệu BE **chưa expose** → ĐỀ XUẤT chỉnh nhẹ:
  thêm field vào GraphQL ObjectType, 1 query/resolver mỏng, hay tweak projection/CQRS read-model. Ghi rõ
  **"⚙️ minor BE change"** + scope nhỏ (không đập kiến trúc, không migration nặng). Chỉ ĐỀ XUẤT — không tự sửa BE.

### Phase 4 — Brainstorm hướng + chốt
- **≥2–3 hướng** khác nhau (mỗi hướng neo ref cụ thể + trade-off) → **CHỐT 1 + lý do**.
- Bảng **section → dữ liệu** (field BE/DB; đánh dấu field cần "⚙️ minor BE change").
- Empty/loading/error + a11y + dark mode tính từ đầu.
- Cập nhật mục "đề xuất hiện tại" trong `.claude/memory/ux/<page-slug>.md`.

### Phase 5 — Output
- Doc brainstorm cạnh trang: `<source>/src/components/features/<Feature>/UX-BRAINSTORM.md` + tóm tắt chat
  (mục tiêu · IA mới · các hướng + hướng chốt · bảng section→data · ref neo · BE delta · cắt/thêm).
- **VẼ WIDGET khi đề xuất LAYOUT/COMPONENT MỚI** (bắt buộc): `read_me` module `mockup` → `show_widget`
  render 1–3 scenario cạnh nhau (CSS vars, accent teal) cho thầy NHÌN + CHỌN; đánh dấu scenario đề xuất.
- **KHÔNG production code.** Thầy chọn xong → `/ux-apply` mới dựng FE; BE delta để thầy duyệt riêng.

→ Feedback bất cứ lúc nào → ghi `<source>/.claude/rules/drafts/<temp>.md` (rút nguyên tắc tổng quát), KHÔNG sửa
file rule ổn định trực tiếp.

## Nguyên tắc (đọc kỹ)
- **Memory-first:** luôn đọc/ghi `.claude/memory/ux/<page>.md` — hiện trạng là tài sản lưu lại, không đào lại.
- **Refs = pattern đã chứng minh, KHÔNG copy nguyên xi.** Mỗi hướng neo ref cụ thể (vd "Coursera left-sidebar
  accordion", "Duolingo demotion-zone"). Adapt theo model StarCi (freemium + gamified + AI credit + coding challenge).
- **Grounded + buildable:** dựng được bằng token + HeroUI v3 + block StarCi (accent teal `#00a898`, layout 3 tầng).
  Ưu tiên data BE có sẵn; thiếu thì **đề xuất minor BE change** rõ ràng — đừng vẽ UI cho data không thể có.

## Khi nào mở ref nào (quick index — chi tiết trong CONTENT.md)
- Catalog / homepage / discovery / search / cards → `catalog-discovery.md` + `coursera.md`, `udemy.md`, `skillshare.md`.
- Lesson reader / video / transcript / notes / 3-pane code editor → `lesson-player.md` + `codecademy.md`, `udemy.md`, `khan-academy.md`.
- XP / streak / league / badge / progress → `gamification.md` + `duolingo.md`, `brilliant.md`, `khan-academy.md`.
- Onboarding / signup / activation / empty states → `onboarding.md` + `duolingo.md`, `codecademy.md`.
- Pricing / paywall / freemium gate / upgrade CTA / AI credit gate → `pricing-paywall.md` + `coursera.md`, `brilliant.md`, `duolingo.md`.
- Dashboard / home / "continue" card / mobile / bottom-nav → `dashboard-mobile.md` + `codecademy.md`, `coursera.md`.
- AI co-pilot panel / Socratic tutor / hint ladder → `coursera.md`, `udemy.md`, `khan-academy.md`, `codecademy.md`, `brilliant.md`.
- Trust / credential / certificate / "serious dev" tone → `edx.md`, `frontend-masters.md`, `freecodecamp.md`.
