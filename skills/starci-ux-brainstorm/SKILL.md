---
name: starci-ux-brainstorm
description: >
  Re-imagine the UX/UI of a StarCi Academy page from first principles, grounded in (a) how the best
  COURSE/LEARNING websites solve the same problem and (b) the StarCi design system. Use this for any
  "ux-brainstorm" need: rethink/redesign a page, design a component, lay out a page, sharpen the
  marketing angle of a screen, or shape a communication strategy for a flow. Covers catalog/discovery,
  lesson player, coding challenges, dashboard, onboarding/activation, gamification (XP/streaks/leagues/
  badges), pricing/paywall, profile, AI co-pilot. Five goal lenses: UX-only, marketing, strategic
  communication, component design, page layout. Output = a brainstorm doc + recommendation (+ widget
  mockup when proposing a new layout). NO production code. Run with MAX reasoning effort (Opus).
  Trigger when the user types `/starci-ux-brainstorm`, asks to rethink/redesign/brainstorm a page,
  design a component, or lay out a page — including Vietnamese: "nghĩ ux", "brainstorm trang",
  "thiết kế lại trang", "thiết kế component", "design layout", "bố cục trang", "góc marketing trang".
---

# /starci-ux-brainstorm — Re-imagine a StarCi page from course-UX refs + the design system (Opus · MAX effort)

Thiết kế LẠI một trang/khối/luồng của StarCi từ **first principles**, neo vào **2 nguồn**:
1. **Cách các website học/khoá học đầu ngành** giải đúng bài toán đó (thư mục `./refs/` — Coursera, Udemy,
   Duolingo, Khan Academy, Brilliant, Codecademy, edX, Skillshare, Frontend Masters, freeCodeCamp + 5 ref
   cross-cutting: onboarding, catalog-discovery, lesson-player, gamification, pricing-paywall, dashboard-mobile).
2. **Design system StarCi** (`D:/Repositories/starci-academy/.claude/design/` + `../cannon/CONTENT.md`).

Bước này **KHÔNG viết production code** — chỉ brainstorm + chốt hướng (+ widget mockup). CHẠY MAX EFFORT.

## Năm "goal lens" (hỏi/đoán mục tiêu trước khi brainstorm)
- **UX-only** — luồng, trạng thái, friction, information architecture của trang.
- **Marketing** — trang/khối này bán cái gì, conversion lever, trust signal, social proof, value-gate.
- **Strategic communication** — trang nói gì với ai, thứ tự thông điệp, tone, cái gì primary message.
- **Component design** — 1 component cụ thể (card, paywall modal, league row, streak widget, AI panel…).
- **Page layout** — bố cục tổng (archetype, cột, rail, spacing rhythm, 3 tầng).
Một yêu cầu có thể chạm nhiều lens; nêu rõ lens chính.

## Nguyên tắc (đọc kỹ)
- **Refs = nguồn pattern đã chứng minh, KHÔNG copy nguyên xi.** Mỗi hướng phải neo vào ref cụ thể
  (vd "Coursera left-sidebar accordion", "Duolingo demotion-zone", "Udemy hover-preview card") — đọc file
  `./refs/<slug>.md` tương ứng, trích cái LÀM TỐT + cái ĐỪNG copy. KHÔNG đoán từ trí nhớ.
- **Grounded in StarCi data + design system.** Đừng vẽ UI cho dữ liệu không có. Field BE/DB có nhưng chưa
  dùng = cơ hội. Mọi đề xuất phải dựng được bằng token + HeroUI v3 + block của StarCi (accent teal `#00a898`,
  layout 3 tầng, `one-progress-bar-at-a-time`, `credit-unified-pool-ui`…).
- **Adapt, don't transplant.** StarCi là freemium + gamified (XP/league/streak/badge) + AI credit co-pilot +
  coding challenge — chọn pattern hợp model đó, loại pattern của model khác (vd Skillshare 1-plan vs StarCi
  freemium). Mỗi ref đã có sẵn mục "Takeaways for StarCi" — dùng làm điểm khởi đầu, không phải kết luận.

## Quy trình (MAX effort)
1. **Khoanh vùng + chốt lens:** trang/khối nào, goal lens chính, ai dùng, cần gì trong ≤30s.
2. **Đọc `./CONTENT.md`** — playbook + pattern library (catalog / lesson player / challenge / gamification /
   onboarding / pricing-paywall / dashboard / AI co-pilot). Nó chỉ đúng `refs/<slug>.md` nào cần mở sâu.
3. **Mở 2–4 `refs/<slug>.md` liên quan** + (nếu cần) research BE/DB StarCi thật (GraphQL op + Postgres
   entities = dữ liệu khả dụng) và legacy UX (chỉ để inventory + pain, KHÔNG để copy).
4. **Map sang design system StarCi:** archetype gần nhất (`design/03`), block tái dùng (`design/02` + cannon),
   token/spacing/3-tầng (`design/01`,`04` + rule drafts). Cái gì có sẵn, cái gì cần block mới.
5. **Brainstorm ≥2–3 HƯỚNG** khác nhau (mỗi hướng neo ref + trade-off), rồi **CHỐT 1 + lý do**. Map mỗi
   section → field BE/DB. Empty/loading/error + a11y + dark mode tính từ đầu.
6. **Output:** doc brainstorm cạnh trang (`<Feature>/UX-BRAINSTORM.md`) + tóm tắt chat: mục tiêu · IA mới ·
   các hướng + hướng chốt · bảng section→dữ liệu · ref neo · cái cắt/thêm. **KHÔNG production code.**
7. **VẼ WIDGET khi đề xuất LAYOUT/COMPONENT MỚI** (bắt buộc, không phải tweak nhỏ): `read_me` module
   `mockup` → `show_widget` render 1–3 scenario cạnh nhau (CSS vars, accent teal) cho thầy NHÌN + CHỌN.
   Đánh dấu scenario đề xuất. Thầy chọn xong → `/ux-apply` mới dựng.

→ Thầy feedback bất cứ lúc nào → ghi `.claude/rules/drafts/<temp>.md` (rút nguyên tắc tổng quát), KHÔNG sửa
file rule ổn định trực tiếp.

## Khi nào mở ref nào (quick index — chi tiết trong CONTENT.md)
- Catalog / homepage / discovery / search / cards → `catalog-discovery.md` + `coursera.md`, `udemy.md`, `skillshare.md`.
- Lesson reader / video / transcript / notes / 3-pane code editor → `lesson-player.md` + `codecademy.md`, `udemy.md`, `khan-academy.md`.
- XP / streak / league / badge / progress → `gamification.md` + `duolingo.md`, `brilliant.md`, `khan-academy.md`.
- Onboarding / signup / activation / empty states → `onboarding.md` + `duolingo.md`, `codecademy.md`.
- Pricing / paywall / freemium gate / upgrade CTA / AI credit gate → `pricing-paywall.md` + `coursera.md`, `brilliant.md`, `duolingo.md`.
- Dashboard / home / "continue" card / mobile / bottom-nav → `dashboard-mobile.md` + `codecademy.md`, `coursera.md`.
- AI co-pilot panel / Socratic tutor / hint ladder → `coursera.md`, `udemy.md`, `khan-academy.md`, `codecademy.md`, `brilliant.md`.
- Trust / credential / certificate / "serious dev" tone → `edx.md`, `frontend-masters.md`, `freecodecamp.md`.
