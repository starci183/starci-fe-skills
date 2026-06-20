## Khan Academy

### What & who

**Positioning:** Nonprofit ("free, world-class education for anyone, anywhere") — the definitive free K-12 and introductory college-level learning platform. No paywalled core content; revenue comes from donations and an optional AI-tutor add-on (Khanmigo).

**Primary audience:** K-12 students (strong North American/English-speaking base), homeschoolers, adult self-learners, and teachers who assign it as supplemental practice. Secondary audience: school districts buying Khanmigo + data integrations.

**Scale / credibility:** 100M+ registered learners, partnerships with College Board (SAT prep), LSAT, MCAT. Wikipedia-level brand recognition in "free education."

---

### Signature UX/UI patterns

#### Navigation & catalog/discovery

- **Top global nav** — minimal header: Khan Academy wordmark (green-blue), hamburger-style subject megamenu (Math, Science, Computing, Humanities, etc.), search bar, and a "Donate" CTA. Minimal. No persistent megabar.
- **Left sidebar (authenticated)** — collapsible rail showing: Home, Classes (teacher-assigned), Courses I'm Taking, Learner Queue, Progress/Mastery Goals. An arrow button collapses it entirely for more reading room. Inside a course, the rail becomes a course table of contents — units listed vertically, each expandable to reveal lessons (videos, articles, exercises) within that unit.
- **Course/subject discovery** — subject landing pages organized by discipline → grade level. Within a course page, units are stacked vertically as accordion cards. Each card shows unit title, number of skills/videos/articles, and a mastery percentage (e.g., "Unit mastery: 42%"). Users tap to expand and see lesson rows inside.
- **Content types are explicit with icons** — every row in a unit is labeled: video (play icon), article (text icon), exercise (pencil icon), quiz, unit test, course challenge. No ambiguity.
- **Learner Queue** — introduced in the 2024 classroom redesign. Instead of raw assignment list, a task-focused view shows prioritized "Daily or Weekly Missions" — next items the student should do. Reduces "what am I supposed to do?" friction.
- **Search** — global keyword search available from header. Subject dropdown also available as a secondary discovery path.

#### Lesson player

**Video player:**
- ~2/3 of screen for video, right panel shows where student is in the unit (about 1/3 screen). Shaded play buttons mark fully-watched videos, half-shaded = partially watched, unshaded = unplayed.
- Controls: standard play/pause, scrubbing, speed (0.5×–2×), captions, fullscreen, quality selector.
- "Transcript" tab allows following along text. "Tips & Thanks" for community notes.
- After video: embedded quick questions (optional), or direct link to related exercise.

**Exercise interface:**
- Clean white center column with question text; multiple-choice answers are tappable cards, or free-response input field for math.
- **Hints system** — a "Hint" button reveals hints one at a time (progressive disclosure, not all at once). Each hint is a step of worked solution. Counting used hints doesn't punish the score but does affect mastery assessment.
- **Immediate feedback** — correct = green checkmark + brief celebration; wrong = red X + "Try again" or "Show answer."
- Below the answer area: "Need help? Watch a video" cross-link to the relevant lesson video. Article links also provided.
- Exercise progress shown as a small row of dots or progress indicator at top of question area showing questions answered in the current session.
- Mastery state badge appears on exercise completion (e.g., "You reached Proficient!") with a brief animation.

#### Progress & mastery system

Khan Academy's most distinctive UX. Built around the concept that learners should not move on until proficient, regardless of time.

**Four mastery levels per skill** (explicit labels, tracked per skill):
1. **Not Started** — no activity
2. **Attempted** (formerly "Struggling") — practiced but not reaching threshold
3. **Familiar** — scored 70–85% on exercise, or correct on quiz/test
4. **Proficient** — scored 100% on exercise starting from Familiar, or correct on quiz/test
5. **Mastered** — reached Proficient then answered correctly on a Unit Test or Course Challenge

**Mastery points:** Each skill worth up to 100 points. Familiar = 50 pts, Proficient = 80 pts, Mastered = 100 pts.

**Mastery visualization on course/unit pages:**
- Each unit card shows "Unit mastery: X%" as text + a progress visualization (colored cells or bar). Grey = not practiced, progressively darker blue = increasing mastery. Per the 2023 update description: "grey = not practiced; blue = familiar, darker blue = proficient/mastered."
- A mastery percentage ring or bar at course level summarizes overall course completion.
- Unit progress bars were removed then later replaced by a new per-course level progress bar after the Streaks & Levels feature launched.

**Mastery Challenges** — periodic review exercises that pull from previously learned skills. Completing these can push skills from Proficient → Mastered. Positioned at the bottom of each unit and at course level (Course Challenge).

