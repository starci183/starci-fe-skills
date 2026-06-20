## Progress & gamification

Reference for StarCi Academy — researched from current (2024–2026) platform data, design analyses, and official posts. Sources cited throughout.

---

### Dominant patterns

These seven solutions appear across virtually every leading learning platform:

**1. The streak (consecutive-day or consecutive-week counter)**
The single most replicated mechanic. A flame icon with a count number, placed in the top navigation bar or home screen header. Duolingo popularised it; Codecademy, Khan Academy, Brilliant, and Headspace all run variants. The psychological hook is loss-aversion: the longer the chain, the more it hurts to break it. Supporting mechanisms always accompany the raw streak: a *freeze* (spend a consumable to protect a missed day), a *grace period* (automatic one-day forgiveness), and *streak repair* (retroactively restore a broken streak, sometimes for a fee or bonus XP). Duolingo's home screen iOS widget showing the streak count alone drove a 60% engagement uplift. ([Trophy/Duolingo case study](https://trophy.so/blog/duolingo-gamification-case-study))

**2. XP as the shared currency**
Experience points unify every other mechanic into one number. Completing a lesson earns XP → advances the streak → feeds the daily goal → updates the league rank → triggers achievement progress. Without this single metric, subsystems operate in isolation. XP values are weighted by effort: Codecademy maps them to Bloom's Taxonomy levels (e.g., 25 XP for a lesson, 50 XP for a portfolio project). ([Codecademy Skill XP blog](https://www.codecademy.com/resources/blog/introducing-codecademy-skill-xp)) The crucial UX rule: show XP feedback *before* the lesson close screen fires — tightly couple the reward to the behaviour.

