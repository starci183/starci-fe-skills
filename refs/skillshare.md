## Skillshare

### What & Who

**Positioning:** "Explore your creativity" — Skillshare is a subscription-only online learning community aimed at creatives, makers, and professionals who want to build creative and practical skills. It is not an academic credential platform; its tagline and content taxonomy are explicitly creativity-first.

**Audience:** Primarily 18–40 year-old creatives, freelancers, side-hustlers, and self-directed learners. Heavy skew toward design, illustration, photography, filmmaking, content creation, entrepreneurship, and writing. Secondarily: business, productivity, and technology topics. As of 2025 the platform has ~8–10 million registered users with a catalog of 30,000–35,000 classes.

**Business model:** Pure subscription (no a-la-carte purchases). All content requires Premium ($167.88/year on web or promotional $59.99/year via iOS/Android apps, ~$13.99/month averaged). Free tier was eliminated in September 2021. A 7–30 day free trial (credit card required) is the acquisition funnel. Teams plan at $159/user/year exists for B2B.

---

### Signature UX/UI Patterns

**Navigation**
- Top nav bar: persistent, light background. Logo left, Browse menu center-left (reveals mega-menu with categories), search bar prominent center, Log In / Start Free Trial CTAs right.
- Primary catalog taxonomy has three top-level buckets: **Create**, **Build**, **Thrive** — with subcategories (e.g., Animation, Graphic Design, Photography under Create; Business Analytics, Web Development under Build; Wellness, Lifestyle under Thrive).
- Category pages use a grid of class cards with filter/sort controls (by recency, skill level, etc.).
- "Staff Picks" section surfaces editorially curated classes on browse pages.

**Catalog / Discovery**
- Homepage is personalized after onboarding interest selection — shows a scrollable vertical feed of horizontal carousels (one per topic area or recommended cluster).
- Class cards in the catalog grid show: thumbnail image (wide 16:9), class title, instructor name + avatar, star rating, student count, skill level indicator (beginner/intermediate/expert), and duration. Tags are visible on hover.
- No public free preview of courses — subscription wall before content.
- Search is prominent; results are filterable by category, skill level, and recency (e.g., "Last 6 months" filter).
- Learning Paths: curated sequences of multiple short classes that build on each other — a newer discovery surface within the platform.

**Lesson Player**
- Desktop: two-column split layout. **Left column: video player** (large, full-width of that column). **Right sidebar: scrollable lesson list** with lesson titles and durations — functions as the table of contents. Users can jump between lessons directly from the sidebar.
- Player controls include: play/pause, 15-second skip back, playback speed (0.5×, 1×, 1.25×, 1.5×, 2×), closed captions (multi-language), note-taking, offline download toggle.
- **Below the player**: tabbed sections organizing class content — tabs are: **About**, **Reviews**, **Projects & Resources**, **Discussion**, **Transcripts**.
- **About**: course summary, outcomes, instructor bio.
- **Reviews**: aggregated star ratings + written student feedback.
- **Projects & Resources**: project brief, downloadable files, resource links.
- **Discussion**: single unified thread (not per-lesson); students and instructors can post, reply, and ask questions. Instructors can pin posts.
- **Transcripts**: full text of the lesson for accessibility and scanning.
- Mobile app: vertically stacked (video top, lesson list below, tabs follow); offline download available only on mobile.

**Progress & "Gamification"**
- Progress is tracked via lesson completion toggles; users can see how many lessons remain.
- Profile page shows "My Classes" with completion state and saved/bookmarked classes.
- Certificate badges are listed as a Premium feature (completion certificates), but they are lightweight — not skill-verified credentials.
- No weekly XP leagues, streaks, or leaderboards. The engagement model is project-based and community-driven rather than gamified point systems.
- Community Groups exist (categorized by Creative, Technology, Business, Lifestyle) for peer connection outside individual class threads.

**Onboarding (iOS — 18-screen flow)**
1. Splash / brand screen
2. Get Started CTA
3. Notification permission prompt (appears twice, pre and post signup)
4. Homepage preview (show value before wall)
5. Request access / signup gate
6. Email entry → password → CAPTCHA
7. Plan selection / upgrade screen (paywall introduced post-signup completion)
8. My Classes landing (post-payment)
9. Profile setup

Key pattern: Skillshare shows some homepage content before asking for credentials, defers the paywall to after the signup form is complete. Interest selection (which topics you care about) happens to personalize the homepage — this occurs during or immediately after account creation.

**Pricing / Subscription UI**
- Single plan displayed prominently on web (annual). Monthly option is de-emphasized or absent on desktop; mobile app stores show aggressive promotional pricing ($59.99/year).
- Free trial CTA appears throughout (hero, class pages, mid-page).
- No individual class purchase option — it's all-or-nothing subscription.
- Students with .edu email get 50% discount.
- Payment methods: all major cards, PayPal, Apple Pay, Google Pay.

---

### Concrete UI Details

**Information density:** Low-to-medium. Skillshare trends toward generous whitespace, large class thumbnails, and minimal text per card. The catalog is image-led. Lesson listing sidebar is compact (title + duration per item) but readable. Not information-dense in the way a SaaS dashboard would be.

