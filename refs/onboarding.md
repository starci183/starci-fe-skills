## Onboarding & Activation

### Dominant Patterns

These recurring solutions appear across Duolingo, Coursera, Codecademy, Brilliant, Udemy, Khan Academy, and edX:

**1. Product-First / Deferred Registration (PLG Onboarding)**
The highest-impact shift in edtech UX. The user touches core value — answers a question, runs a snippet, translates a phrase — before being asked for an email address. Duolingo canonized this: the onboarding is 7 steps entirely inside the product experience; account creation comes only after the first mini-lesson is complete. The registration prompt is reframed as "save your progress" rather than "create an account." Codecademy's mobile app similarly shows the exercise UI before gating on signup.

**2. Intent / Goal Funnel (3–6 questions, progressive)**
Every platform collects 2–4 intent signals before routing the user. The canonical shape is:
- What do you want to learn / what brought you here?
- What is your current level?
- What is your daily time commitment / goal?
- (Optional) What is your end goal — career, travel, curiosity?

Each answer is used to generate a personalized recommended path rather than dumping a catalog. Crucially, the funnel is never more than 5–7 steps, each self-contained with one decision, user-triggered (the user taps "Next", not an auto-advance timer), and with visible progress.

**3. Placement Assessment (Binary or Adaptive)**
Platforms with tiered content offer a placement gate: a short diagnostic that branches beginners from returners. Duolingo offers "I'm new" vs. "I know some [language]" — the latter unlocks a short adaptive placement test. Brilliant uses actual math problems (not preference sliders) as the skill signal. Codecademy shows a binary "I'm new / I know some coding" and routes to either a recommendation wizard or self-guided catalog search.

**4. Single-Screen Goal Commitment**
After intent is captured, one screen locks the user into a specific, measurable commitment — typically a daily time goal presented as 3–4 discrete options (5 min / 10 min / 15 min / 20 min). The selection is immediately confirmed with an animation (Duolingo shows a motivational message from Duo tied to the chosen goal). This is the activation of the habit loop before any content is consumed.

**5. Immediate First Win — no feature tour**
The fastest-converting platforms skip the feature tour entirely. Time-to-first-value for Duolingo is documented at 3–4 minutes from download to completing a real interaction. Brilliant drops the user into an interactive math puzzle as the onboarding itself. Khan Academy and edX are the counter-examples: they show a dashboard with multiple CTAs and no prescribed first step, which creates decision paralysis and higher early drop-off.

**6. Gamification Hooks Introduced During Onboarding, Not After**
Streaks, XP, and daily goals are set up before the user has earned any of them. Duolingo introduces the streak concept in step 3 of onboarding (goal-setting screen), before the user has completed a single lesson. Brilliant shows the XP counter and streak tracker on the home screen from day one, creating an empty container the user immediately wants to fill. The psychological mechanism is goal-gradient: the further from zero the perceived starting point, the more motivated the user.

**7. Contextual Empty States (Action-Oriented, Not Apologetic)**
Empty dashboard states are treated as CTA surfaces. Platforms doing this well replace "You have no courses yet" with a specific action: "Start your first lesson in [Recommended Path]" with a primary button. Codecademy's path dashboard for new users shows the first recommended course card already populated, minimizing blank-state anxiety. Duolingo's empty lesson history shows Duo in an encouraging pose with a direct "Start" CTA.

**8. Persona-Based Flow Branching**
Codecademy explicitly identified two user types (explorers vs. goal-directed) and built two distinct paths through onboarding: one questionnaire-driven recommendation flow, one direct catalog search. The choice is offered on a single screen: "Give me a recommendation" vs. "I'll explore on my own." Neither is hidden or framed as secondary. Udemy does a lighter version: goal selection (personal development / career change / academic) and category selection are sequential screens that gate the home feed content.

**9. Social Proof at Signup Friction Points**
Trust signals are placed next to form fields and primary CTAs, not on marketing landing pages. Used patterns include enrollment counts ("4.2 million learners"), completion testimonials, and skill outcome stats. Coursera's signup pages embed "70% of learners report career outcomes" in proximity to the email field.

**10. Progressive Disclosure / Everboarding**
Features beyond the critical first session are not surfaced in onboarding. Leaderboards, advanced settings, streak freezes, certificate pathways — these appear contextually after the user has demonstrated activation (completed a lesson, returned on day 2, hit a milestone). Duolingo's league system is not visible until the user finishes a full lesson unit. This prevents the "tourist effect" where new users read about features rather than use them.

---

### Concrete Examples Per Platform

