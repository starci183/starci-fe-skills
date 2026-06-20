## Course Catalog & Discovery

---

### Dominant Patterns

**1. Search-first homepage hero**
Every major platform puts a full-width search bar at the top of the homepage or catalog page. Udemy, Coursera, and edX all open with a hero-search covering at least 60–70% viewport width on desktop, with placeholder text anchoring expectations ("Search for anything", "What do you want to learn?"). The search bar is the primary entry point; browsing is secondary.

**2. Horizontal category tabs / mega-nav**
Top-level categories live in a persistent horizontal nav bar (Udemy: dark bar beneath the logo; Coursera: "Browse" dropdown → mega-panel with subject columns; Khan Academy: horizontal subject tabs). Hovering or clicking reveals a mega-panel with 2–4 columns of subcategories — no more than 2 levels deep. Subcategories resolve to a filtered results grid, never another mega-panel.

**3. Left-sidebar faceted filters on results pages**
All major platforms (Coursera, Udemy, edX, Skillshare) use a fixed-width left sidebar (~240–280px) with checkbox filter groups: **Level** (Beginner/Intermediate/Advanced), **Duration**, **Rating** (4.5+, 4.0+), **Language**, **Price/Free**, **Type** (course/path/certificate). Active filters show as removable chips above the results grid. On mobile, filters move behind a sheet or bottom drawer triggered by a "Filter" button.

**4. Grid-first results with responsive density**
Results render in a CSS grid: 4 columns desktop → 3 tablet → 2 → 1 mobile. Coursera and edX use wider cards (~280px min) at lower density (3 col); Udemy goes denser (4 col) with smaller thumbnails. Skillshare uses a masonry-adjacent feel with portrait-oriented thumbnails (creative platform aesthetic). Khan Academy uses a larger card at lower density because the subject tiles include mastery progress bars.

**5. Course card anatomy (converged across all platforms)**
Every platform has landed on roughly the same card structure:
- **Thumbnail** (16:9 ratio) — always top, full card width
- **Title** — 2-line clamp, `font-weight: 600`, 14–16px
- **Instructor / Provider** — muted, 12–13px, 1 line
- **Rating row** — star icon + numeric rating (e.g. "4.7") + review count in parens — Udemy shows this in amber/gold; Coursera uses teal
- **Meta row** — duration or lesson count or student count (only 1–2 items, never all three)
- **Price / Free badge** — bottom or overlaid on thumbnail corner
- **Level / Type badge** — pill or small text beneath title

**6. Hover-to-expand card (Udemy pattern)**
On desktop, hovering a course card for ~300ms triggers a popover expanding to ~340px wide, showing the full title, 3–4 bullet "What you'll learn" points, last-updated date, level, and an "Add to cart" / "Enroll free" button. The popover appears left or right depending on proximity to viewport edge. This is the most copied pattern from Udemy — edX does a lighter version with hover-triggered course preview info.

**7. Horizontal recommendation rails**
Homepage and post-enrollment pages feature horizontally scrollable rails ("Because you viewed X", "Popular in Web Development", "New this week"). Each rail has a header label, an optional "See all" link, and 4–6 cards visible. Arrow chevrons appear on hover for desktop scroll. Coursera personalizes these rails post-login using a career quiz + ML signals. Rail labels shift from generic ("Popular") to personalized ("Recommended for you") after enrollment.

**8. Course About page — long-form landing page**
All platforms treat the course detail page as a conversion landing page:
- **Hero section**: title, subtitle, rating + enrollment count, instructor name, last-updated, badges (Bestseller, New, etc.)
- **Sticky right sidebar** (desktop): price, CTA button ("Enroll" / "Buy Now"), key stats (hours, articles, certificate). On mobile this becomes a sticky bottom bar.
- **"What you'll learn"** checklist section — 6–8 bullet points in a 2-col grid
- **Curriculum accordion** — sections → lessons, collapsible, shows duration per item
- **Instructor bio** — photo, credentials, rating/students/course count
- **Student reviews** — aggregate stars + histogram + top reviews (sorted by helpful/recent)
- **Related courses** rail at bottom

---

### Concrete Examples Per Platform