**3. The guided linear path (not a free-form skill tree)**
Post-2022 research and Duolingo's own redesign showed that open skill trees generate decision paralysis and are abandoned faster than guided paths. Duolingo replaced its skill tree with a single scrolling path of "pebble-shaped circles" in a swirling line. Each circle is one level. Completed nodes turn gold. A floating arrow button snaps you back to your current position if you scroll away. Stories appear as book-icon nodes interspersed through the path. ([Duolingo blog: new home screen](https://blog.duolingo.com/new-duolingo-home-screen-design)) Brilliant uses "color-coded pathways where nodes and connecting lines are Rive-animated" — each subject track has a distinct hue so the user knows which domain they're in at a glance. ([Rive blog on Brilliant](https://rive.app/blog/how-brilliant-org-motivates-learners-with-rive-animations))

**4. Weekly leagues / tiered leaderboards**
Duolingo's league system is the gold standard. 30 users per pool, ranked by XP earned that week. 10 tiers: Bronze → Silver → Gold → Sapphire → Ruby → Emerald → Amethyst → Pearl → Obsidian → Diamond. Visual layout of the league screen: ranked list with avatar + username + weekly XP. A green "PROMOTION ZONE" label sits between the qualifying and non-qualifying rows. A grey "DEMOTION ZONE" label marks the bottom danger band. A countdown timer at the top shows time until Monday reset. Week-end result: full-screen animated reveal showing final rank, tier change notification, and gem reward for top finishers. Lower tiers promote 15–20 users; Diamond tier is extremely restrictive. Introducing leagues drove a 25% increase in lesson completions. ([Duolingo Leagues guide](https://www.tprteaching.com/duolingo-leagues/), [Deconstructor of Fun analysis](https://duolingo.deconstructoroffun.com/mechanics/leagues))

**5. Tiered badges / achievement shelves**
Khan Academy has five badge rarity tiers (Meteorite, Moon, Earth, Sun, Black Hole — ordered by rarity). Codecademy awards badges for weekly-target streaks, with progressively harder unlock thresholds as the streak number grows. Duolingo separates badges into "Personal Records" (milestones only you compete against) and "Awards" (challenge completions). The shelf lives on the profile page; badges use distinct icon shapes with color coding per rarity. The key insight: badges tied to *behaviour* (kept your streak 10 weeks) outperform badges tied to *quantity* (earned 500 points). ([Khan Academy help](https://support.khanacademy.org/hc/en-us/articles/202487710-What-are-energy-points-badges-and-avatars))

**6. Daily goal picker / weekly target selector**
Duolingo: a daily minute selector (5 min → 10 → 15 → 20) shown at onboarding and editable later. It feeds the home screen "daily quest" progress indicator. Codecademy: a weekly days-per-week selector (e.g., 3 days/week), displayed as a ring or small indicator in the top-right of "My Home". Meeting the weekly target for consecutive weeks advances a "weekly streak" counter and unlocks harder achievement badges. ([Codecademy weekly targets forum](https://discuss.codecademy.com/t/new-feature-release-weekly-targets/548750)) The weekly cadence is more forgiving than daily, which suits professional learners.

**7. Completion animations (micro-rewards)**
Brilliant uses Rive for animated celebrations on streak milestones and lesson completions — event-triggered state machines that fire a satisfying animation + XP counter sequence before advancing to the next screen. ([Rive/Brilliant post](https://rive.app/blog/how-brilliant-org-motivates-learners-with-rive-animations)) Duolingo: thick-border buttons with a downward shift animation on press (tactile feel); correct-answer feedback is green banner, wrong-answer is a gentle red banner showing the right answer with "GOT IT" language, not punitive messaging. ([Blake Crosley Duolingo design guide](https://blakecrosley.com/guides/design/duolingo)) The rule: feedback must be *immediate* and *visually coupled* to the action — reward fires before you navigate away.

---

### Concrete examples per platform

**Duolingo** — the reference implementation
- Home screen: single scrolling path of pebble nodes on a green/teal background. Completed = gold. Locked = grey. Current node = highlighted with a character head popping out. Bottom nav: Home (owl), Search, Quests (chest icon), Profile; Super members get Practice Hub (barbell icon) as a 5th tab.
- Streak: flame icon + number in top nav bar, always visible. Supporting: streak freeze (purchasable with gems), streak repair, and a weekly calendar grid of filled/empty circles on the streak detail screen.
- XP: awarded immediately after lesson exit screen, before the app navigates home. Feeds daily goal (circular arc progress bar on home screen below the path), and league rank simultaneously.
- Hearts: 5 red hearts shown top-right during active lessons. Wrong answer = -1 heart with a shake animation and red banner. Running out of hearts stops the lesson; Super subscribers have unlimited hearts.
- League: separate tab in the Leagues section. 30-user list. Green promotion zone label between rows 1–10 and row 11. Grey demotion zone below rank 25. Countdown timer at top. Full-screen animated result Monday morning with gems for top 3.
- Badges: split into Personal Records and Awards sections on the profile page. Shelf shows locked badges as greyed silhouettes, creating a completionist pull.
- Colors: Green #58cc02 (success/primary CTA), Red #ff4b4b (hearts/wrong), Orange #ff9600 (streak flame), Yellow #ffc800 (XP reward), Purple #ce82ff (leagues).
- Sources: ([Trophy case study](https://trophy.so/blog/duolingo-gamification-case-study)), ([Duolingo home screen blog](https://blog.duolingo.com/new-duolingo-home-screen-design)), ([Blake Crosley](https://blakecrosley.com/guides/design/duolingo))

**Brilliant**
- Learning paths: color-coded per subject (maths, science, CS), Rive-animated nodes and connecting lines. Path scrolls vertically. Each node = one interactive lesson ("bite-sized, requires active participation").
- Problem cards: interactive — wrong answers open an explorable explanation with interactive elements (not just text). Weight-scale visuals for algebra, etc.
- Streak: animated milestone celebration when streak achieved — Rive state machine, color-coded to match subject.
- Onboarding: 12-step flow. First screen = competency assessment using real problems (not a survey). Paywall appears at step ~4 with a visual trial timeline to build trust.
- Loading: tangram-style animated spinners instead of generic circles — brand-reinforcing.
- Dark mode: supported natively.
- Sources: ([Screensdesign Brilliant](https://screensdesign.com/showcase/brilliant-learn-by-doing)), ([Rive/Brilliant animations](https://rive.app/blog/how-brilliant-org-motivates-learners-with-rive-animations)), ([Trophy/Brilliant case study](https://trophy.so/blog/brilliant-gamification-case-study))

**Codecademy**
- Dashboard: skill XP log showing progress per skill category (e.g., Python, SQL, Web Dev), sortable by "most XP" or "most recent". Skill XP values: 25 XP per lesson/quiz, 50 XP per portfolio project.
- Weekly target: shown top-right on "My Home" as a days-of-week indicator. Each day you log activity, that day lights up. Missing a week resets the weekly streak counter.
- Badge shelf: under "Achievements" on profile. Badges for completing exercises (500 exercises badge), maintaining weekly streaks, course completions.
- Profile: public-facing, shows skills earned, courses in progress, streak, and badge shelf side by side.
- Skill XP note: level thresholds not yet published as of 2024–2025 ("excited to build that soon").
- Sources: ([Codecademy Skill XP intro](https://www.codecademy.com/resources/blog/introducing-codecademy-skill-xp)), ([Codecademy weekly targets](https://discuss.codecademy.com/t/new-feature-release-weekly-targets/548750)), ([Codecademy profile updates](https://help.codecademy.com/hc/en-us/articles/1260806913469-Profile-Updates))

**Khan Academy**
- Badge tiers (rarity-ordered): Meteorite (common), Moon, Earth, Sun, Black Hole (rarest). Plus "Challenge Patches" for completing specific course units.
- Mastery levels per skill: Attempted → Familiar → Proficient → Mastered — shown as color-coded states on a course map ("progress" tab per class).
- Energy points: measure *effort*, not mastery. Pushing at the edge of knowledge earns more points than easy review.
- Streaks: "deliberately understated" (Headspace-style) — visible but not anxiety-inducing.
- Sources: ([Trophy/Khan Academy case study](https://trophy.so/blog/khan-academy-gamification-case-study)), ([Khan Academy help: badges](https://support.khanacademy.org/hc/en-us/articles/202487710-What-are-energy-points-badges-and-avatars))

**Coursera / edX**
- Minimal gamification layer — progress is *extrinsic* (certificates, Credly badges, peer grades) not intrinsic (XP, streaks, leagues).
- Coursera: module-level progress bar per week; certificate delivered via Credly with shareable badge for LinkedIn. No streaks, no leagues.
- edX (Open edX): learner dashboard MFE shows enrolled courses as cards with completion percentage. Badge system exists but is institution-driven, not platform-driven.
- Takeaway: these platforms bet on credential value as the motivation layer, not gaming mechanics. Their completion rates are lower as a result — gamification matters for retention.
- Sources: ([e-learning design principles, Justinmind](https://www.justinmind.com/ui-design/how-to-design-e-learning-platform)), ([edX badges docs](https://docs.openedx.org/projects/edx-credentials/en/latest/badges/index.html))

---

### DO / DON'T heuristics

**DO**

- **Unify everything under one XP number.** Streak + league rank + daily goal + achievement progress should all read from the same XP counter. Fragmented metrics (separate "energy points" + "mastery points" + "streak") create confusion. ([Xperiencify design guide](https://xperiencify.com/gamification-design/))
- **Show XP reward before dismissing the lesson screen.** The feedback must be coupled to the behaviour — if the reward appears after navigation, the link is broken.
- **Put the streak counter in persistent UI** (top nav, always visible). Duolingo's widget test proved this: even a home screen widget showing only the streak number moved engagement by 60%.
- **Offer a streak freeze / grace mechanism.** Without one, a single missed day destroys weeks of investment. Users who feel punished churn. Duolingo, Brilliant, Codecademy (weekly target is already more forgiving) all provide protection.
- **Use a weekly cadence alongside daily.** Codecademy's weekly target is less anxiety-inducing than a daily streak for adult professionals. Many platforms now offer both.
- **Color-code promotion/demotion zones clearly.** Green promotion band, grey/red demotion band in leagues. Users need to instantly parse their position without reading.
- **Animate milestone events.** Streak achievements, level-ups, and course completions deserve a moment. Use Rive or CSS keyframe animations that fire immediately and feel snappy (<600ms). Brilliant's tangram spinners and lesson-complete celebrations are the benchmark.
- **Separate personal-record badges from competitive badges.** Duolingo's Personal Records shelf lets users feel achievement regardless of league rank. Competing with yourself is always motivating; competing with others isn't for everyone.
- **Give greyed-out "locked" badge silhouettes** on the shelf. Creates a completionist pull without disclosing requirements prematurely.
- **Make the learning path linear by default** with visible progress (completed nodes turn gold/filled). Decision paralysis from branching trees is a real dropout cause.
- **Use weekly goals over arbitrary daily ones** for professional learners — picking 3×/week feels achievable, 7/7 feels like a job.

**DON'T**

- **Don't put leaderboards front and center for new users.** Leaderboards demotivate ~90% of users who are not in the top 10. Duolingo correctly hides the league in its own tab. Surface it only when the user has opted in or is ranked near the top.
- **Don't build two separate progress metrics for the same concept.** Older StarCi pattern: two lanes (auto credit vs premium credit) in one screen. Same anti-pattern applies to XP: don't show "lesson points" separately from "streak XP" separately from "badge XP" — they must merge. (See credit-unified-pool-ui rule in project context.)
- **Don't use guilt-trip dark patterns as the primary retention mechanic.** Sad mascots, loss-framed notifications, and social shaming create short-term engagement and long-term churn + app deletion. Headspace frames a missed day as "recoverable, not failure." ([UX Magazine on streak psychology](https://uxmag.com/articles/the-psychology-of-hot-streak-game-design-how-to-keep-players-coming-back-every-day-without-shame))
- **Don't make badges purely cosmetic.** If earning a badge doesn't gate anything, unlock anything, or tie to any narrative, users will stop caring. Tie badges to social profile visibility, minor feature unlocks, or at minimum a satisfying unlock animation.
- **Don't show a progress bar for every item in a list.** One full-width bar per screen, or per open section (see one-progress-bar-at-a-time rule). Three stacked progress bars = visual noise that signals "you're always behind." ([Arounda UX/gamification blog](https://arounda.agency/blog/gamification-in-product-design-in-2024-ui-ux))
- **Don't gate daily logins with a pure "check-in reward" (Skinner box).** Daily login bonuses with no learning action required train users to tap-and-leave, inflating DAU without improving retention value. ([Gamification Gone Wrong analysis](https://nerdsip.com/blog/gamification-gone-wrong-when-streaks-become-the-point))
- **Don't make XP farming trivially easy.** Duolingo's notorious easy-lesson XP grinding (users repeat level 1 for hours during league week) degrades actual learning. Weight XP by difficulty/time, or introduce diminishing returns on repeated easy content.
- **Don't introduce leagues before the user has a baseline.** A new user thrown into a Bronze league full of high-earners will churn. Seed early leagues with similarly new users or make first-week leagues private/solo.

---

### Takeaways for StarCi

StarCi already has: weekly leagues, XP, streaks, badges, AI credit, freemium tiers, coding challenges. Below are the highest-leverage design decisions based on the research:

**1. One XP pool, one number everywhere**
Don't surface "lesson XP" separately from "challenge XP" separately from "AI co-pilot credits". Learners should see a single weekly XP total feeding their league rank and daily goal. Credits/AI quota is a *separate* resource meter (not XP) — keep it visually separate and clearly labelled (e.g., a fuel gauge icon, not an XP bar shape).

**2. Linear course path with gold-filled completed nodes**
Content map (modules → lessons) should feel like a path, not a tree. The accordion rail pattern (one open module at a time, collapsed = count "n/m", open = one progress bar) already moves in this direction per the project rules. Make completed lesson nodes visually "filled" (solid teal circle with checkmark), current node "pulsing" (subtle ring animation), locked future nodes greyed.

**3. Weekly league screen layout**
Modelled on Duolingo's confirmed pattern:
- List of 30 users: avatar + username + weekly XP (right-aligned number)
- Green "PROMOTION ZONE" divider label between rows 7 and 8 (or wherever your tier cutoff lands)
- Grey "DEMOTION ZONE" divider label near the bottom band
- Countdown timer at top right ("resets in 3d 14h")
- User's own row highlighted (teal background row, not just bold text)
- Week-end: full-screen modal with final rank, tier change, XP total, gem/reward

**4. Streak with freeze, not shame**
Show streak counter in top nav (flame icon + number). Provide streak freeze (spend a premium benefit or earn via completing challenges). Tone: "Your streak is safe today" (green) not "You failed" (red skull). Missed day: grey flame, copy "Resume your streak today — no penalty this time" (first miss of week only). This matches StarCi's freemium model where premium streak-freeze is a meaningful benefit, not just cosmetic.

**5. Badge shelf on profile**
Two sections: "Achievements" (personal-record based — e.g., "Completed 10 challenges", "7-week streak") and "Trophies" (league/competition based — top-3 finishes). Show locked badges as teal-tinted silhouettes. Each badge: small icon (32px), category colour ring, name on hover/tap. No more than 3–4 per row on a 3xl-wide column.

**6. Daily goal ring on home/dashboard**
A small circular arc ring (not a full-width bar — that's for lesson-level progress inside content). Shows today's XP vs daily goal (e.g., 50 XP / 100 XP). Lives in the top of the home screen below the breadcrumb/header. Teal fill, muted background track. Tapping it opens the goal-picker modal (three options: Casual 50 XP / Regular 100 XP / Intense 200 XP).

**7. Completion micro-animation**
On lesson complete: a 400–600ms Tailwind/Framer burst animation on the XP counter (count-up number animation + brief confetti or ring pulse in accent teal). Happens *before* the "Next lesson" CTA appears. Do this with CSS animation or a minimal Rive asset, not a heavyweight library. Keep it under 800ms total.

**8. Don't show leaderboard by default on home**
StarCi's league is opt-in competitive. Put the league under its own nav item or profile tab. On the home dashboard, show only: streak counter (top bar), daily goal ring, and the linear lesson path. Users who want to see their rank should navigate to league, not have it shoved in their face each visit.

**9. Weekly cadence as the primary habit signal**
Given StarCi's adult professional learner base (developers, engineers), a weekly target (e.g., "complete 3 lessons this week") is less anxiety-inducing than a daily streak. Run both: daily streak as the *bonus* mechanic (flame), weekly target as the *primary* habit signal (7-dot row on home, a dot fills per active day).

**10. Freemium gate: badge silhouettes + league floor, not feature lockouts**
Freemium users should see the full gamification system (XP, streak, badges, leagues) with a handful of "premium badge" slots shown greyed out ("Unlock with Pro"). Don't hide leagues from free users — the competitive visibility is what drives conversion. Gate streak-freeze, double-XP weekends, and certain elite badge categories behind Pro.

---

### Sources

- [Duolingo Gamification Case Study 2026 — Trophy](https://trophy.so/blog/duolingo-gamification-case-study)
- [Duolingo Gamification — Strivecloud](https://www.strivecloud.io/blog/blog-gamification-examples-boost-user-retention-duolingo)
- [Duolingo Gamification Secrets — Orizon](https://www.orizon.co/blog/duolingos-gamification-secrets)
- [Duolingo: Gamification as Design Language — Blake Crosley](https://blakecrosley.com/guides/design/duolingo)
- [Duolingo New Home Screen Design — Official Blog](https://blog.duolingo.com/new-duolingo-home-screen-design)
- [Duolingo Leagues & Leaderboards — Official Blog](https://blog.duolingo.com/duolingo-leagues-leaderboards/)
- [Duolingo Leagues Explained — TPR Teaching](https://www.tprteaching.com/duolingo-leagues/)
- [Duolingo Leagues Guide — DuolingoGuides](https://duolingoguides.com/duolingo-leagues/)
- [Duolingo Leagues Mechanics — Deconstructor of Fun](https://duolingo.deconstructoroffun.com/mechanics/leagues)
- [Duolingo Divisions 2026 — Spliiit](https://www.spliiit.com/en/blog/divisions-duolingo-explication)
- [Duolingo Friend Streak — Official Blog](https://blog.duolingo.com/friend-streak/)
- [Brilliant Gamification Case Study — Trophy](https://trophy.so/blog/brilliant-gamification-case-study)
- [Brilliant UI Breakdown — Screensdesign](https://screensdesign.com/showcase/brilliant-learn-by-doing)
- [How Brilliant Motivates with Rive Animations](https://rive.app/blog/how-brilliant-org-motivates-learners-with-rive-animations)
- [Khan Academy Gamification Case Study — Trophy](https://trophy.so/blog/khan-academy-gamification-case-study)
- [Khan Academy Badges, Energy Points & Avatars — Help](https://support.khanacademy.org/hc/en-us/articles/202487710-What-are-energy-points-badges-and-avatars)
- [Codecademy Gamification Case Study — Trophy](https://www.trophy.so/blog/codecademy-gamification-case-study)
- [Codecademy Skill XP Introduction](https://www.codecademy.com/resources/blog/introducing-codecademy-skill-xp)
- [Codecademy Weekly Targets Forum Announcement](https://discuss.codecademy.com/t/new-feature-release-weekly-targets/548750)
- [Codecademy Profile Updates Help](https://help.codecademy.com/hc/en-us/articles/1260806913469-Profile-Updates)
- [Gamification in Product Design 2025 — Arounda](https://arounda.agency/blog/gamification-in-product-design-in-2024-ui-ux)
- [Essential Guide to Gamification Design 2024 — Xperiencify](https://xperiencify.com/gamification-design/)
- [Streaks & Milestones for Mobile Gamification — Plotline](https://www.plotline.so/blog/streaks-for-gamification-in-mobile-apps)
- [Apps That Use Streaks: 10 Examples — Trophy](https://trophy.so/blog/streaks-feature-gamification-examples)
- [The Psychology of Streaks — Trophy](https://trophy.so/blog/the-psychology-of-streaks-how-sylvi-weaponized-duolingos-best-feature-against-them)
- [Psychology of Hot Streak Game Design — UX Magazine](https://uxmag.com/articles/the-psychology-of-hot-streak-game-design-how-to-keep-players-coming-back-every-day-without-shame)
- [Gamification Gone Wrong — NerdSip](https://nerdsip.com/blog/gamification-gone-wrong-when-streaks-become-the-point)
- [Dark Side of Gamification: UX Ethics — Medium](https://medium.com/@jgruver/the-dark-side-of-gamification-ethical-challenges-in-ux-ui-design-576965010dba)
- [Progress Bars Feature: 10 Apps — Trophy](https://trophy.so/blog/progress-bars-feature-gamification-examples)
- [Gamification 2.0: Beyond Points and Badges — UX Magazine](https://uxmag.com/articles/gamification-2-0-beyond-points-and-badges-designing-for-players-not-metrics-chapter-1-the-problem)
- [e-Learning Platform Design Principles — Justinmind](https://www.justinmind.com/ui-design/how-to-design-e-learning-platform)
- [edX Open Learning Dashboard Challenge](https://openedx.org/blog/edx-learning-dashboard-challenge/)
- [edX Badges Documentation](https://docs.openedx.org/projects/edx-credentials/en/latest/badges/index.html)
