## Brilliant

### What & who

Brilliant (brilliant.org) is a STEM-focused interactive learning platform founded in 2012 by Sue Khim. It targets curious adults, working professionals, students, and gifted learners who want to build genuine mathematical and computational thinking — not passive video consumption. As of 2025 it claims 10 million registered users and 90+ guided courses across Math, Computer Science, Data Science, Science, and Logic. Positioning is squarely anti-video: "Learn by doing" is the tagline and the entire product enforces it. It competes less with Coursera/Udemy (video-lecture platforms) and more with Duolingo/Khan Academy — but aims for a premium, adult-skewing, aesthetically serious version of that lane.

---

### Signature UX/UI patterns

**Navigation & global structure**

- Top navigation bar: logo left, primary CTA "Go Premium" button right — visible everywhere, including during free-tier lesson play. No cluttered mega-menu.
- Three top-level subject buckets (Math / Computer Science / Science+Data) are the primary discovery axes; a fourth informal one is Logic & Reasoning.
- Learning Paths page sits between the catalog and individual courses — it surfaces curated sequences (e.g. Foundational Math, Python, Data Analysis) as a separate layer so users who don't want to choose can follow a prescribed path. This is a deliberate tension design: structured path vs. free browse is explicit, not hidden.

**Catalog & discovery**

- Course grid organized into category rows. Each course rendered as a card with course title, a short descriptor line, difficulty hint, and a small illustrative icon/thumbnail (geometric, abstract — not stock photography).
- "New Courses" filter available. Popular courses surfaced monthly. No complex tag/filter system — the catalog is curated enough that faceted search isn't needed.
- First chapter of every course is free; subsequent levels are paywalled. The lock state is visible on the course card itself before you enter — no bait-and-switch.

**Lesson player** (the signature component)

- No video. Every lesson is a sequence of interactive steps: a short conceptual framing text + an interactive problem (drag-and-drop, slider, multiple-choice with visual options, fill-in, embedded simulation). Explanation comes after the attempt — never before.
- Problem-first methodology: you are dropped into a puzzle before receiving theory. The theory is unlocked by your attempt, correct or wrong.
- When wrong: an animated explanation plays showing *why*, with interactive elements so the learner can re-explore the solution actively. This is not "here is the answer" — the explanation is itself interactive.
- Hints available on most problems (progressive reveal, not full solution dump).
- Step length is designed for ~15 min lessons; actual time is 30-45 min for hard content. Lessons are broken into numbered steps visible in a side/top progress strip.
- "Jump Ahead" affordance — lets confident users skip already-mastered steps.
- "Show Explanation" toggle on problems — optional scaffolding, not forced.
- Coding courses use an embedded coding environment with "Start Practice" button launching an inline IDE panel.

**Progress & gamification**

- XP earned per completed lesson and problem. Repeating completed content does NOT re-award XP (anti-farming).
- Streak: consecutive days tracked. Must complete 3 problems or 1 full lesson per day. Streak Charges (max 2 banked, never expire) protect against missed days — preserves streak without extending it, a clever honesty mechanic.
- Leagues: weekly competitions, 30 learners per league, 10 named tiers (Hydrogen → Einsteinium — thematic naming). League standings reset every Sunday at 8 PM PT. Visible on the home page inside a "Leagues" section.
- Level Gameboard: a visual map of lesson nodes connected by animated paths. Nodes and connecting lines are color-coded by subject/topic. Built in Rive — same file runs on Android, iOS, and web identically.
- Badges: earned for completing courses, mastering skills, consistent practice, challenge participation. Displayed on user profiles and designed to be shareable.
- In-lesson celebrations: correct answers trigger whimsical Rive animations + XP counter pop. Struggle states trigger encouragement moments (not silence or failure penalty).

**Onboarding**

- Short questionnaire on first sign-up: role selection (student / professional / hobbyist / parent-teacher) + learning goals → drives personalized path recommendation. Roughly 12-step flow.
- Notably places both sign-up AND paywall pitch before full content access — early premium push, but softened by allowing Level 1 (sometimes Level 2) free before the gate.
- 7-day free trial on all paid plans; no credit card until trial end is typical but not always enforced.
- Personalized suggestion page shown post-onboarding: recommended courses + recommended path based on role selection. Users can also skip and browse freely.

**Pricing & paywall**

- Three plans: monthly ($24.99/mo), annual (~$13.49/mo billed $161.88/yr), group/family (up to 6 members).
- "Go Premium" CTA is persistent in the top nav throughout the free experience.
- Premium unlock shown in-context during lesson play when reaching a locked step — not a separate page redirect. The lock UI appears inline within the course flow with a subscription pitch card.
- Koji (AI tutor) is premium-only; limited free access exists. It can see and manipulate interactive lesson elements — not just a text chat overlay. It guides through thinking without revealing answers (Socratic model).