**Coursera**
- Catalog at `coursera.org/browse` uses a left sidebar of subject categories (not filters), clicking one loads a results page with left-sidebar facet filters.
- Course cards show provider logo (Google, Stanford, etc.) prominently above the title — trust signal that differentiates from Udemy. Rating shown as yellow stars + number + "(reviews)" in gray.
- Post-login homepage: 5–6 horizontal rails, first rail is "Pick up where you left off" (in-progress courses), then personalized, then role-based. Each rail title is left-aligned, h3-weight, with a right-aligned "Show all" link.
- In 2025 Coursera added a "Compass" onboarding flow: a 3-step career quiz (current role → desired role → time commitment) that populates the first homepage visit with role-based recommendations instead of generic popular courses.
- Course about page: wide left content column (~60%) + sticky right sidebar (~35%); sidebar becomes a bottom sticky bar on mobile.

**Udemy**
- Homepage category bar: 14 top-level categories in a horizontal scrolling nav (dark background, white text). Hover triggers a mega-panel showing subcategories.
- Search results: left sidebar 280px with 6 filter groups; results in 4-col grid on 1440px desktop. Sort bar above grid (Relevance / Most Reviewed / Highest Rated / Newest).
- Course card: 16:9 thumbnail + title (2-line clamp) + instructor name (muted) + rating (amber stars, bold) + review count + duration + price. On hover: popover with bullet "what you'll learn" list + "Add to wishlist" heart + "Add to cart" button.
- "Bestseller" badge: orange pill on card thumbnail top-left corner — one of the most recognized trust signals in online learning.
- Course page: hero banner is full-width with dark overlay (brand purple/dark), white text. Sticky sidebar appears after scrolling past hero.

**Khan Academy**
- No "catalog" in the commercial sense — subject selection is the entry point. Homepage after login shows a vertical left sidebar of subjects (Math, Science, Computing, etc.) with colored icons, main content area shows current course units.
- Course/unit page (2025 update): a mastery progress bar per unit using a 4-state color system (Not started → Attempted → Familiar → Mastered) in a grid of skill tiles. Progress visualization replaced the old list view — tiles are color-coded squares in a section grid.
- Zero commercial patterns: no price, no CTA, no "bestseller" — the entire UI is about learner progress, not conversion.
- Color language: each subject gets a unique accent color (Math = teal, Science = green, Computing = purple) carried through icons, progress bars, and unit headers.

**Duolingo**
- No catalog in the traditional sense post-onboarding. The "home" is a single linear path (the Path, post-2022 redesign) — a vertical scrollable scroll of lesson nodes on a winding road.
- Course selection (language picker): appears only at onboarding or settings. Language cards are simple flag + language name in a flat grid — no metadata, no ratings.
- Gamification UI: persistent top bar showing flame/streak count, XP gems, hearts (lives). Below path: "Daily Goals" ring, league position chip.
- Leagues: dedicated tab — weekly leaderboard of ~30 users in a scrollable ranked list with XP totals, promotion/demotion zone markers (green/red band at top/bottom).
- Achievement section (2023 redesign): two panels — Personal Records (individual bests shown as stats) and Awards (badge grid with locked/unlocked state).

