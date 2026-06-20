## Learner Dashboard & Mobile — Research Reference

### Overview

Web tools confirmed available and used. Training knowledge fills gaps where web fetch was blocked (Mobbin 403, some paywalled reviews). Sources cited throughout.

---

## Dominant Patterns

### 1. Hero "Continue" Card — The Single Most Important Widget

Every platform converges on a single, prominently placed card above the fold that resumes the last session with one tap. This is structurally the most battle-tested pattern in learner dashboards.

- **Mechanism**: server-persists last cursor (module/lesson/video timestamp), hydrates on page load, renders as a large card with course thumbnail, lesson name, progress bar, and a single primary CTA ("Resume", "Continue", "Pick up where you left off").
- **Position**: always the first content below the page header — either a full-width hero or the top card in a "My Learning" shelf.
- **Progress bar style**: horizontal bar inset into the card, showing % complete. Sometimes accompanied by a unit/chapter label ("Module 3 of 8").
- **Codecademy** calls this the "Today View" — a focused panel surfacing the single course you are actively working on. Previous courses live under a separate "My Courses" tab. This separation of "now" vs "library" is a strong pattern.
- **Coursera** surfaces "the next thing to do at the top of the page" with direct links to upcoming video/assignment. Week-by-week planning guides appear as secondary content below.
- **Khan Academy** redesign (Scott Liang case study): a single "Resume" button in the tab bar acting like Kindle's "current book" shortcut — the lowest-friction path back into learning. [Source](https://www.scottliang.com/work/khan-academy-redesign)

### 2. Linear Path / Scrollable Map vs Grid

Platforms have diverged sharply: **scrollable vertical path** (Duolingo, Brilliant) vs **grid of course cards** (Coursera, Udemy, Codecademy).