**Duolingo**
- Flow: language pick → motivation ("Travel / Career / Brain Training" with icons) → level self-assessment → placement test option for returners → daily goal selection (5 / 10 / 15 min) → first interactive lesson → account creation prompt ("Save your progress")
- Layout: single-decision full-screen cards, one action per screen, large tap targets, mascot (Duo) present throughout
- Motion: animated progress bar at top of each onboarding screen; Duo waves/cheers on goal confirmation; celebratory particle burst on first correct answer
- Empty states: illustrated Duo with direct "Start lesson" CTA; no text-only error messages
- Gamification in onboarding: streak concept introduced at goal-setting screen; XP counter appears on first lesson completion even before account creation
- Time-to-first-value: 3–4 minutes from launch to first lesson interaction
- Key stat: 7-day streak users have 90% retention at day 30 vs. 20% without; streak iOS widget increased commitment by 60%
- Source: [GoodUX/Appcues Duolingo breakdown](https://goodux.appcues.com/blog/duolingo-user-onboarding), [Juno School](https://www.junoschool.org/article/duolingo-onboarding-experience/), [UserGuiding](https://userguiding.com/blog/duolingo-onboarding-ux)

**Codecademy**
- Flow: "What do you want to build?" (goal selection) → "Give me a recommendation" vs. "I'll explore" branch → questionnaire (interest, experience, time commitment) → recommended Career Path or Skill Path card → first interactive lesson
- Two-persona architecture: recommendation wizard for beginners, direct catalog for experienced users
- Context-aware: users arriving from a specific course URL skip the wizard entirely and drop into that course (reducing recommended-path friction for directed traffic)
- Mobile cross-bridge: users on mobile are told to continue on desktop for full experience, then shown the companion app CTA
- Copy principle: "welcoming, easy-to-understand, streamlined" — no jargon in onboarding copy
- Source: [Codecademy onboarding case study by Jackie Liu](https://jackieis.online/projects/codecademy/)

**Brilliant**
- Flow: topic/interest survey (select ~5 courses) → actual math/logic problems as skill assessment (not sliders or self-rating) → account creation → paywall screen (with trial timeline + testimonials) → learning path visualization
- Onboarding uses 12 steps; skill signal comes from doing a real problem, not answering "how good are you?"
- Visual design: color-coded learning path nodes built in Rive (each topic a distinct color), animated connecting lines showing progression; "tangram-style" thematic loading animations instead of generic spinners
- Gamification: XP counter and streak tracker visible from first session; "Blorbs" character companions guide between lessons
- Lesson design: interactive elements on incorrect answers (not just static explanations); "weight-scale puzzles" for algebra introduce concepts visually
- Key design principle: "STEM requires deep focus — gaming elements constrained to celebrations and transitions, not core interaction"
- Source: [ScreensDesign Brilliant breakdown](https://screensdesign.com/showcase/brilliant-learn-by-doing), [ustwo x Brilliant case study](https://ustwo.com/work/brilliant/), [Rive blog on Brilliant animations](https://rive.app/blog/how-brilliant-org-motivates-learners-with-rive-animations)

**Udemy**
- Flow: splash → sign-in/signup → interest/category selection → goal selection → course recommendations feed → wishlist save → notifications permission
- Goal and category selection both appear before first course recommendation — personalization gates discovery
- Navigation: tab-based (Home, Search, Library, Categories) established from onboarding screen 1
- Empty state: "no search results" handled with specific screen rather than inline text
- Micro-interactions: "Add to list" → "Saved to wishlist" immediate confirmation; notification permission mid-flow (after first value moment)
- Source: [Page Flows — Udemy iOS onboarding](https://pageflows.com/ios/products/udemy/)

**Coursera**
- Career-goal-first: users state a career goal early; the system generates a complete learning path from prerequisites through certificate
- Trust signals embedded at signup: "70% of learners who stated a career goal and completed a course report career outcomes" placed near the primary CTA
- Personalized recommendations shown on first dashboard visit based on stated goal
- Weakness noted across reviews: initial dashboard can feel overwhelming without a prescribed first step; course catalog density creates friction vs. Duolingo's single-next-step model
- Source: [Coursera blog — learning paths](https://blog.coursera.org/new-coursera-start-finish-learning-paths-starting-new-career)

**Khan Academy**
- Teacher/parent-oriented onboarding has explicit tutorial sequences; student-direct flow is lighter
- Mastery goals (Unit Mastery / Course Mastery) can be self-set or teacher-assigned; empty goal state shows a direct CTA to set a goal
- Dashboard approach: subject cards on home screen with progress indicated; no single prescribed first step → lower activation vs. Duolingo-style funnels
- Strength: grade/topic placement is explicit and fast (pick grade → subject → unit)
- Source: [Khan Academy Help — Mastery goals](https://support.khanacademy.org/hc/en-us/articles/360031123551)

**edX**
- Noted by reviewers as requiring sign-in/registration before product experience — opposite of PLG model
- Interface described as "simple and clean, similar to Khan Academy, but may feel outdated"
- No documented placement assessment in core learner flow
- Source: [LearnersView MOOC comparison 2025](https://learnersview.com/top-5-mooc-platforms-compared-coursera-edx-udemy-futurelearn-khan-academy/)

---

### DO / DON'T Heuristics

**DO**
- Lead with the product, not the form. Defer account creation until after the user has completed one meaningful interaction (answered a question, run code, completed a lesson). Frame signup as "save your progress."
- Limit the intent funnel to 4–5 single-decision screens. One choice per screen. Let the user advance manually (no auto-scroll). Show a progress indicator (dots, numbered steps, or a thin bar at the top).
- Use actual skill-signal activities (mini-quiz, drag-match, code snippet) rather than self-rating sliders for placement. Real performance data is more accurate and creates immediate engagement.
- Introduce the gamification container (streak, XP, goal) before the user earns anything. An empty streak counter on day 0 creates a goal-gradient pull toward day 1.
- Make empty states actionable: one primary CTA pointing to the highest-value next step. Illustration + short direct copy + one button. No secondary links in the empty state.
- Branch on user type at the first fork: "Recommend a path for me" vs. "I'll find it myself." Both are first-class citizens.
- Place social proof (enrollment count, outcome stat, testimonial) adjacent to friction moments: sign-up form, paywall screen, commitment confirmation.
- Show the learning path visualization immediately after onboarding: color-coded nodes, current position highlighted, first locked item is the next tap target.
- On mobile: bottom-sheet confirmations, large tap targets (min 48px), single-column card stacks for decision screens.

**DON'T**
- Don't show a feature tour or tooltip sequence before the user has done anything. Tours are read, not internalized; first-time usage is internalized.
- Don't require email/password before showing value. Platforms that gate immediately (edX pattern) see higher early bounce.
- Don't collect more than 5 fields on signup. Every additional field reduces completion. Push secondary data collection (bio, avatar, notification preferences) to post-activation.
- Don't drop the user on an empty dashboard with no prescribed first step. Decision paralysis is real; the first action must be obvious and singular.
- Don't use self-rating ("How experienced are you? Beginner / Intermediate / Advanced") as the only placement signal — users miscalibrate. Use a real task.
- Don't show all gamification mechanics in onboarding. Leagues, leaderboards, treasure chests, badges — these dilute focus. Surface one mechanism (streak or XP) in onboarding; reveal others as earned milestones.
- Don't animate transitions in a way that adds latency to the critical onboarding path. Celebration animations on correct answers are high-value; page-transition animations that slow decision screens are friction.
- Don't use the same empty state across all contexts. A first-time learner's empty course list and an empty quiz-history state need different CTAs and copy.
- Don't scatter progress bars across every list item (see StarCi's own draft rule: `one-progress-bar-at-a-time.md`). In onboarding, one thin progress bar at the top of the wizard; in the course map, one bar per open section.

---

### Takeaways for StarCi

StarCi is a freemium platform with courses → modules → lessons/challenges, AI credit co-pilot, XP/leagues/streaks/badges, and a Next.js + HeroUI v3 + Tailwind v4 stack with teal #00a898 accent.

**1. Implement PLG signup: product first, email second.**
Let an unauthenticated user: pick a course → start lesson 1 of module 1 → complete the first content card (or first challenge). Only then prompt "Create a free account to save your progress." This maps to the Duolingo pattern and should be achievable with Next.js middleware guarding /api routes while keeping the lesson reader fully server-rendered.

**2. Build a 4-screen intent funnel.**
- Screen 1: "What do you want to learn?" — card grid of tracks (System Design, FullStack, DevOps, etc.) with icons, single-select. Teal accent on selected card border.
- Screen 2: "What's your experience level?" — 3 options (New to this / Familiar with basics / I want to go deep). Optionally follow with a 3-question mini-quiz for placement.
- Screen 3: "How much time per day?" — 3 options (10 / 20 / 30 min). On select, animate a visual of a daily streak starting at 1.
- Screen 4: Recommended course card + "Start your first lesson" primary CTA. This is the activation moment.

**3. Introduce the streak + XP container on day 0.**
Show the streak indicator (flame icon, "Day 1") and an XP bar at 0/100 on the dashboard immediately after onboarding. The empty container is the pull. First lesson completion fills it partially and triggers a small celebration (confetti burst, XP counter animation). In HeroUI terms: a `Chip` or `Badge` component with a `motion`-powered counter increment.

**4. Design for the two-persona fork.**
- Guided: "Recommend a course for me" → intent funnel → landing on recommended course.
- Self-directed: "Browse all courses" → catalog grid → no wizard friction.
Display both options on screen 1 of signup flow. Self-directed users skip to the catalog but still get the streak/XP container setup.

**5. Empty-state patterns (content-first, whitespace-heavy).**
Per StarCi's design vibe (content-first, lots of whitespace):
- My Courses (empty): Centered illustration (minimal line art, teal accent) + "You haven't started a course yet." + primary button "Find a course" + secondary ghost button "See recommended".
- My Challenges (empty): Code icon illustration + "Complete a lesson to unlock challenges." (locked state, not an error state).
- AI Credit (empty / zero): Show the credit pool bar at 0 with a "How credits work" link, not a blank space. The visible-but-empty container communicates what the feature is.

**6. Placement diagnostic for challenge difficulty.**
When a user first enters a course, offer: "Have you seen this material before? [Yes, show me harder challenges / No, start from basics]." Route to easy vs. medium/hard tier without a multi-step test. The "yes" path is the Duolingo returner placement UX adapted for StarCi's challenge tiers.

**7. Social proof at the paywall / freemium gate.**
When the user hits a premium-locked content node (the "challenge premium lock" referenced in recent commits), the lock screen should include: number of learners who completed this challenge, one short outcome quote, and the specific premium feature being unlocked (AI co-pilot credits, challenge access). Position these above the upgrade CTA, not below.

**8. Gamification introduction order.**
Onboarding: introduce streak + daily goal (screen 3 of funnel).
After first lesson: show XP earned, animate XP bar, reveal badge earned.
After 3 lessons: reveal league system ("You've entered Bronze League — compete this week").
Don't surface leagues, leaderboards, or badge gallery during onboarding itself.

**9. Navigation density on first visit.**
On the very first dashboard visit, reduce sidebar / nav clutter. Consider a "simplified mode" for unauthenticated or just-signed-up users: show only My Courses, Find a Course, and a prominent "Continue where you left off" CTA. Surface Settings, AI Usage, Payments, Profile in the nav only after the first lesson is complete. This follows progressive disclosure and prevents the "empty dashboard paralysis" observed on edX and early Coursera.

**10. Motion budget.**
StarCi uses content-first + clean + lots of whitespace. Apply the Brilliant principle: animations celebrate progress transitions (lesson complete, XP gain, streak day incremented), not navigation. Page transitions should be subtle (fade, 150ms). Celebrate-at-milestone animations can be richer (confetti, scale pulse on XP counter) — these are earned moments.

---

### Sources

- [GoodUX / Appcues — Duolingo user onboarding breakdown](https://goodux.appcues.com/blog/duolingo-user-onboarding)
- [UserGuiding — Duolingo onboarding UX in-depth](https://userguiding.com/blog/duolingo-onboarding-ux)
- [Juno School — Duolingo onboarding: 5-minute masterclass](https://www.junoschool.org/article/duolingo-onboarding-experience/)
- [Orizon — Duolingo gamification secrets: streaks & XP](https://www.orizon.co/blog/duolingos-gamification-secrets)
- [Jackie Liu — Codecademy onboarding case study](https://jackieis.online/projects/codecademy/)
- [ScreensDesign — Brilliant UI breakdown](https://screensdesign.com/showcase/brilliant-learn-by-doing)
- [ustwo x Brilliant — game feel design case study](https://ustwo.com/work/brilliant/)
- [Rive blog — Brilliant.org animations](https://rive.app/blog/how-brilliant-org-motivates-learners-with-rive-animations)
- [Page Flows — Udemy iOS onboarding flow](https://pageflows.com/ios/products/udemy/)
- [Coursera blog — learning paths for career goals](https://blog.coursera.org/new-coursera-start-finish-learning-paths-starting-new-career)
- [Khan Academy Help — Mastery goals](https://support.khanacademy.org/hc/en-us/articles/360031123551-How-can-I-view-my-students-progress-towards-their-Mastery-goals)
- [LearnersView — Top 5 MOOC platforms compared 2025](https://learnersview.com/top-5-mooc-platforms-compared-coursera-edx-udemy-futurelearn-khan-academy/)
- [UserGuiding — 100+ user onboarding statistics 2026](https://userguiding.com/blog/user-onboarding-statistics)
- [ProductLed — PLG benchmarks and freemium conversion](https://productled.com/book/onboarding)
- [Nielsen Norman Group via StriveCloud — progressive disclosure reduces task time 20–40%](https://www.strivecloud.io/blog/gamification-examples-onboarding)
- [Duolingo Medium — streak system detailed breakdown](https://medium.com/@salamprem49/duolingo-streak-system-detailed-breakdown-design-flow-886f591c953f)
