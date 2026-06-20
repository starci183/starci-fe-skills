## edX

### What & Who

edX (now owned by 2U, Inc. since a 2021 $800M acquisition from Harvard and MIT) is a premium-tier MOOC platform targeting adult professionals and degree-seeking learners globally. Positioning: institutional credibility first — every course is fronted by a partner logo (Harvard, MIT, Google, IBM, etc.), and the product hierarchy runs Free Audit → Verified Certificate ($50–300) → Professional Certificate → MicroMasters/XSeries Program → Online Degree (up to tens of thousands). There is no subscription. As of 2025 it claims 100M global learners, 230+ university partners including 19 of the top-20 ranked globally, and ~3,500 learning opportunities. Audience: career-changers and corporate upskilling (also sells B2B via "edX For Business" / Online Campus enterprise subscriptions). The platform carries a promotional banner year-round (currently "Save 15% with code CURVE2026 until June 30") — promotional cadence is aggressive.

---

### Signature UX/UI Patterns

**Global Navigation**
- Minimal top bar: edX logo (left), two nav links ("Learn" / "edX For Business"), promotional banner spanning full width, and a "Register for free" / account avatar (right).
- No mega-menu visible on landing; discovery is pushed into the body/catalog pages.
- Sticky header on scroll (standard pattern).

**Catalog / Discovery**
- Subject landing pages (e.g. `/learn/python`) follow a consistent template: full-width hero with headline + short descriptor copy → key stats bullet-list → course/certificate count badges ("22 Certificates," "26 Courses," "Executive Education (3)") → course cards grid → long-form SEO content (What is X, Why Learn X, Career Paths with salary data) → social proof (testimonials with photos + location) → mega-footer.
- The main `/search` page uses **subject filter tiles** (large image tiles for Data Science, Computer Science, Business, etc.) rather than a traditional left-sidebar faceted filter. Filters available: Subject, Partner, Program type, Level, Language, Availability, Learning Type.
- Program-type cards appear below: Masters, MicroMasters, MicroBachelors, Professional Certificates, XSeries — each with thumbnail, name, and 2-line description + 3 attribute chips (e.g. "Graduate-level · Master's Degree · Affordable & flexible").
- Hover-triggered course previews allow learners to evaluate relevance before committing (described as "course preview" interaction).
- No infinite scroll confirmed; structure is organized into "Most popular," "Executive Education," "New" sections with "Show More" affordances.

**Course-About / Detail Page**
- Hero: institution logo + course title + short description + instructor name. Promotional banner persists.
- Enrollment CTA: primary button leads to the **paid verified track** by default. A smaller, visually de-emphasized "Audit this course" link gives access to the free path — this hierarchy is intentional to drive upgrade conversion. Verified certificate price shown prominently near CTA.
- Sticky sidebar (or sticky top panel on mobile) holds the price, duration, effort estimate, and the primary Enroll CTA — it follows the learner as they scroll the course description.
- Body sections (in order): What you'll learn → Syllabus (week-by-week breakdown) → Instructor cards (photo, title, institution, social links) → Partner info (institution logo, about) → Learner testimonials (~2 per course) → Requirements/Prerequisites.
- Program pages (MicroMasters): list courses in the sequence with individual course cards, show total program duration + effort, certificate credential type, and a single enrollment CTA.

**Enrollment Flow**
- Click Enroll → modal or redirect to a track-selection screen: two options shown — "Upgrade Now" (paid, verified, certificate) vs "Continue" / "Audit this course" (free, no certificate). If the learner picks "Continue" they can still upgrade later before the upgrade deadline.
- Audit enrollment is instant — no payment info required; lands directly on course dashboard.
- Verified track: payment page → ID verification via webcam + government ID → course access.

**Lesson / Content Player (post-2024 redesign)**
- Old layout: left sidebar (section/subsection tree) + sequence bar across top. Content area was constrained by the sidebar.
- New layout (rolled out in two phases): dedicated **Course Outline Page** (full-width, shows entire course structure, visual progress indicators, last-accessed resumption point, certificate upgrade prompt) is the landing for a course. Learner clicks into content → **sidebar is removed**, content area widens to "immersive" full-width. Breadcrumb above the content (not a sidebar) links back to the outline.
- Sequence bar still exists across the top of content pages; redesigned with cleaner icons, updated colors, Previous/Next buttons now show adjacent unit names.
- Unit page title is displayed to help learners know their position.
- Video player: HLS adaptive streaming, standard controls + playback bar + time display. Transcript and speed controls included.
- Green check marks indicate completed units in both the course outline and the sequence bar.
- Bookmarking tied to unit title area.

**Learner Dashboard**
- "Courses" tab lists all enrolled courses. Two filter categories: Course Status (In Progress, Not Started, Done, Not Enrolled, Upgraded) and Sort (Last Enrolled, Title A–Z).
- Course cards on dashboard: course thumbnail, organization name, course title, end/expiry date (the key scan-critical field; historically cluttered — a redesign proposal to improve information hierarchy is in-flight as of 2025).
- Programs page lists enrolled programs separately with program completion record.