**Course Mastery Levels (badge/rank tier):**
- Apprentice: 0–24%
- Explorer: 25–49%
- Pioneer: 50–74%
- Adventurer: 75–99%
- Sage: 100%
These are displayed as milestone badges on the course page.

**Streaks (introduced 2024):**
- Weekly streak — requires earning "Proficient" (or better) on at least 1 new skill per week (Mon–Sun Pacific). Displayed prominently; losing a streak is a strong retention driver.

**Levels & skill points:**
- Every time a skill reaches Proficient or better: earn 1 skill point.
- Accumulate skill points → go up in course Level. Levels break a long course into tangible milestones; "level up" triggers a celebration animation.
- Course level shown in learner home and sidebar.

**Energy points (legacy, still present):**
- Earned for all activity (not a mastery measure; effort metric). 50 pts per correct mastery challenge question, 5 pts for skills already practiced. Used historically to unlock avatars/badges.

**Badges:**
- Space-themed badge collection (meteorite, moon, earth, sun, black-hole tiers) based on energy points.
- Achievement badges for specific accomplishments (completing courses, streaks).
- Badge showcase visible on public profile page.

**Gems (Khanmigo classroom pilot):**
- Students earn gems by completing exercises, quizzes, Khanmigo activities. Class pooled total; reaching class goal triggers celebration. Gems unlock cosmetic Khanmigo accessories (hats, eyewear). This is the "teacher-class social gamification" layer — layered on top of individual mastery.

#### Onboarding

- **Signup:** "Continue with Google / Apple / Facebook / email" — 4 auth options on one page. No paywall.
- **Role selection immediately:** "I'm a learner / I'm a teacher / I'm a parent" — routes to different experiences.
- **Grade level + subject picker** for learners after signup — populates the "Courses" recommendation on Home.
- Teachers go through a setup wizard: pick subject → add students (via class code or Google Classroom sync). Revised after research showed teachers wanted to explore content before committing students.
- No long tutorial; learning by doing — first action is often watching a video or doing an exercise.

#### AI — Khanmigo

- Chat interface embedded within the lesson player (sidebar chat panel) or accessible as standalone tutor.
- **Socratic by design** — does not give direct answers; responds with guiding questions ("What do you think the first step is?").
- Voice input/output ("you talk, Khanmigo types") — eliminates typing barrier for young users.
- Image upload in "Tutor Me: Math and Science" — students photograph handwritten work or textbook problems.
- Khanmigo avatar character — customizable with earned accessories (hats from gems).
- **Pricing:** Free for teachers (100%). $4/month or $44/year for learners/parents (up to 10 child accounts). District licensing: $10–$15/student.
- Not gated behind the core content; Khanmigo is a standalone add-on layer.

#### Pricing / free model

- **Everything curricular is free:** all videos, exercises, quizzes, unit tests, course challenges, mastery tracking, streaks, levels, badges.
- **Khanmigo = the only paid feature** — AI tutoring, parent tools (quiz creation, lesson planning). The mission framing ("supports our nonprofit") reduces friction vs. pure commercial paywalling.
- No ads on the learning interface.
- Donation button in header; nonprofit positioning is part of the brand identity.

---

### Concrete UI details

**Information density:** Low to medium. Generous whitespace. Single column for content reading. Course pages have a moderate content list but no overwhelming feature density. The emphasis is on clarity over feature completeness.