**Brilliant**
- Catalog on web: horizontal category tabs (Math, Data, CS, Science) at top; below is a grid of course cards using a distinctive dark-card-on-dark-bg aesthetic (very different from Coursera's white).
- Course cards are portrait-oriented (3:4 approx), with the course topic rendered as a large abstract illustration — no thumbnail, the card IS the illustration. Title at bottom, difficulty dot indicator.
- Learning path page: branching tree visualization — nodes for lessons/challenges connected by lines showing prerequisites. Current position highlighted. Users can see multiple valid paths to a goal.
- Lesson tiles within a course: numbered squares in a horizontal strip at the top of the lesson player, like a progress indicator/navigator combined.

**Codecademy**
- Catalog at `codecademy.com/catalog`: top-level subjects as horizontal pill filters (All / Web Development / Data Science / AI / etc.), then a grid of cards.
- Three card types are visually distinct: **Course** (shorter, single topic), **Skill Path** (medium, curated sequence), **Career Path** (tall/featured card, full role preparation). Paths show estimated hours and a "Pro" lock badge if paywalled.
- Interface mirrors IDE aesthetics: dark sidebar, monospace font accents, tab-style navigation inside lesson content — signals "this is for developers" without saying so.
- Catalog card: flat, no thumbnail photo — uses colored icon/illustration on solid color background (each language/topic has a color). More compact than Udemy cards.

**edX**
- Category navigation: top-level "Subjects" dropdown → list of ~20 subjects → subject page shows programs + courses in a grid.
- Hover-triggered course previews: hovering a card for ~500ms shows a tooltip-panel with course outline, institution logo, and "View on edX" link.
- Strong institutional branding on cards: university logo appears above course title — e.g., MIT, Harvard, Berkeley. The logo is the primary trust signal.
- Boot Camp / MicroMasters / Professional Certificate are visually differentiated by a colored type badge on the card.

**Skillshare**
- Browsing is category-first via a horizontal color-coded category bar at top (Design, Illustration, Photography, etc. — each with a distinct hue).
- Cards use a portrait thumbnail (teacher doing the craft or a work-in-progress) — creative energy, not a corporate stock photo.
- Below the thumbnail: class title, teacher name, and a simple "X lessons" count. No price shown (subscription model — everything appears "included").
- No filter sidebar: instead, subcategory pills appear below the search bar to narrow within a category.
- "Staff Picks" and "Trending Now" are prominent label types on rails — editorial curation is a Skillshare differentiator.

---

### DO / DON'T Heuristics

**DO**

- Put search first. The search bar must be the largest, most prominent element on browse/catalog pages. Empty state should show popular/trending searches.
- Use a 16:9 thumbnail for every course card and enforce it consistently. Visual inconsistency (mixed ratios) reads as unpolished.
- Show exactly 3–4 pieces of metadata on a card, never more: title + instructor + rating + one more (duration or student count). Use muted text for secondary items.
- Lock the card CTA to the hover/focus state or the detail page. Cards in a grid should not all have visible "Enroll" buttons — it creates visual noise.
- Make filters sticky on scroll (left sidebar). Users apply filters and then scroll results — if the sidebar scrolls away they abandon filtering.
- Use horizontal rails for recommendations on the homepage. Horizontal = browsable/explorable, vertical = authoritative/ranked.
- Show a count + remove chip for active filters above the grid. Users need to know what's filtered and be able to clear one at a time.
- On course about pages, use a sticky right sidebar (desktop) with the price + primary CTA. Convert the sidebar to a sticky bottom bar on mobile.
- Treat the "What you'll learn" section as a first-class section near the top of the course page, before the curriculum — it answers the user's primary question.
- Show social proof early: enrollment count, rating, and a few review excerpts above the fold or in the sticky sidebar.
- Encode content hierarchy visually: Courses vs. Paths vs. Certificates need distinct visual treatments (different card heights, badges, or background colors).
- Use progress persistence signals prominently: "Continue where you left off" rail should always appear first for returning logged-in users.

**DON'T**

- Don't put more than 2 levels of category hierarchy in navigation. Users get lost past subcategory → sub-subcategory.
- Don't use masonry/variable-height card grids for a catalog. They look creative (Skillshare works because it is a creative platform) but make comparison-scanning harder. Uniform grid is correct for educational catalogs.
- Don't mix thumbnail aspect ratios across cards in the same grid — even one landscape card among portrait cards breaks visual rhythm instantly.
- Don't show pricing on every card if the platform is subscription-based — it creates "is this included?" anxiety. Show "Included with Pro" or a lock icon instead of a price.
- Don't put a horizontal scroll rail below the fold on mobile without clear affordance (arrow / "drag to explore"). Most users won't discover it.
- Don't use more than 3 filter groups open by default in the sidebar. Collapsed groups reduce cognitive load; let users expand what's relevant.
- Don't use gray placeholder text in search as the only hint. Add a few trending-topic chips below the search bar so users see what's searchable even if they type nothing.
- Don't design course cards without a defined hover/focus state — keyboard and mouse users both need feedback that the card is interactive.
- Don't rely on color alone to differentiate content types (accessibility violation). Use icon + color + label.
- Don't make the course about page a wall of text. Scannable sections with clear h2 headings, bullet lists, and accordions are the norm for a reason.
- Don't show the full curriculum expanded by default — default to showing 2–3 sections expanded, the rest collapsed, with a "Show all sections" button.
- Don't omit a "last updated" date on course cards or the about page. Users trust recency signals, especially in tech.

---

### Takeaways for StarCi

**Catalog & Homepage**
- Homepage hero: full-width search bar with 3–4 trending topic chips below it ("System Design", "Full-Stack", "DevOps", etc.). Below the search: a horizontal category tab strip (the 5–7 top subjects StarCi offers). This replaces a generic hero banner — it puts users directly into browse mode.
- Use horizontal rails built from real data signals: "New this week", "Popular with learners like you" (post-onboarding quiz), "Continue learning" (returning users only), "Trending: weekly league members are studying...". Each rail = 4–6 course cards, horizontally scrollable, with a "See all" link.
- Post-login first rail must be "Pick up where you left off" (in-progress course/module/lesson). This is the single highest-value personalization signal and all major platforms agree on it.

**Course Cards**
- Card anatomy: 16:9 thumbnail (rendered from course `thumbnailUrl` field) + title (2-line clamp, `text-base font-semibold`) + instructor name (muted, 12px) + rating stars (teal accent, matching #00a898) + one meta pill (e.g. "12 lessons" or "Intermediate"). For freemium: show a lock icon on the thumbnail corner for premium-gated courses, not a price — reduces subscription anxiety.
- Add a "Continue" badge (teal border + "X% complete" text) on cards for in-progress courses — this state is visually distinct from non-started and completed.
- Hover state: subtle shadow lift + reveal a "Start" / "Continue" button at card bottom. No full popover needed for a tighter catalog — StarCi's course count doesn't justify Udemy-scale hover previews.
- Badge vocabulary: "New" (accent), "Popular" (amber), "Free" (success green), "Premium" (lock icon, not price). Keep to 1 badge per card max.

**Browse & Filters**
- Left sidebar filters on results/catalog page: Level (Beginner/Intermediate/Advanced), Duration, Topic/Tag, Free vs Premium. Keep 4 groups max, all collapsed by default except Level.
- Active filter chips above the grid with individual X removal + "Clear all".
- Sort bar above grid: Relevance / Most Popular / Newest / Highest Rated.
- On mobile: sheet drawer triggered by "Filters (N)" button — N = count of active filters.

**Category Navigation**
- Top-level: horizontal tab strip with 5–7 subjects (System Design, Full-Stack, DevOps, AI/ML, Data, Security, Soft Skills). Use HeroUI Tabs in underline style.
- No mega-menu needed at StarCi's scale. A category page shows a subcategory pill-filter row below the tab strip, then the grid. This avoids 2-level mega-panel complexity.

**Course About Page**
- Two-column layout (desktop): left 60% = content (hero description, what-you-learn grid, curriculum accordion, instructor bio, reviews); right 35% = sticky sidebar (thumbnail preview/video, enrollment CTA, key stats: lessons, challenges, XP earned, AI credits included, certificate).
- Mobile: sidebar content moves to a sticky bottom bar — "Enroll / Continue" button + price. Sidebar stats collapse to a horizontal scroll strip.
- What-you-learn section: 2-col bullet grid, max 8 points, positioned immediately after the description — before curriculum. This is the highest-read section.
- Curriculum accordion: show module → lessons list. Each lesson row: icon (video/challenge/quiz) + title + duration. Default: first module expanded, rest collapsed.
- Gamification context on about page: show XP you'll earn (e.g. "+850 XP"), badge you unlock, and how it affects your league rank. This is a StarCi differentiator none of the major platforms leverage.
- Social proof: average rating (large number, teal stars), enrollment count, and 3 featured reviews with avatar + star + text excerpt. Place near top of left column.

**Discovery / Recommendations**
- On onboarding (first login after signup), run a 3-step quiz: role/background → goal → weekly time. Populate first homepage visit from this quiz, not generic "popular" content — Coursera's Compass feature proves this significantly improves enrollment.
- Use XP/league data for discovery: "What high-league players are learning this week" rail can surface aspirational content organically and ties discovery to StarCi's gamification layer.
- "AI co-pilot recommended" rail: surface 3–4 courses the AI co-pilot's usage patterns suggest (e.g., if many users ask AI about caching in System Design → surface the caching module). Label clearly as AI-suggested.
- Related courses at bottom of course about page: 4 cards in a horizontal rail, filtered to same subject/tag.

**Visual / Motion**
- Teal `#00a898` is reserved for primary CTAs, active states, star/rating color, and progress fills — not decorative. Consistent with the accent discipline in StarCi's design system.
- Card hover: `box-shadow` lift + `translateY(-2px)` transition ~150ms ease-out. No color background change on card hover — avoids competing with the thumbnail.
- Rail scroll arrows: appear only on `group-hover`, fade-in with opacity transition. Do not persist — they add visual weight when not needed.
- Progress bars on cards: thin (4px height), teal fill. Do not add per-module progress bars inside catalog cards — only on the in-progress card state (per the one-progress-bar-at-a-time rule already in your draft rules).
- Dark mode: card backgrounds → `bg-content1` (HeroUI token), thumbnail border-radius consistent (8px). Muted text → `text-default-500`.

---

### Sources

- [Transforming the Search Experience: A UX Design Journey with Coursera (Medium)](https://medium.com/@ahujaashmita15/transforming-the-search-experience-a-ux-design-journey-with-coursera-487c12807778)
- [Coursera Online Course Catalog by Topic and Skill](https://www.coursera.org/browse)
- [Introducing New Tools and Features as Demand for Online Learning Grows — Coursera Blog](https://blog.coursera.org/introducing-new-platform-innovations-as-demand-for-online-learning-grows/)
- [Improving Udemy's Search — UX Challenge (Medium)](https://medium.com/@henryrae/improving-udemys-search-ux-challenge-97725163c4fb)
- [How to Filter Udemy Courses by Language, Rating, and Level — Demosmith](https://demosmith.ai/demos/udemy)
- [Brilliant.org x ustwo — Case Study](https://ustwo.com/work/brilliant/)
- [Brilliant: Learn Math & Coding UI Breakdown — ScreensDesign](https://screensdesign.com/showcase/brilliant-learn-by-doing)
- [Duolingo Gamification Strategy: A Full Case Study — Trophy](https://trophy.so/blog/duolingo-gamification-case-study)
- [The Duolingo Design Method — Designlab](https://designlab.com/blog/the-brief-08-08-25)
- [Codecademy Catalog Home](https://www.codecademy.com/catalog)
- [UI Change That Duolingo Users Are Asking For In 2025 — DuolingoGuides](https://duolingoguides.com/ui-change-that-duolingo-users-want/)
- [10 Best Educational Website Design Examples — DevsData](https://devsdata.com/best-educational-website-design-examples/)
- [Best Practices for Designing UI Cards — UX Design World](https://uxdworld.com/designing-ui-cards/)
- [UI & UX Design Trends for E-Learning: Best Practices — FRAM Creative](https://framcreative.com/insights/latest-trends-best-practices-and-top-experiences-in-ui-ux-design-for-e-learning)
- [Top 10 Course Platform Designs for 2025 — Stylokit](https://stylokit.com/blog/top-10-course-platform-designs-for-2025)
- [Duolingo's Gamified Growth — The Product Brief (Medium)](https://medium.com/@productbrief/duolingos-gamified-growth-how-a-green-owl-turned-language-learning-into-a-14-billion-habit-d47d9fa30a77)
- [Khan Academy — New mastery progress visualization on Course and Unit pages](https://support.khanacademy.org/hc/en-us/articles/18735142028045-Update-New-mastery-progress-visualization-on-Course-and-Unit-pages)
- [Khan Academy Wikipedia](https://en.wikipedia.org/wiki/Khan_Academy)
- [Mega Menu Design Examples: 15 Navigation Patterns — Banana Produced Designs](https://www.bananaproduced.com/mega-menu-design-examples-15-navigation-patterns-that-improve-ux/)
- [UX Navigation Design: Common Patterns and Best Practices — Eleken](https://www.eleken.co/blog-posts/ux-navigation-design)