**Progress / Gamification**
- Green checkmarks on sequence bar and course outline (completion indicators).
- "Progress" page with visual progress tracking.
- Verified certificates with institution logo, instructor signatures, unique URL/ID — shareable credential.
- Skill badges (IBM, etc.) as verifiable digital credentials.
- No XP, streaks, leagues, or leaderboards — edX does not gamify. Progress is purely completion-based and credential-focused.

**Onboarding**
- Registration is a short form (email, name, password). No multi-step interest/goal selection funnel typical of consumer apps. Identity for verified track is collected at payment time (webcam ID check), not at registration.
- Minimal progressive profiling — the platform does not force goal-setting before browsing.

**Pricing Display**
- No subscription. Per-course pricing.
- Verified Certificates: $50–$300 per course (typical $90–$300).
- Professional Certificates (multi-course): variable.
- Executive Education: $400–$700.
- Boot Camps: $1,000–$2,000.
- Online Degrees: tens of thousands.
- Audit: always free, but the word "Audit" is secondary/small on enrollment screens.
- Financial aid available for some programs (not boot camps or executive ed).
- Year-round promotional discount codes shown in a sitewide banner.

---

### Concrete UI Details

**Information Density**
Moderate-to-high on catalog pages (lots of SEO copy, stats, and testimonials below course cards). Course-about pages are long-scroll single-column with distinct sections separated by generous whitespace. The lesson player is intentionally low-density — wide content area, minimal chrome after the 2024 redesign.