**Color:** The 2020 rebrand (which is still in use) uses:
- **"Wander Green"** — a bright, distinctive lime-adjacent green as the primary brand color (inspired by traffic light "go"). Exact production hex varies by source: community-cited values cluster around a vivid spring green (#00FF84 or similar bright green) for the logotype, with the UI surfaces using a more muted teal-green. Logo color palette listed on brand resources: **Moonstone Blue / Pastel Teal (#6AB9BE)** and **Vivid Tangelo (#F16C24)** as logo accent pair, with a deep **Persian Blue (#3722D3)** appearing in some brand contexts.
- In product UI, the dominant palette is white/off-white backgrounds, near-black text, the brand teal/green for primary interactive elements (buttons, links, active states), and orange/tangelo for accent highlights.
- No native dark mode (as of 2025, dark mode requires third-party extensions).

**Typography:** The wordmark uses a custom unicase geometric sans-serif (mixed upper/lowercase with slightly altered letterforms to express individuality). Product UI uses clean geometric sans-serif (no serif anywhere). Body text is functional and readable, not expressive. Large class titles on cards use semi-bold weight. The typographic hierarchy is functional rather than typographically expressive.

**Motion:** Not prominently reported. UI transitions appear subtle and conventional (hover states on cards, tab switching). No heavy animation culture. The "squiggly line" motif in branding (representing winding creative journeys) appears in marketing/illustration contexts but is not an in-product interaction pattern.

**Cards:** Class cards are image-dominant (thumbnail takes majority of card area). Below the image: instructor avatar + name, class title (2-line clamp), star rating + student count small/muted, duration. Tags or skill level shown on hover or in a small chip below. Card grid uses even columns (typically 4-across on desktop, 2 on tablet). Hover likely reveals a play button or "quick view" affordance.

**Key screens:**
- Homepage (personalized carousel feed)
- Browse / category grid (filtered card grid)
- Class detail page (hero thumbnail, metadata, instructor card, tab sections)
- Lesson player (split: video left, sidebar right, tabs below)
- Profile / "My Classes" dashboard
- Student Projects gallery (grid of submitted work images with like/comment)
- Community Groups directory

---

### What Skillshare Does Exceptionally Well

1. **Project-based framing from day one.** Every class has an explicit "Class Project" — a concrete deliverable students are expected to create and share. This turns passive watching into active making. The Projects & Resources tab surfaces the brief prominently alongside the video. This is baked into instructor requirements, not optional.

2. **Community project gallery as social proof + motivation.** Student project submissions are visible to everyone — a scrollable gallery below the class. This creates ambient social motivation: you see real work from real people at your level, not just the instructor's polished examples. Projects can be liked and commented on.

3. **Subscription simplicity.** One plan, one CTA everywhere, no cognitive overhead of comparing tiers or buying individual courses. Lower-friction than Udemy's a-la-carte confusion.

4. **Short class format.** Most classes are 20–60 minutes total (average ~30 min). This matches modern attention spans and makes it easy to complete a class in one or two sittings. Progress feels achievable.

5. **Creative-niche clarity.** The Create/Build/Thrive taxonomy and heavy creative category depth means discovery is less overwhelming than general platforms. If you're a creative, you feel at home fast.

6. **In-player note-taking.** Integrated notes inside the player (not a separate app) — reduces context-switching during learning.

7. **Instructor presence model.** Instructors pin posts in Discussion, participate in feedback on student projects, and the platform's social layer (following instructors, seeing their new classes) keeps learners coming back.

---

### Takeaways for StarCi

StarCi = Next.js App Router + React 19 + HeroUI v3 + Tailwind v4. Accent teal #00a898. Freemium: courses → modules → lessons/content + coding challenges, AI credit co-pilot, gamified weekly leagues/XP/streaks/badges.

**1. Mandate a "Course Project" equivalent for every module.**
Skillshare's single biggest retention lever is the project requirement — it converts watchers into makers. For StarCi, every module (not just lesson) could have a capstone challenge or mini-project: a system design diagram to submit, a code challenge to complete, a written design decision to post. Tie it to XP/badge rewards. Render a gallery of submitted solutions (with opt-in visibility) below the module landing page. This creates the social-proof loop Skillshare has.

**2. Adopt the two-column lesson player layout (video left, curriculum sidebar right).**
The Skillshare split is proven. On StarCi's lesson player, a persistent right sidebar showing the full module lesson list + completion checkmarks (with the current lesson highlighted) gives learners orientation without a navigation round-trip. This replaces or complements the rail-nav pattern you already have — the sidebar is always in view during study, not a separate navigation layer. Match to the "1 progress bar at a time" draft rule: the sidebar shows per-lesson completion dots (not bars), one full-width bar at module header only.

**3. Tab architecture inside a lesson/content page.**
Skillshare's five-tab structure (About, Reviews, Projects & Resources, Discussion, Transcripts) is directly applicable: for StarCi content pages use tabs: **Nội dung** (lesson body), **Thử thách** (coding challenge), **Thảo luận** (community Q&A), **Tài nguyên** (links, files), and optionally **AI Q&A** (askContentAi). This maps to the `TabsCard` block pattern already in the design system — two secondary tab groups on one toolbar bar (content/challenge tabs left, language switcher right).

**4. Interest-selection onboarding → personalized homepage carousels.**
Skillshare's post-signup interest selection that generates a personalized homepage carousel feed is directly applicable to StarCi's discovery. After onboarding, ask 3–5 interest questions (system design, full-stack, DevOps, etc.) and render the homepage as stacked horizontal carousels ("Recommended for you", "Continue learning", "Popular in System Design") rather than a flat all-courses grid. This is a lower-engineering investment than full recommendation ML — manually curated rails per tag combination work well at StarCi's catalog size.

**5. "Staff picks" / editorial curation surface.**
Add a "Được chọn bởi giảng viên" or "Nổi bật tuần này" strip on the browse page — a small horizontally scrollable row of 4–5 cards editorially selected. This breaks the algorithmic-only feel and adds trust/curation signal, especially while StarCi's catalog is still growing and personalization data is thin.

**6. Single subscription clarity.**
Skillshare's one-plan simplicity is instructive. StarCi's freemium model is inherently more complex (free tier + premium + AI credits), but the upgrade CTA should always be singular and contextual — not a pricing table comparison. When a user hits a locked lesson, a single in-context card says "Nâng cấp Premium — truy cập toàn bộ nội dung" with one button, not a modal with 3 tiers. Keep tier comparison on a dedicated /pricing page.

**7. Timestamp-linked Discussion.**
Skillshare allows commenting on specific timestamps. For StarCi's video/content lessons, a discussion thread where a question is linked to a specific scroll position or lesson section (not just the whole lesson) dramatically improves the quality of peer Q&A and reduces duplicate questions. This is especially powerful for coding challenge explanations: "Tại dòng 42, tại sao dùng O(n log n) ở đây?" threads directly on the code block.

**8. Short class format discipline.**
Skillshare's 30-minute average is a content authoring discipline, not a platform constraint. StarCi should similarly cap individual lesson content length (target 15–25 min read/watch) and make this visible on the card ("~18 phút"). This reduces intimidation and increases completion rates — which feeds the streak/XP engine StarCi already has.

**9. Student project gallery as social proof on course landing pages.**
Below each StarCi module's landing page, render a public gallery of recent coding challenge submissions or system design diagrams (opt-in). Even 4–6 cards showing real learner work with avatar + username is enough to trigger social motivation. Use HeroUI Card components, image thumbnails for diagrams, code snippets for challenges. Add a "like" count. This costs little to build but drives the community flywheel.

**10. Learning Paths surface.**
Skillshare's Learning Paths (curated multi-class sequences) map directly to StarCi's concept of a course as a module sequence. But consider exposing a "learning path" abstraction that spans multiple courses (e.g., "Backend Engineer Path: FS21 → SD22 → DevOps"). This gives learners a macro goal beyond a single course and increases platform stickiness.

---

### Sources

- [Skillshare – Wikipedia](https://en.wikipedia.org/wiki/Skillshare)
- [Skillshare Pricing – makeheadway.com](https://makeheadway.com/blog/skillshare-cost/)
- [Skillshare Pricing – myelearningworld.com](https://myelearningworld.com/skillshare-pricing/)
- [Skillshare Review (Influencer Marketing Hub)](https://influencermarketinghub.com/skillshare/)
- [Skillshare Review – upskillwise.com](https://upskillwise.com/reviews/skillshare/)
- [Skillshare Review – legitcoursereviewers.com](https://legitcoursereviewers.com/skillshare-review/)
- [Skillshare Review – kristian-larsen.com](https://www.kristian-larsen.com/reviews/skillshare-review/)
- [How Does Skillshare Work – seturon.io](https://seturon.io/blog/how-does-skillshare-work)
- [Skillshare iOS Onboarding Flow – Page Flows](https://pageflows.com/post/ios/onboarding/skillshare/)
- [Skillshare Brand Colors – brandpalettes.com](https://brandpalettes.com/skillshare-logo-colors/)
- [Skillshare Logo Colors – schemecolor.com](https://www.schemecolor.com/skillshare-logo-colors.php)
- [Skillshare New Brand Identity – DesignTAXI](https://designtaxi.com/news/408074/Skillshare-Reveals-Bright-New-Brand-Identity-To-Visualize-The-Creative-Journey/)
- [Skillshare New Logo – Brand New / UnderConsideration](https://www.underconsideration.com/brandnew/archives/new_logo_for_skillshare.php)
- [Skillshare UX Redesign Case Study – pritpalbrar.com](https://www.pritpalbrar.com/skillshare)
- [Skillshare App Redesign Dark Mode – Dribbble](https://dribbble.com/shots/14330104-Skillshare-App-Redesign-Dark-Mode)
- [Build a Website Like Skillshare – DevTechnosys](https://devtechnosys.com/insights/build-a-website-like-skillshare/)
- [Skillshare For Teams Features – Skillshare Help Center](https://help.skillshare.com/hc/en-us/articles/360026470711-What-features-benefits-are-included-in-Skillshare-For-Teams-plans-)