---

### Concrete UI details

**Color & dark theme**

- Primary brand dark: deep navy/dark-brown backgrounds (not pure black — reviewers describe a "dark brown" warmth to it). Avoids the cold pure-black look.
- Accent colors are bright and subject-coded: each learning path/topic gets its own vivid hue for the gameboard nodes. Not a single accent — a palette per domain.
- Homepage hero: dark background + prominent "Get Started" CTA, geometric/tangram-influenced illustration style.
- Light mode exists but the brand identity and aesthetic premium feel leans dark.

**Typography**

- Clean, geometric sans-serif throughout. High contrast against dark backgrounds. Body text is comfortable and readable — not condensed. Lesson text is sized for reading, not scanning; density is moderate, not dense.
- Labels and UI chrome are small but clear. No decorative serifs.

**Motion & animation**

- Rive is the primary animation engine — enables cross-platform identical playback. Key animated surfaces:
  - Loading screen: tangram-style geometric puzzle animation (on-brand, not a generic spinner)
  - Gameboard nodes and path connectors: animated state transitions (unlocked/locked/completed)
  - Streak counter: numerical counter synchronized with animation
  - In-lesson celebration: per-correct-answer micro-celebration
  - Learning companion character: guides to next lesson
- Motion philosophy: "deliberately calibrated art, UI, and motion to convey both playful feel and necessary guidance." Avoids over-distracting game elements that break concentration on STEM problems.

**Cards**

- Course catalog cards: moderate density, icon/illustration thumbnail, title, short descriptor, category tag, difficulty. No excessive metadata. Lock badge overlaid for premium content.
- Lesson step cards: full-width canvas for interactive content. Clean white/dark surface with the interactive element centered — no sidebar clutter during problem-solving.
- Paywall card: appears inline in lesson flow when hitting a locked step; offers plan comparison in a feature table format before checkout redirect.

**Information density**

- Homepage: low density, hero + featured paths + category grid. Generous whitespace. Premium feel from restraint.
- Course catalog: medium density — grid of cards, not a dense list. Browsable at a glance.
- Lesson player: low density per step. One problem at a time. No scrolling during active problem solving. Progressive reveal is the dominant pattern.
- No dashboards with 8 widgets. Progress is surfaced contextually (gameboard, streak widget, league panel) rather than on a dedicated analytics page.

**Key screens in order**

1. Homepage hero (dark, "Learn by doing", Get Started)
2. Onboarding questionnaire (role/goals, 12 steps)
3. Personalized path recommendation page
4. Course catalog grid (categorized, lock state visible)
5. Course overview (levels listed, free vs locked indicator, path context)
6. Lesson player (problem → attempt → animated explanation → next step)
7. Completion celebration (XP earned, streak update, next lesson prompt)
8. Leagues/home page (league standing, XP weekly progress, streak status)
9. Paywall inline card (triggered at locked step, not a separate page)

---

### What it does exceptionally well

1. **Problem-first sequencing with no escape valve.** There are no videos to passively watch. Every step requires an action. This is a hard product constraint, not just a design choice — it differentiates Brilliant from 95% of the market.

2. **Rive-powered motion as a learning signal.** Animations are not decoration — they ARE the explanation in many cases. The animated tangram loader, color-coded gameboard, and celebration micro-interactions are all semantically loaded, not cosmetic.

3. **Streak Charges as a safety valve.** The design acknowledges real user behavior (missing a day) without destroying the streak system's motivational value. Capping charges at 2 prevents abuse while keeping the system humane.

4. **League naming that scales prestige.** Hydrogen → Einsteinium uses element names — thematically connected to science and intrinsically conveying relative rank to educated users. Non-arbitrary naming that reinforces brand identity.

5. **Koji's in-context AI integration.** The AI tutor can manipulate the same interactive elements the learner is working with — it's not a text bubble next to a screenshot. This is a genuinely harder technical and design challenge executed well.

6. **Paywall placement without betrayal.** The lock appears after Level 1 is consumed, not before content is touched. Users have invested enough to understand the value proposition before hitting the gate. The gate itself is inline, not a redirect-away jarring interruption.

7. **Learning path + free browse coexistence.** The system offers both curated sequences AND free exploration without forcing a choice or hiding either. Paths are a recommendation, not a cage.

---

### Takeaways for StarCi