**Color**
Brand palette: Autumn Blue (#136CA5) and Battery Charged Blue (#1F9FD9) are the two primary blues. Secondary marks include a Freezy Magenta (#B82669) and Dark Velvet (#77202E). The Paragon design system (Bootstrap-based) uses a light-first semantic token system (gray-100 through -900 scale, semantic success/info/danger/warning states). The overall palette skews institutional blue — authoritative, not playful. No dark mode confirmed for the main marketing site.

**Typography**
Paragon defines a 7-level heading scale (h1–h6 + heading-label), five body text sizes (lead, body, small, x-small, micro), and display-1 through display-4 for hero contexts. Specific font family is not publicly codified in brand guidelines but the platform renders with a clean sans-serif (consistent with Bootstrap/system sans). Type scale is conservative and readable, not editorial.

**Motion**
No notable animation or transition described in documentation. Hover-triggered course previews are the most interactive surface. The overall motion philosophy is restrained — consistent with an academic/institutional brand that avoids "edutainment" aesthetics.

**Course Cards (catalog)**
- Thumbnail image (top)
- Institution logo
- Program type chip (MicroMasters, Professional Cert, etc.)
- Course/program title
- Short descriptor (1–2 lines)
- Attribute chips: level, duration/effort, degree type
- Price (implicit or shown on hover/expansion)

**Course Cards (dashboard)**
- Historically cluttered: organization name, course title, and end date competed for visual weight
- Redesign (in-flight 2025): cleaner hierarchy with separated organization / title / deadline, strategic iconography

**Key Screens**
1. Subject browse page (`/learn/python`) — hero + stats + card grid + SEO content column
2. Search/catalog (`/search`) — tile-based subject filter + program-type cards, minimal left-rail
3. Course-about page — long-scroll, sticky enrollment panel, institution-credentialed header
4. Track-selection modal — Upgrade Now vs Audit (paid prominent, audit de-emphasized)
5. Course outline page (post-2024) — full-width tree view, progress checkmarks, resume CTA
6. Content player (post-2024) — full-width, sidebar-free, breadcrumb top, sequence bar

---

### What it Does Exceptionally Well

1. **Institutional credentialing as the primary value hook.** Partner logos (Harvard, MIT, IBM) are the first thing visible on every card and page. The credential is the product, and the UI is engineered around making that credential feel authoritative and worth paying for.
2. **The audit/paid split as a conversion funnel.** Making audit access real but visually secondary (small link) while making the paid path the big CTA is an elegant freemium-to-paid conversion lever that does not deceive users but consistently nudges them toward upgrade.
3. **Course-outline as a separate orientation surface.** The 2024 redesign separating the outline (navigation) from the content player (focus) reduces cognitive load significantly — the learner orients in one mode, learns in another. This is a mature pedagogical UX decision.
4. **Scale of SEO-optimized subject landing pages.** Each `/learn/<subject>` page is a deep, structured content piece with career data, salary info, and FAQs — this drives acquisition without paid media and positions edX as an authoritative source.
5. **Long-form course-about page.** The syllabus-week-by-week, instructor bios, testimonials, and institution info give learners enough signal to make a confident enrollment decision. Reduces post-enrollment regret.

---

### Takeaways for StarCi

1. **Credentialing as a conversion anchor.** edX wraps every course in the partner institution's reputation. StarCi should similarly wrap every course/lesson in visible outcome signals — not just "what you'll learn" copy but concrete artifacts: the badge you'll earn, the challenge score you'll get, the league rank improvement. These are StarCi's version of a Harvard logo.

2. **Explicit two-path enrollment gate.** edX's "Upgrade Now vs Audit" modal is a high-converting freemium gate. For StarCi, a similar explicit moment — "Continue free (no certificate + no AI credits)" vs "Go Premium (full access + AI co-pilot + league ranking)" — surfaced at the moment of enrolling in a course, would make the value of premium concrete at peak intent rather than buried in a pricing page.

3. **Separate the map from the player.** edX's 2024 course outline / player split is directly applicable. StarCi's content map (module/lesson tree) should be a dedicated orientation view, not a persistent sidebar competing for reading width inside the lesson player. On desktop: outline as a collapsible panel or separate route; in player: breadcrumb only, full-width content. This aligns with the `one-progress-bar-at-a-time` rule already in your design guidelines.

4. **Subject landing pages as SEO + discovery.** edX generates high-intent organic traffic via deep `/learn/<topic>` pages. StarCi could build equivalent course-family landing pages (e.g. `/courses/system-design`, `/courses/fullstack`) with outcome data, curriculum preview, and career path context — not just a filtered course list.

5. **De-emphasize the free path visually, but keep it real.** edX's audit link is genuinely there but small. StarCi's free tier should be fully accessible but the premium CTA should be the primary button size and color (`accent teal #00a898`), with "Continue free" as a ghost/text link below. Don't hide free, but don't treat it as co-equal with premium.

6. **Institution/author authority signals on cards.** edX cards always show the partner logo. StarCi cards should have a clear "instructor" or "by StarCi Academy" badge plus a difficulty/level chip and an estimated time — three fast-scan signals that let a learner evaluate fit without opening the detail page.

7. **Long-form course-about page.** edX invests heavily in the pre-enrollment page. StarCi course pages should include: curriculum accordion (week/module breakdown), what you'll be able to build/solve after, challenge preview, instructor info, and a progress/completion rate stat (social proof). This reduces bounce and increases confident enrollment.

8. **Progress as completion artifacts, not gamification.** edX does not use XP or streaks — it uses certificates and verified credentials. StarCi uses both (badges + XP + streaks). The lesson: credentials and portfolio artifacts (completed challenges, earned badges) carry more long-term motivation weight than points. Lean into the badge economy and make earned badges visually prominent on the dashboard.

9. **Sitewide promotional banner.** edX's persistent promo banner is a low-cost conversion driver. StarCi could use a similar sticky banner for trial promotions, limited-time discounts, or "Week 1 of league — join now" urgency signals.

10. **No subscription but clear per-item pricing.** edX shows price near the enrollment CTA, not buried. StarCi's pricing should be surfaced at the course level (e.g. "This course is in the Premium tier — see plans") rather than only on a separate pricing page, to make the value exchange visible at the decision moment.

---

### Sources

- [edX homepage](https://www.edx.org/) — live fetch, June 2026
- [edX Python courses page](https://www.edx.org/learn/python) — live fetch
- [edX search/catalog page](https://www.edx.org/search) — live fetch
- [Coming Soon: Course Navigation Changes — Open edX](https://openedx.org/blog/coming-soon-course-navigation-changes/)
- [Update: Course Navigation Changes — Open edX](https://openedx.org/announcements/update-course-navigation-changes/)
- [Enhanced Course Card Design proposal — openedx/platform-roadmap #355](https://github.com/openedx/platform-roadmap/issues/355)
- [Catalog Domain MFE conversion proposal — openedx/platform-roadmap #375](https://github.com/openedx/platform-roadmap/issues/375)
- [Sidebar Navigation Release Notes (Redwood)](https://docs.openedx.org/en/latest/community/release_notes/redwood/sidebar_nav.html)
- [edX Audit Track — Help Center](https://edxsupport.zendesk.com/hc/en-us/articles/1500003964681-What-is-the-audit-track)
- [edX Free Courses 2026 Guide — OnlineCertHub](https://onlinecerthub.com/edx-free-courses/)
- [edX Review — UpSkillWise](https://upskillwise.com/reviews/edx/)
- [edX Pricing — MyElearningWorld](https://myelearningworld.com/edx-pricing/)
- [edX brand colors — SchemeColor](https://www.schemecolor.com/edx-logo-colors.php)
- [Paragon Design System — GitHub](https://github.com/openedx/paragon)
- [Paragon Colors documentation](https://paragon-openedx.netlify.app/foundations/colors/)
- [Paragon Typography documentation](https://paragon-openedx.netlify.app/foundations/typography/)
- [edX Wikipedia](https://en.wikipedia.org/wiki/EdX)
- [2U + edX merger completion](https://2u.com/newsroom/2u-inc-and-edx-complete-industry-redefining-combination/)
- [edX dashboard — edX Help Center](https://edxsupport.zendesk.com/hc/en-us/articles/360000340307-What-is-my-dashboard)
- [Best Educational Website Design — DevSData](https://devsdata.com/best-educational-website-design-examples/)