**Color palette (Wonder Blocks design system):**
- Rebuilt from 58 colors → 18 functional colors (2018), then re-architected again in 2024–2025 using semantic token layers (Domain → Layer → Context → Intensity).
- **Blue** = primary action color (buttons, interactive elements, links). Described explicitly as "blue denotes action." Estimated to be approximately `#1865f2` range (KA's documented brand blue), used on primary CTAs.
- **Green** = success/affirmative states. Described as "green [is] accompanied by text to connote affirmative messaging."
- **Red** = warning/error.
- Semantic token structure: 9 contexts (Base, Instructive, Neutral, Disabled, Success, Warning, Critical, Knockout, Overlay), each at 3 intensities (Subtle, Default, Strong).
- WCAG compliant: "Strong Foreground tokens pass at 4.5:1+ on all Subtle and Base Background tokens."
- Background is clean white/off-white. No dark mode as a primary experience (though experimental dark mode appeared in mobile app late 2024).

**Typography (Wonder Blocks):**
- Reduced from 8+ typefaces to 5 typefaces, from 119+ type styles to 14 styles.
- Information density increased 11–18% for sans-serif, 26% for serif while maintaining legibility — optimized for low-cost hardware, low-density screens, limited bandwidth.
- Clean, readable sans-serif for body and UI; explicit hierarchy (heading → body → caption).

**Motion:** Celebration moments on level-up, mastery achievement, gem class goal — animated Khanmigo character (party hat, party horn). Otherwise motion is minimal. No gratuitous transitions.

**Cards:** Unit accordion cards on course page — title, skill count, mastery percentage, expand arrow. Lesson rows inside are simple list items with icon + title + mastery state icon. No heavy card shadows; flat or subtle border.

**Key screens:**
1. **Learner Home** — classes row at top left, current courses with level + streak, Learner Queue with today's missions, quick-access to recent activity.
2. **Course page** — unit cards stacked, each showing mastery %, expandable to lesson list.
3. **Video player** — 2:1 video-to-sidebar ratio. Sidebar = unit nav with watched state icons.
4. **Exercise page** — full-width white question area, progressive hints, immediate feedback, cross-link to video.
5. **Mastery/Progress page** — skills grid showing color-coded mastery states across all units in a course.
6. **Teacher dashboard** — Assignments / Reports / Settings tabs; class-level mastery heat map; Learner Queue assignment builder.

---

### What it does exceptionally well

1. **Mastery learning as the organizing principle** — the 4-level skill progression (Attempted → Familiar → Proficient → Mastered) is exposed everywhere consistently. Students always know exactly where they are. This is not just a progress bar — it's a pedagogical contract visible in the UI at every level (skill, unit, course).

2. **Progression legibility without cognitive overload** — skill points + course levels break a year-long course into 10–20 tangible milestones. Learner Queue reduces "what do I do next?" to zero thinking.

3. **Scaffolded help without giving away answers** — the progressive hint system (one step at a time), Khanmigo's Socratic refusal to give direct answers, and "watch a video first" cross-links together model a principled pedagogical scaffold without frustrating power users who don't need it.

4. **Trust through transparency of the free model** — nothing is locked behind a paywall in the core curriculum. The donation framing removes cynicism. Khanmigo add-on pricing is clearly presented and inexpensive ($4/mo). No dark patterns.

5. **Dual-audience design** — same content works for independent self-learner and teacher-assigned classroom use without separate product experiences. The class layer (assignments, learner queue, teacher dashboard) overlays gracefully on top of the self-paced mastery layer.

6. **Design system discipline** — Wonder Blocks enforced a drastic reduction (58 → 18 colors, 119+ → 14 type styles) enabling consistent visual language across a massive content library and multiple audiences. WCAG compliance built into the token system.

---

### Takeaways for StarCi

**1. Expose mastery as a 4-level contract, not just a progress bar.**
Khan Academy's named levels (Attempted / Familiar / Proficient / Mastered) with explicit point values (50/80/100) make progression feel earned and legible. StarCi's lessons/modules could adopt named mastery tiers per content unit visible in the rail and on the course map — not just "completed ✓" but e.g., "Practiced / Understood / Applied / Mastered" with specific completion criteria for each.

**2. The Learner Queue pattern — surface "do this next" prominently.**
Instead of expecting learners to navigate the course map themselves, a homepage "Queue" showing today's 2–3 recommended items (next unfinished lesson, overdue challenge, weekly league task) dramatically reduces decision friction. StarCi's home/dashboard could adopt a daily mission card above the course grid.

**3. Progressive hint system in coding challenges.**
Khan Academy's one-hint-at-a-time pattern maps well to StarCi's coding challenges. Rather than a monolithic "Show solution" CTA, surface step-by-step guided hints — each one a partial reveal. Pair with "Watch the explanation" cross-link to the AI co-pilot.

**4. Socratic AI tutor mode — don't give answers by default.**
Khanmigo refuses direct answers; guides via questions. For StarCi's AI credit co-pilot (askContentAi), consider a "guide me" mode (Socratic) vs. "explain it" mode (direct), with guide mode as the default. Socratic costs fewer credits and teaches better — and is a differentiator vs. raw copy-paste AI tools.

**5. The freemium contract: core content always free, AI add-on priced.**
Khan Academy's model — everything curricular free, AI tutor at $4/mo — sets a clear user expectation. StarCi's freemium tiers should be similarly unambiguous: free tier gets full course content access + basic progress, premium/AI credits are the upgrade vector. Avoid feature-locking core content (videos, lesson text) — lock AI interactions and advanced analytics instead.

**6. Color semantic tokens: one color = one meaning, always.**
Wonder Blocks' semantic token architecture (blue = action, green = success, red = error, strictly) prevents the "50 shades of teal" problem. StarCi's Tailwind v4 token setup should enforce: `accent` (teal `#00a898`) = primary actions only; `success` = green for completion/mastery states; never cross-pollinate. The draft `starci-ui.rules` chip/color conventions (bg-success/10 text-success) are exactly on this track — make it a hard lint rule.

**7. Mastery badge tiers as public profile anchors.**
Khan Academy's Apprentice → Explorer → Pioneer → Adventurer → Sage tiers on course pages create profile identity. StarCi has leagues/XP/badges — the missing piece is per-course mastery rank visible on profiles and in social league comparisons. "You're a Pioneer in System Design" is a shareable identity hook.

**8. Collapse sidebar = more reading room.**
Khan Academy's collapsible left rail (controlled with a single arrow button) is a small but high-value pattern for dense content like StarCi's lesson reader. Per the `one-progress-bar-at-a-time.md` draft rule, the content rail should be controlled (expandedKeys) — the collapse button follows naturally. Add keyboard shortcut (e.g., `[` / `]`) for power users.

**9. Watch-state icons on nav — not just checkmarks.**
Shaded / half-shaded / unshaded play buttons on the lesson nav tell the student their exact engagement state (completed, in-progress, not started) at a glance without a separate progress section. StarCi's content rail icons (currently likely just ✓ / ○) could adopt a three-state: completed / started / not-started with distinct visual treatments.

**10. Streak window = weekly, not daily — less punishing, more achievable.**
Khan Academy's streak requires 1 new skill to Proficient per week (Mon–Sun), not daily login. This is gentler than Duolingo's daily streak but still drives weekly retention. For StarCi's league/streak system, a weekly engagement streak (complete ≥1 challenge or ≥1 lesson per week) would be more sustainable for working adult learners than a daily streak.

---

### Sources

- [Meet the New Khan Academy Classroom Experience — Khan Academy Blog](https://blog.khanacademy.org/meet-the-new-khan-academy-classroom-experience/)
- [Five Ways Khan Academy Is Making Student Practice More Motivating — Khan Academy Blog](https://blog.khanacademy.org/five-ways-khan-academy-is-making-student-practice-more-motivating/)
- [Khan Academy's New Streaks and Levels — Khan Academy Blog](https://blog.khanacademy.org/get-motivated-to-learn-with-khan-academys-new-streaks-and-levels-features/)
- [How We Rebuilt Khan Academy's Color System from the Ground Up — Khan Academy Blog](https://blog.khanacademy.org/how-we-rebuilt-khan-academys-color-system-from-the-ground-up)
- [Wonder Blocks: on the creation of Khan Academy's design system — designsystems.com](https://www.designsystems.com/about-wonder-blocks-khan-academys-design-system-and-the-story-behind-it/)
- [How Khan Academy Leverages Gamification to Boost Retention (2025) — Trophy](https://trophy.so/blog/khan-academy-gamification-case-study)
- [What are Course and Unit Mastery? — Khan Academy Help Center](https://support.khanacademy.org/hc/en-us/articles/115002552631-What-are-Course-and-Unit-Mastery)
- [How do Khan Academy's Mastery levels work? — Khan Academy Help Center](https://support.khanacademy.org/hc/en-us/articles/5548760867853--How-do-Khan-Academy-s-Mastery-levels-work)
- [Update: New mastery progress visualization on Course and Unit pages — Khan Academy Help Center](https://support.khanacademy.org/hc/en-us/articles/18735142028045-Update-New-mastery-progress-visualization-on-Course-and-Unit-pages)
- [Khan Academy Pricing 2026 — ITQlick](https://www.itqlick.com/khan-academy/pricing)
- [Khanmigo Pricing — khanmigo.ai](https://www.khanmigo.ai/pricing)
- [What's New for the 2025-26 School Year: Khan Academy Districts — Khan Academy Blog](https://blog.khanacademy.org/whats-new-for-the-2025-26-school-year-big-updates-from-khan-academy-districts/)
- [2025 Khan Academy Updates Every Parent Should Know — Khan Academy Blog](https://blog.khanacademy.org/2025-khan-academy-updates-every-parent-should-know/)
- [Wonder Blocks GitHub — Khan/wonder-blocks](https://github.com/Khan/wonder-blocks)
- [Khan Academy Review 2026 — BitDegree](https://www.bitdegree.org/online-learning-platforms/khan-academy-review)
- [Khan Academy-A UX/UI Case Study — Dan / Medium](https://medium.com/@danielgordonemail/khan-academy-a-ux-ui-case-study-230640d6ee00)
- [Khan Academy mobile redesign — Scott Liang](https://www.scottliang.com/work/khan-academy-redesign)