1. **Problem-first sequencing inside lesson steps.** StarCi lessons currently present theory before challenge. Consider a "try first" toggle or a lesson step type that drops the learner into a problem before explanation — even for concept lessons. The aha-moment after struggling is more sticky than reading before trying.

2. **Gameboard node visualization for module/lesson maps.** StarCi's content-map rail (accordion list) could evolve into a visual node path per module — color-coded by module theme, animated completion state. HeroUI + Framer Motion or Rive can handle this. The key is the path IS the progress indicator — eliminating the need for multiple progress bars (see `one-progress-bar-at-a-time` draft rule).

3. **Streak Charges as a UX safety valve.** StarCi has streaks. Consider a max-2 "streak shield" mechanic (earned, not bought) that protects against missed days without resetting. This reduces user anxiety around travel/busy days without inflating streak counts.

4. **Subject-coded accent palette per module/course.** StarCi's teal accent is uniform across all content. Brilliant differentiates content domains with per-topic color on the gameboard. StarCi could assign each major course (System Design, DevOps, Fullstack) a secondary accent hue used on cards, progress nodes, and league badging — while keeping global chrome in teal.

5. **Koji-equivalent: AI tutor that sees the current problem.** StarCi's AI co-pilot (`askContentAi`) currently answers questions about content body. A next-level version would be context-aware of which lesson step / challenge the user is on and which code they've written — similar to Koji manipulating interactive elements. The credit-gating already exists; the missing piece is richer context injection.

6. **League naming that is on-brand.** StarCi's leagues can use thematic names tied to the engineering/tech domain (e.g. Intern → Junior → Mid → Senior → Staff → Principal → Fellow → Architect → Distinguished → Fellow Emeritus) rather than generic "Bronze/Silver/Gold." Naming is cheap to implement and substantially elevates perceived craft.

7. **Inline paywall, not redirect.** When a StarCi free user hits a premium-locked lesson or challenge, show the upgrade pitch inline as a card within the lesson flow — not a navigation away to `/pricing`. The user has momentum; preserve it. The card shows what they unlock, current plan, CTA to upgrade. This matches Brilliant's non-jarring gate pattern.

8. **Persistent "Go Premium" in nav, not buried in settings.** StarCi currently surfaces upgrade paths inconsistently. A persistent top-right nav CTA visible across all non-premium surfaces (with smart hiding once subscribed) drives conversion without being intrusive — Brilliant's simplest and most effective growth pattern.

9. **Hint system on challenges.** Brilliant's progressive-reveal hint system (not "show answer," but a series of nudges) directly maps to StarCi's coding challenges. Implementing a 3-step hint ladder (approach hint → pseudocode hint → key insight hint) with each hint costing a small credit amount would add value and monetize hint usage as a natural extension of the AI credit system.

10. **Calibrated motion, not celebration inflation.** Brilliant deliberately avoided over-gamifying (per the ustwo case study) to preserve concentration for STEM material. StarCi should follow the same philosophy: celebration animations are reserved for meaningful moments (lesson complete, streak milestone, league promotion) — not for every button click. Motion = signal, not noise.

---

### Sources

- [Brilliant: Learn Math & Coding UI Breakdown — ScreensDesign](https://screensdesign.com/showcase/brilliant-learn-by-doing)
- [Brilliant.org x ustwo — design case study](https://ustwo.com/work/brilliant/)
- [How Brilliant.org motivates learners with Rive animations — Rive blog](https://rive.app/blog/how-brilliant-org-motivates-learners-with-rive-animations)
- [Brilliant.org Review 2026 — e-student.org](https://e-student.org/brilliant-org-review/)
- [Brilliant.org Review 2026 — scorebeyond.com](https://scorebeyond.com/brilliant-org-review/)
- [Brilliant.org Review 2026 — missiongraduatenm.org](https://missiongraduatenm.org/brillant-org-review/)
- [Brilliant.org Pricing Guide — myelearningworld.com](https://myelearningworld.com/brilliant-pricing/)
- [Brilliant.org Review — Learnopoly](https://learnopoly.com/brilliant-org-review/)
- [Is Brilliant Worth It — nibble-app.com](https://nibble-app.com/blog/is-brilliant-worth-it)
- [How Brilliant Uses Gamification — Trophy blog](https://trophy.so/blog/brilliant-gamification-case-study)
- [Product Features — Brilliant Help Center](https://brilliant.org/help/features/)
- [Brilliant (website) — Wikipedia](https://en.wikipedia.org/wiki/Brilliant_(website))
- [Brilliant.org Review — myelearningworld.com](https://myelearningworld.com/brilliant-review/)