- **Duolingo path** (post-Nov 2022): a serpentine path of circular "pebble" nodes flowing downward, each node = one lesson. Completed nodes turn gold. Upcoming nodes are gray. Tapping any node shows a tooltip popup with lesson topic. A floating arrow button bottom-right lets you jump to current position on a long path. Unit headers show descriptive labels not abstract numbers ("Get directions", not "City 3"). [Source](https://blog.duolingo.com/new-duolingo-home-screen-design)
- **Brilliant**: animated path with color-coded nodes and connecting lines (via Rive animations). Different node types use different shapes/colors for topic differentiation. A "Level Gameboard" overlays progress tracking. [Source](https://rive.app/blog/how-brilliant-org-motivates-learners-with-rive-animations) / [Source](https://ustwo.com/work/brilliant/)
- **Coursera / Udemy / Codecademy**: catalog-style card grids — course thumbnail, title, instructor, progress bar, last accessed. Efficient for multi-course learners; less opinionated about sequence.

**Rule of thumb**: if your content is a fixed, curated sequence (language course, skill path), a visual path map gives a sense of journey and progress. If users browse a large catalog of independent courses, cards win.

### 3. Gamification — Dedicated Tab, Not Sidebar Clutter

The leading apps isolate gamification into dedicated tabs/screens, not persistent sidebar widgets:

- **Duolingo**: streak flame + day count live in a persistent top-bar widget on the home screen. XP total appears next to it. The Leagues leaderboard has its own dedicated bottom-navigation tab (the shield/trophy icon). The weekly competition screen shows a ranked list of ~30 users with XP bars, promotion zone (highlighted green, top N users), demotion zone (red, bottom N), and a countdown timer to weekly reset. Bronze → Silver → Gold → Pearl → Sapphire → Ruby → Emerald → Amethyst → Pearl → Obsidian → Diamond tiers. [Source](https://www.tprteaching.com/duolingo-leagues/)
- **Brilliant**: streak animation via Rive fires when streak milestone hit; XP counter shown in lesson completion screen. Competitive leagues unlock progressively (not visible until user reaches threshold). Gamification is revealed, not forced upfront. [Source](https://rive.app/blog/how-brilliant-org-motivates-learners-with-rive-animations)
- **Khan Academy**: energy points + mastery levels in profile/dashboard section; streaks as weekly consistency metric ("at least one skill to Proficient each week"). [Source](https://support.khanacademy.org/hc/en-us/articles/360054115071-What-are-Streaks-and-Course-Levels)

### 4. Bottom Tab Navigation — 3–5 Tabs, Icon + Label, Fixed

Universal mobile pattern. Best practice data from [UX World](https://uxdworld.com/bottom-tab-bar-navigation-design-best-practices/):

- **3–5 tabs maximum**. Fewer than 3 = use tab controls. More than 5 = use a "More" drawer.
- **Icon + text label on every tab**. Never icon-only (recognition > recall). Labels: short, single word, never truncated.
- **Active state**: filled icon vs outlined icon is the dominant pattern. Optional: 2px underline bar or subtle background highlight.
- **Badge dots/counts** on tabs for new notifications, unread items — never for progress (that belongs in content).
- **Fixed, never scrolling**. Tabs distribute evenly across full width.
- **Thumb zone alignment**: bottom bar hits the natural thumb arc on phones — far more ergonomic than top tabs on mobile.

**Duolingo** (after core tabs redesign): Home (lesson path), Quests (chest icon), Leaderboard (shield), Profile. Super subscribers get a Practice Hub tab (barbell icon). Lesson-specific icons were criticized for being unrecognizable in isolation — reinforces the icon+label rule. [Source](https://blog.duolingo.com/core-tabs-redesign)

**Khan Academy** (current): Home, Search, Bookmarks, Profile — 4 tabs, all labeled.

### 5. Density Tradeoffs — Less Is More on Mobile

Consistent signal across all platforms: reduce density, favor whitespace, avoid competing visual weights.

- **Duolingo core tabs redesign** explicitly moved from "forcing containers around components" to "purposefully using whitespace around components." Decorative artwork removed from headers where it didn't signal useful information. [Source](https://blog.duolingo.com/core-tabs-redesign)
- **Brilliant / ustwo**: six design concepts tested; final direction balanced "playfulness with cognitive demands of STEM." Gamification elements intentionally suppressed during focused study. [Source](https://ustwo.com/work/brilliant/)
- **General principle** (2025 e-learning trend): "clutter-free UI — no extra text, heavy animation, or overly complex menus." Large CTAs, generous whitespace. [Source](https://lollypop.design/blog/2025/august/top-education-app-design-trends-2025/)

### 6. Responsive / Adaptive Navigation

- **Desktop**: persistent left sidebar with course/module tree (Codecademy, Coursera web).
- **Tablet**: collapsible sidebar with hamburger toggle, or a "rail" (icon-only collapsed sidebar).
- **Mobile**: sidebar disappears entirely; replaced by bottom tab bar. 5-item max on bottom bar; any overflow goes to a "More" drawer or hamburger accessed from within a tab.
- Swipe gestures increasingly used for back navigation and modal dismissal; menus deprioritized in favor of gesture affordances (2025 trend). [Source](https://lollypop.design/blog/2025/august/top-education-app-design-trends-2025/)

### 7. Freemium Lock / Upgrade CTA

- Lock icon (padlock) overlaid on locked content nodes is the cross-platform standard (Duolingo Super, Codecademy Pro, Coursera audit locks).
- Lock appears inline in the path/grid — not hidden. Showing what you can't have creates upgrade motivation (Duolingo's strategy: path nodes visible, locked, gold padlock).
- Upgrade CTA fires contextually when user taps a locked item — a bottom sheet or modal (not a separate page navigation), showing the benefit relevant to that specific locked feature, with a single primary upgrade button.
- **Hard vs soft paywall**: learning platforms universally use soft paywalls (some free content always accessible) to maintain trust and conversion funnels. [Source](https://www.solutelabs.com/blog/paywalls-guide)

---

## Concrete Examples Per Platform

### Duolingo
- **Home**: vertical scrollable pebble path, top-bar shows streak flame + count + XP gems, quick-nav arrow floats bottom-right.
- **Lesson node**: circle icon, tap → popup tooltip with topic name + "Start" button.
- **Bottom tabs** (5): Home, Quests, Leaderboard, Social/Video, Profile.
- **Leagues tab**: full-screen leaderboard with 30 competitors, each row = avatar + username + XP bar + rank number. Promotion zone highlighted green. Demotion zone highlighted red. Weekly countdown timer at top.
- **Streak widget**: flame icon + number, persistent in home top bar. iOS lock-screen widget available (streak total + owl image that changes based on streak length).
- **Headers** (post-redesign): tiered sizes per tab, all left-aligned title, no decorative artwork, intentional whitespace.
- **Sources**: [Core tabs redesign](https://blog.duolingo.com/core-tabs-redesign) | [Home screen redesign](https://blog.duolingo.com/new-duolingo-home-screen-design) | [Leagues](https://www.tprteaching.com/duolingo-leagues/) | [Streak system](https://medium.com/@salamprem49/duolingo-streak-system-detailed-breakdown-design-flow-886f591c953f)

### Brilliant
- **Home**: animated path nodes (Rive), color-coded by topic. "Level Gameboard" tracks lesson progress.
- **Lesson completion**: XP counter animates up, streak animation fires on milestone, competitive leagues unlock progressively.
- **Navigation**: learning companion widget guides to next lesson. Lesson and challenge tiles as primary nav elements.
- **Design philosophy**: 6 concepts tested; rejected options that were too "game-like" during STEM study.
- **Sources**: [ustwo case study](https://ustwo.com/work/brilliant/) | [Rive animations](https://rive.app/blog/how-brilliant-org-motivates-learners-with-rive-animations) | [UI breakdown](https://screensdesign.com/showcase/brilliant-learn-by-doing)

### Codecademy
- **Home / Today View**: hero section shows the single active course. Skill XP log below (sortable by recent or by skill area). My Courses tab for library. New & Noteworthy section for platform updates.
- **Career Path pages**: broken into distinct modules, each with explicit skill label. Progress bar updates per-lesson (not per-module) for frequent reward cadence.
- **AI Learning Assistant**: inline in lesson view, not a separate page.
- **Sources**: [Dashboard update](https://www.codecademy.com/resources/blog/updates-to-the-codecademy-dashboard) | [Skill XP](https://www.codecademy.com/resources/blog/introducing-codecademy-skill-xp)

### Coursera
- **Dashboard**: "resume in one click" primary action top of page. Progress bars + week-by-week planning guides. Links to upcoming videos/assignments.
- **Mobile app**: 4-tab bottom nav (Home/Learn, My Learning, Explore, Profile). Personalized recommendations in home feed below continue card.
- **Course home page**: progress bar, grades, next-up content, certificate tracker.
- **Sources**: [Dashboard update](https://blog.coursera.org/whats-new-on-coursera-dashboard-and-course-home/)

### Khan Academy
- **Bottom nav (mobile)**: Home, Search, Bookmarks, Profile — 4 tabs.
- **Home screen**: My Classes section with "See All" link. Mastery-based progression shown per unit (Familiar → Proficient → Mastered).
- **Proposed redesign** (Scott Liang concept): single "Resume" tab shortcut, lessons fly up from bottom as dynamic panel, horizontal progress bar in lesson view replacing thumbnail grids, new Discussions tab.
- **Streaks**: weekly metric (Monday–Sunday Pacific), at least one skill to Proficient to maintain.
- **Sources**: [Khan redesign concept](https://www.scottliang.com/work/khan-academy-redesign) | [Streaks and Levels](https://support.khanacademy.org/hc/en-us/articles/360054115071)

---

## DO / DON'T Heuristics

### DO

**DO** put the "continue" CTA as the first interactive element on the home screen, above the fold, every time. One tap to resume. This is the single highest-value widget.

**DO** use icon + text label on every bottom tab. Never icon-only. Label must fit in one word, never truncated.

**DO** keep bottom tabs to 3–5 items max. If you need 6+, use a "More" drawer for overflow.

**DO** use the streak flame + count persistently in a top header bar or tab badge — not buried in a profile page. Habit mechanics only work when they are always visible.

**DO** put the league/leaderboard in a dedicated bottom tab (not a modal, not a sidebar panel). When it has its own tab, users visit voluntarily; when it is injected into the home feed, it feels coercive.

**DO** animate gamification moments (lesson completion XP tick-up, streak milestone) at the point of action — not on the home screen when the user returns. Celebration must be immediate or it loses meaning.

**DO** show locked content inline in the path/grid (with padlock icon) rather than hiding it. Aspirational visibility drives upgrades.

**DO** fire upgrade CTAs contextually as bottom sheets when a locked node is tapped — show the specific benefit of unlocking, single primary button.

**DO** use whitespace intentionally around components rather than adding card borders/containers. Duolingo's redesign directly attributed higher engagement to removing unnecessary containers.

**DO** use a horizontal progress bar per course card (not circular rings) for multi-course dashboards — bars are faster to compare at a glance across multiple cards.

**DO** make the desktop sidebar collapsible at tablet breakpoint and replace it with a bottom tab bar on mobile — never a hamburger-only mobile nav for a learning app (too many taps to get anywhere).

### DON'T

**DON'T** render multiple progress bars stacked vertically in a list (course bar + module bar + content bar all visible simultaneously). One bar at a time — aggregate progress at top, per-section count elsewhere (see StarCi's own rule: one-progress-bar-at-a-time draft).

**DON'T** build leaderboard rank/position as a home-feed widget. Negative for lower-ranked users; creates anxiety rather than motivation for the majority. Put it behind a voluntary tab.

**DON'T** make gamification elements louder than the content. Streaks/XP are nudges, not the product.

**DON'T** use icon-only bottom tabs with "creative" icons unique to your brand (Duolingo's own post-mortem cites this as a usability failure — non-standard icons aren't recognized without labels).

**DON'T** gate all content behind a paywall before the user has built any habit. Soft paywall with clear free tier is the standard; hard paywall on first visit kills conversion.

**DON'T** use card grids with 6+ visible courses on mobile — too dense. Limit to 2–3 visible cards with horizontal scroll or "see all" link.

**DON'T** separate streak / XP / badges into three different pages in settings/profile. Consolidate into one "My Progress" or "Stats" screen.

**DON'T** put "week by week plan" and "continue learning" in the same visual hierarchy level. The continue card is always the primary action; planning tools are secondary/collapsed.

---

## Takeaways for StarCi

StarCi Academy: Next.js App Router + React 19 + HeroUI v3 + Tailwind v4. Accent teal #00a898. Freemium. Courses → Modules → Lessons/Contents + Challenges. AI co-pilot. Weekly leagues/XP/streaks/badges.

### 1. Home screen information architecture

```
[Streak bar — flame + N days + XP weekly goal ring]  ← sticky top bar
[Hero "Continue" card — course thumb + lesson name + progress bar + "Resume" CTA]
[My Courses shelf — horizontal scroll, 2 cards visible, progress bar on each]
[Recommended / Explore section]
[AI credit usage nudge if low — subtle, dismissible]
```

The streak bar should be a single line — the same visual weight as a browser address bar. It should not be a full card.

### 2. Bottom tab bar (mobile, ≤md breakpoint)

```
Home | Explore | [Leagues (shield icon, badge for new season)] | Profile
```
4 tabs. No more. Label every tab. Consider a 5th "AI" tab if AI co-pilot is a primary workflow — otherwise surface AI as a floating action button (FAB) within content screens.

League tab should show a badge with "NEW" or a dot when a new weekly season starts, not a number.

### 3. Course/module content map

Use the linear scrollable path pattern (like Duolingo / Brilliant) rather than a flat list — StarCi courses have a fixed sequence (modules → lessons), which suits a path map. Each node = one lesson/content. Challenge nodes get a distinct icon (code-bracket or bolt). AI-locked content = node + teal padlock overlay + on-tap bottom sheet upgrade prompt.

Per the existing `one-progress-bar-at-a-time` draft rule: the module accordion in the rail should show a progress bar only for the expanded module, and `n/m` count for collapsed ones. This is directly aligned with Duolingo's principle of "one focused progress indicator per screen state."

### 4. Gamification widget placement

- **Streak**: persistent in the home top bar (not buried in profile).
- **XP**: shown in top bar alongside streak, or as a weekly progress ring.
- **Leagues**: dedicated tab with its own screen. Leaderboard list = avatar + username + XP + rank. Promotion zone teal (StarCi accent), demotion zone neutral/muted. Weekly countdown at top.
- **Badges**: profile section, not home feed. Celebrate earning via a full-screen moment animation (like Duolingo's lesson complete screen) — not a toast.

### 5. Freemium lock UI

- Show all content nodes, lock non-free ones with padlock overlay (opacity-75 card + lock icon centered).
- Tapped locked node → HeroUI bottom sheet (not modal navigation) with: "This is a Pro lesson", specific benefit copy, "Upgrade" primary button (teal), "Maybe later" dismiss.
- Never disable/hide locked content entirely — aspirational visibility converts.

### 6. AI credit widget

Per the `credit-unified-pool-ui` draft: do NOT render two separate bars (Auto lane vs Premium lane). Show a single credit pool widget:
```
[AI Co-pilot]  ████████░░  48/100 credits · resets in 3d 14h
[Upgrade for more →]
```
One bar, one window. Put this as a secondary card on home (below the hero continue card), or inside the Profile tab — not as a primary element.

### 7. Dark mode / color strategy

Teal accent works well in both light and dark — it has sufficient contrast on both white and dark surfaces. Follow Coursera's move to dark mode as an option (not default). Use `bg-success/10 text-success` pattern (from the `three-tier-page-layout` draft) for "Completed" / "Read" badges on lesson nodes — semantic green, not teal accent, to preserve teal for interactive/primary actions.

### 8. Responsive breakpoints

```
≥ lg (1024px+): persistent left rail (course/module tree) + content area + optional right panel
md (768–1023px): collapsible rail (hamburger toggles overlay drawer) + content
< md (767px): rail gone, bottom tab bar, content full-width, FAB for AI
```

---

## Sources

- [Duolingo core tabs redesign](https://blog.duolingo.com/core-tabs-redesign)
- [Duolingo new home screen design](https://blog.duolingo.com/new-duolingo-home-screen-design)
- [Duolingo Practice Hub guide](https://blog.duolingo.com/guide-to-duolingo-practice-hub)
- [Duolingo streak system design breakdown](https://medium.com/@salamprem49/duolingo-streak-system-detailed-breakdown-design-flow-886f591c953f)
- [Duolingo leagues explained — TPR Teaching](https://www.tprteaching.com/duolingo-leagues/)
- [Duolingo gamification & engagement design — UIinkits](https://www.uinkits.com/blog-post/how-to-design-like-duolingo-gamification-engagement)
- [Brilliant × ustwo case study](https://ustwo.com/work/brilliant/)
- [How Brilliant.org motivates learners with Rive animations](https://rive.app/blog/how-brilliant-org-motivates-learners-with-rive-animations)
- [Brilliant UI breakdown — Screensdesign](https://screensdesign.com/showcase/brilliant-learn-by-doing)
- [Codecademy dashboard update](https://www.codecademy.com/resources/blog/updates-to-the-codecademy-dashboard)
- [Codecademy Skill XP](https://www.codecademy.com/resources/blog/introducing-codecademy-skill-xp)
- [Coursera dashboard and course home updates](https://blog.coursera.org/whats-new-on-coursera-dashboard-and-course-home/)
- [Khan Academy app review — Educational App Store](https://www.educationalappstore.com/app/khan-academy)
- [Khan Academy streaks and course levels](https://support.khanacademy.org/hc/en-us/articles/360054115071-What-are-Streaks-and-Course-Levels)
- [Khan Academy redesign concept — Scott Liang](https://www.scottliang.com/work/khan-academy-redesign)
- [Bottom tab bar navigation best practices — UXDWorld](https://uxdworld.com/bottom-tab-bar-navigation-design-best-practices/)
- [Bottom tab bar — UX Planet](https://uxplanet.org/bottom-tab-bar-navigation-design-best-practices-48d46a3b0c36)
- [UX best practices for e-learning platforms — Pinlearn](https://pinlearn.com/ux-best-practices-for-e-learning-platforms/)
- [Top education app design trends 2025 — Lollypop](https://lollypop.design/blog/2025/august/top-education-app-design-trends-2025/)
- [Gamification design guide — Xperiencify](https://xperiencify.com/gamification-design/)
- [Paywalls for e-learning — Poool](https://blog.poool.fr/paywalls-for-e-learning-and-online-course-platforms/)
- [Hard vs soft paywall — RevenueCat](https://www.revenuecat.com/blog/growth/hard-paywall-vs-soft-paywall/)
- [Duolingo gamification secrets — Orizon](https://www.orizon.co/blog/duolingos-gamification-secrets)
