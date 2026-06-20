# StarCi UX Brainstorm — CONTENT.md

> Heavy reference for the `starci-fe-ux-brainstorm` skill. It does three things:
> 1. **Playbook** — how to run a StarCi UX brainstorm from first principles across the 5 goal lenses.
> 2. **Pattern library** — the course-website UX patterns distilled from `../../refs/`, with which platform
>    does each best, so you can pull the right pattern fast.
> 3. **Design-system mapping** — how to land a chosen pattern on StarCi (HeroUI v3, accent teal `#00a898`,
>    3-tier layout, existing blocks + rule drafts), plus the output artifact shape.
>
> Every pattern below cross-references a `../../refs/<slug>.md` file. Open the ref for the concrete detail; this
> doc is the map. The refs each already contain a "Takeaways for StarCi" section — treat those as a
> *starting point* you pressure-test here, not a conclusion.
>
> Repo layout: this canon lives at `skills/starci-fe-ux-brainstorm/CONTENT.md`; the lean entry is
> `SKILL.md` next to it; references live in `../../refs/<slug>.md`.

---

## 0. The mental model (read this first)

StarCi Academy is a **freemium, gamified, content-first coding/CS learning platform**:

```
Course → Module → Lesson/Content (markdown reader) + Coding Challenge (easy→insane)
        + AI credit co-pilot (askContentAi, unified credit pool, freemium-gated)
        + Gamification: weekly leagues · XP · streaks · badges
        + Profiles · Payments (SePay/PayOS, freemium plans)
Stack: Next.js App Router + React 19 + HeroUI v3 + Tailwind v4 (OKLCH tokens, brand hue teal)
Vibe: content-first, clean, lots of whitespace, accent teal #00a898, light + dark (default dark).
```

The reference universe splits into **two archetypes** — and StarCi sits *between* them:

- **MOOC / credential tier** (Coursera, edX, Udemy, Skillshare, Frontend Masters, freeCodeCamp): trust
  signals, sticky purchase sidebar, certificate-as-artifact, week/module accordion player, minimal-to-no
  gamification. StarCi borrows their **catalog cards, lesson player, trust stacking, certificate moment**.
- **Habit / gamified tier** (Duolingo, Brilliant, Khan Academy, Codecademy): streak + XP + leagues, linear
  path metaphor, deferred signup, friction-as-conversion paywall, in-context everything. StarCi borrows
  their **gamification, onboarding, path metaphor, inline paywall** — this is StarCi's differentiator vs.
  the MOOC tier, so lean in, don't flatten.

**The golden adaptation rule:** StarCi's audience is engaged learners/devs who respond to *both* depth
(MOOC) and motivation mechanics (habit). Pick patterns from whichever tier fits the goal; never copy a
pattern whose *business model* contradicts StarCi's (e.g. Skillshare's single-plan simplicity, Udemy's
fake-urgency flash sales, Coursera's no-gamification dashboard).

---

## 1. How to run a StarCi UX brainstorm (the 5 goal lenses)

A brainstorm always: (a) names the goal lens, (b) inventories what StarCi data/features exist, (c) pulls
2–4 proven patterns from the refs, (d) maps them onto the StarCi design system, (e) produces ≥2–3 directions
→ picks 1, (f) draws a widget mockup if the layout/component is new.

### Lens A — UX-only (flow, IA, states, friction)
Ask: what is the user's *one job* on this screen in ≤30s? What is the single primary action? What are the
empty/loading/error states? Where is the friction? Pull from the cross-cutting refs first
(`lesson-player.md`, `catalog-discovery.md`, `dashboard-mobile.md`, `onboarding.md`) then a platform ref
that nails it. Apply: `one-progress-bar-at-a-time`, `three-tier-page-layout`, content-column cap
`max-w-3xl`, AsyncContent states (see `starci-async` skill).

### Lens B — Marketing (what this screen sells)
Ask: what conversion/retention lever lives here? Trust signals (enrollment count, rating, badge-on-completion,
instructor authority), social proof placement, value-gate clarity (free vs premium chip + lock), the upgrade
CTA. Pull `pricing-paywall.md`, `catalog-discovery.md` (course-about page), `coursera.md` / `edx.md` (trust
architecture), `udemy.md` (social-proof saturation). Apply: inline paywall not redirect, gate
credential/AI-credits not core content, teal `bg-success/10 text-success` for "Save %" / "Free" chips.

### Lens C — Strategic communication (message order + tone)
Ask: who reads this, what's the *primary message*, in what order do messages land, what tone? A course-about
page communicates "this is worth your time + money"; a paywall communicates "here's exactly what you unlock
+ what you'd lose"; an empty state communicates "here's your obvious next step". Pull `onboarding.md`
(progressive disclosure, social proof at friction), `edx.md` / `frontend-masters.md` (serious-dev credibility
tone), `pricing-paywall.md` (personalize paywall headline to the trigger feature). Tone for StarCi: clean,
content-first, confident-not-loud; NO fake urgency, NO guilt-trip gamification.

### Lens D — Component design (one element, deeply)
Ask: what is this component's single responsibility, its states, its variants, its anatomy? Common StarCi
components and their canonical refs:
- **Course card** → `catalog-discovery.md §card anatomy` (the converged anatomy) + `udemy.md` (hover-preview),
  `frontend-masters.md` (sparse card, resist over-stuffing).
- **Paywall modal / upgrade card** → `pricing-paywall.md` (contextual modal, 3-bullet, annual-default toggle).
- **League leaderboard row** → `gamification.md` + `duolingo.md` (promotion/demotion zones, countdown).
- **Streak widget** → `gamification.md` + `duolingo.md` (persistent top-bar, freeze, no-shame tone).
- **Lesson rail / content map** → `lesson-player.md` + `coursera.md`, `khan-academy.md` (accordion, watch-state icons).
- **AI co-pilot panel** → `coursera.md` (floating Coach), `udemy.md`/`codecademy.md` (right-panel tab, in-scope), `khan-academy.md` (Socratic).
- **Completion / badge-earn moment** → `gamification.md` + `brilliant.md`, `duolingo.md` (motion = reward only).
Build it from HeroUI v3 + a StarCi block; never a bare primitive (see `design/02` + cannon).

### Lens E — Page layout (the whole composition)
Ask: which StarCi archetype is closest, how many columns, where's the rail, what's the spacing rhythm? Map to
`design/03-layout-archetypes.md` (Course detail / Course learn / Challenge split) + `three-tier-page-layout`
(breadcrumb → H3 header → content, all `max-w-3xl mx-auto`, `h-3` spacers). Pull `lesson-player.md` (two-column
master layout, content-width cap), `dashboard-mobile.md` (hero "continue" card first, bottom-nav on mobile),
`catalog-discovery.md` (grid density, sticky filter sidebar).

### The brainstorm output discipline (all lenses)
- ≥2–3 directions, each neon to a named ref pattern, each with a one-line trade-off; then CHỐT 1 + why.
- A `section → BE/DB field` table (don't design for data that doesn't exist; flag unused fields as opportunity).
- Empty/loading/error/dark-mode considered from the start.
- Widget mockup (`show_widget`, module `mockup`) for any new layout/component — 1–3 scenarios side by side,
  CSS vars, accent teal, proposed one marked. Then `/ux-apply` builds it (not this skill).

---

## 2. Pattern library (distilled from the refs)

Each entry: the pattern, **who does it best** (→ ref), and the **StarCi adaptation gist**. Open the ref for detail.

### 2.1 Catalog & discovery
*(→ `catalog-discovery.md`, `coursera.md`, `udemy.md`, `skillshare.md`, `codecademy.md`, `edx.md`, `frontend-masters.md`)*

- **Search-first hero + category tab strip** — *Udemy/Coursera/edX*. StarCi: full-width search + 3–4 trending
  topic chips + horizontal subject tab strip (HeroUI Tabs underline), no mega-menu at StarCi scale.
- **Horizontal recommendation rails, "Continue" first** — *Coursera/Udemy/Codecademy*. First rail for logged-in
  users is always **"Pick up where you left off"**. Then "New this week", "Popular", and a StarCi-unique
  **"What high-league players are studying"** (ties discovery to gamification).
- **Converged course-card anatomy** — *everyone* (see `catalog-discovery.md §5`): 16:9 thumbnail (`thumbnailUrl`)
  + title (2-line clamp, `text-base font-semibold`) + instructor/author + rating (teal stars) + ONE meta pill +
  1 badge max. Freemium: **lock/"Premium" badge on thumbnail corner, NOT a price** (reduces subscription anxiety).
- **Hover-preview card** — *Udemy* (best), *edX* (lighter). StarCi: optional; at StarCi scale a subtle
  shadow-lift + reveal "Start/Continue" button is enough (FM-style restraint beats Udemy-scale popover).
- **Sparse cards, resist stuffing** — *Frontend Masters*. Don't pile rating + reviews + tag-cloud on the card;
  push those to the detail page.
- **Left-sidebar faceted filters** — *Coursera/Udemy/edX/Codecademy*. StarCi: Level / Duration / Topic / Free-vs-Premium,
  4 groups max, sticky on scroll, active-filter chips with individual remove. Mobile → sheet drawer with "(N)" count.
- **Course-about = conversion landing page** — *Coursera/Udemy/edX* (sticky purchase sidebar), *edX* (long-form
  SEO + syllabus accordion), *Udemy* (social-proof saturation). StarCi: 2-col, left = description + what-you-learn
  grid + curriculum accordion + reviews; right = **sticky** enroll/plan card (lessons, challenges, **XP you'll
  earn**, **badge you unlock**, AI credits included, certificate). Mobile → sticky bottom bar.
- **Content-type-distinct cards** — *Codecademy* (Course/Skill-Path/Career-Path), *edX* (program-type badge).
  StarCi: distinguish Course vs Learning-Path (cross-course) visually.
- **What NOT to copy:** Skillshare masonry/variable-height grid (use uniform grid for comparison-scanning);
  Udemy perpetual "83% off, ends in Xh" fake-urgency timers; Coursera monotonous logo-on-dark thumbnails.

### 2.2 Lesson player (reading / video / code)
*(→ `lesson-player.md`, `codecademy.md`, `udemy.md`, `coursera.md`, `khan-academy.md`, `skillshare.md`, `brilliant.md`)*

- **Two-column master layout** — *Udemy/Coursera/Skillshare/edX*: content/video left (60–70%), outline rail
  right (30–40%), rail scrolls independently. StarCi reading lesson: content `max-w-3xl mx-auto`, rail right
  on lg+, drawer on mobile.
- **Separate the map from the player** — *edX 2024 redesign* (best). Course outline as an orientation surface,
  player gets breadcrumb-only + full-width content. Directly aligns with StarCi `one-progress-bar-at-a-time`.
- **Accordion outline + watch-state icons + per-item completion** — *Coursera/Udemy*, *Khan Academy*
  (3-state shaded play buttons: done/in-progress/not-started — richer than ✓/○). Controlled accordion
  (`expandedKeys`), auto-expand the active section. StarCi: open group → 1 progress bar; collapsed → "n/m" muted
  (the `one-progress-bar-at-a-time` rule, already a draft).
- **Sticky prev/next — never bottom-only** — *CFI redesign lesson*, *Udemy* (arrows in player chrome). Put
  prev/next in the sticky top bar AND at content bottom. StarCi top bar: `breadcrumb + lesson title (H3,
  truncate+tooltip per rail-long-title rule) + AI co-pilot icon + prev/next chevrons`, ≤60px tall.
- **Transcript as interactive component** — *Coursera* (best: click-to-seek, highlight-to-save-note, PiP video),
  *Khan Academy*, *edX*. For StarCi (text-first) the equivalent is **highlight-to-save annotations + a Notes tab**.
- **Three-pane code editor** — *Codecademy* (instructions / editor / output), *freeCodeCamp* (test-as-spec),
  *LeetCode* (split view). StarCi coding challenge: left = instructions + AI hint toggle, center = editor
  (dark-by-default regardless of page theme), right = test output + submit; draggable gutters; nav in the
  persistent top bar, not the editor zone.
- **Step-count as the only in-lesson progress cue** — *freeCodeCamp* ("Step 12 of 69", 2-min steps),
  *Duolingo* (single challenge per screen, full-width, minimal chrome). For StarCi challenge steps, a counter
  not a bar.
- **Tab architecture beneath/around content** — *Skillshare* (About/Reviews/Projects/Discussion/Transcripts),
  *Udemy* (Overview/Q&A/Notes/AI). StarCi: maps onto the `TabsCard` block (left tabs = Nội dung/Thử thách,
  right tabs = language switcher TS/Java/C#/Go) — see `tabscard-two-secondary-groups` draft.
- **Problem-first sequencing** — *Brilliant* (drop into the problem before theory). Consider a "try first"
  lesson-step type for StarCi concept lessons.
- **What NOT to copy:** AI panel that covers video/editor controls (the CFI bottom-drawer mistake); full-bleed
  reading text on wide screens; auto-opening the AI panel (treat as pull, not push).

### 2.3 Gamification (XP / streak / league / badge / progress)
*(→ `gamification.md`, `duolingo.md`, `brilliant.md`, `khan-academy.md`, `codecademy.md`)*

- **One unified XP pool** — *Duolingo* (XP feeds streak + league + daily goal simultaneously). StarCi: don't split
  "lesson XP" vs "challenge XP" vs AI credit. One weekly XP total → league rank + daily goal. **AI credit is a
  SEPARATE resource meter** (fuel-gauge, not XP-bar shape) — exactly the `credit-unified-pool-ui` rule.
- **Weekly league screen** — *Duolingo* (the reference): 30-user list (avatar + name + weekly XP), **green
  PROMOTION zone** divider, **muted/red DEMOTION zone** divider (the *stronger* retention lever — mark it as
  prominently as promotion), countdown timer, own row highlighted (teal bg). Week-end full-screen result modal.
  StarCi: promotion zone teal, demotion zone neutral/muted (not alarming red), league in its OWN tab — not shoved
  into the home feed (anxiety for lower-ranked users).
- **Linear path metaphor, gold-filled nodes** — *Duolingo* (winding path), *Brilliant* (Rive color-coded nodes).
  StarCi module/lesson map: completed node = solid teal + checkmark, current = subtle pulsing ring, locked = grey.
  The path IS the progress indicator (kills multi-bar clutter).
- **Streak with freeze, not shame** — *Duolingo* (freeze, 60% widget lift), *Brilliant* (max-2 streak charges),
  *Khan Academy* (weekly streak = gentler for working adults). StarCi: flame + count in persistent top bar;
  streak-freeze as a Pro benefit; tone "Your streak is safe today" (green) not "You failed"; weekly cadence as the
  primary habit signal + daily streak as bonus.
- **Mastery as a named contract** — *Khan Academy* (Attempted→Familiar→Proficient→Mastered, point values,
  color-coded). StarCi: named mastery tiers per unit beats a bare "completed ✓"; per-course mastery rank as a
  profile/social identity hook ("You're a Pioneer in System Design").
- **Badge split: day-one personal records + long-term milestones** — *Duolingo* (33% vs 20% day-7 retention from a
  day-one badge), *Khan Academy* (rarity tiers). StarCi: at least one badge earnable in the first session, full
  celebration moment; locked badges as teal-tint silhouettes (completionist pull); on-brand league naming
  (*Brilliant* element names → StarCi tech ladder: Intern→Junior→…→Architect→Distinguished) beats Bronze/Silver.
- **Completion micro-animation** — *Brilliant/Duolingo*. Reserve motion for reward moments (lesson/streak/league),
  <800ms, accent-teal burst, fires BEFORE the "Next" CTA. UI otherwise still (matches StarCi calm aesthetic).
- **What NOT to copy:** leaderboard as a home-feed widget; two parallel progress metrics for one concept;
  guilt-trip dark patterns / sad-mascot shaming; trivially-farmable XP; check-in Skinner-box logins.

### 2.4 Onboarding & activation
*(→ `onboarding.md`, `duolingo.md`, `codecademy.md`, `brilliant.md`)*

- **Product-first / deferred signup (PLG)** — *Duolingo* (first lesson before account; reframe as "save your
  progress"). StarCi: let a guest pick a course → finish lesson 1 → then prompt signup. Big top-of-funnel win.
- **4–5 screen intent funnel** — *everyone*. StarCi: (1) "What do you want to learn?" track grid → (2) experience
  level (+ optional mini-quiz placement, real task not self-rating — *Brilliant*) → (3) daily time goal (animate
  a Day-1 streak starting) → (4) recommended course + "Start your first lesson" CTA.
- **Two-persona fork** — *Codecademy* ("Recommend a path for me" vs "I'll explore"). Both first-class; self-directed
  still gets the streak/XP container set up.
- **Introduce the gamification container on day 0** — *Duolingo/Brilliant*. Empty streak + 0/100 XP bar visible
  immediately; the empty container is the pull. First completion partially fills it + celebration.
- **Action-oriented empty states** — *Codecademy* (pre-populated first card). StarCi (content-first, whitespace):
  centered minimal line-art (teal accent) + one-line copy + single primary button; "My Challenges" empty = locked
  state "Complete a lesson to unlock", not an error; AI-credit zero = show the pool bar at 0 with a "how it works" link.
- **Social proof at friction points** — *Coursera*. Place learner count / outcome stat / testimonial next to the
  signup field and the paywall, above the CTA.
- **Progressive disclosure / everboarding** — reveal leagues after 3 lessons, not during onboarding; reduce nav
  clutter on first visit (avoid edX/early-Coursera empty-dashboard paralysis).
- **What NOT to copy:** feature tours before any action; email-gate before value (edX); >5 signup fields; auto-advance
  timers in the funnel.

### 2.5 Pricing, paywall & upgrade
*(→ `pricing-paywall.md`, `coursera.md`, `brilliant.md`, `duolingo.md`, `codecademy.md`, `edx.md`)*

- **Soft freemium gate at a success moment** — *Coursera* (Module-1 preview), *Brilliant* (first problems free,
  lock shows a preview of the next). StarCi: free first module OR audit content but gate certificate + AI credits +
  challenge submission + streak shields (the "credential + accountability" gate outperforms content gating).
- **Inline contextual paywall, NOT a redirect** — *Brilliant/Duolingo* (best). When a free user hits a locked node,
  show a card/sheet **in the lesson flow** (stay on page): one outcome headline personalized to the trigger feature,
  3–4 benefit bullets (teal checkmarks), plan options (annual default + "Save 40%"), single CTA, "Cancel anytime" muted.
- **Explicit two-path enrollment gate** — *edX* ("Upgrade Now" prominent vs "Audit" small-but-real). StarCi: at
  course-enroll, "Go Premium (full + AI co-pilot + league)" big teal vs "Continue free" ghost link — free is real
  but not co-equal in visual weight.
- **3-tier pricing page, highlighted middle** — *Codecademy/Coursera/Duolingo*. Annual/monthly toggle default annual
  + explicit savings. Outcome-framed feature rows ("Unlimited AI hints", "League ranking protection"), not feature names.
- **Friction-as-conversion (study, adapt carefully)** — *Duolingo* hearts/energy. StarCi equivalent: AI credits run
  out mid-lesson → gentle inline "You've used your free AI credits this week — upgrade to continue", felt in context,
  not an interrupt modal. Do NOT clone the hostile energy drain without Duolingo's scale/buy-in.
- **AI credit as plan differentiator** — unified pool fits cleanly: Free = N/week, Pro = unlimited; show
  "3 of 5 credits left this week" with a subtle upgrade link — ONE bar, one window (`credit-unified-pool-ui`).
- **What NOT to copy:** redirect-away-to-/pricing mid-flow; 4+ tiers (−31% conversion); fake countdowns;
  hollow free tier (edX backlash); banner + modal + sticky CTA all at once.

### 2.6 Dashboard & mobile
*(→ `dashboard-mobile.md`, `codecademy.md`, `coursera.md`, `khan-academy.md`, `duolingo.md`)*

- **Hero "Continue" card first** — *all platforms converge* (Codecademy "Today View", Coursera "resume in one
  click", Khan "Resume" shortcut). The single highest-value widget: course thumb + lesson name + progress bar +
  one "Resume" CTA, above the fold. Separate "now" (continue) from "library" (My Courses shelf).
- **Streak/XP in a persistent top bar, league in its own tab** — *Duolingo*. Streak = single line (address-bar
  weight, not a card). Daily-goal ring (not a bar — bars are for lesson-level). Leagues = dedicated tab, never a
  home-feed widget.
- **Bottom tab nav, 3–5 tabs, icon+label** — *Duolingo post-mortem* (non-standard icon-only failed). StarCi mobile:
  Home / Explore / Leagues (shield, "NEW" dot on new season) / Profile; AI as a FAB inside content screens.
- **Density restraint** — *Duolingo redesign* (whitespace > containers). Horizontal progress bar per course card
  (compare-at-a-glance), one bar at a time per the StarCi rule. Locked nodes shown inline with padlock (aspirational
  visibility converts) → tapped → bottom-sheet upgrade, not a navigation.
- **Responsive ladder** — lg: persistent left rail + content (+ optional right panel); md: collapsible rail drawer;
  <md: rail gone, bottom-nav, full-width content, FAB for AI.

### 2.7 AI co-pilot (cross-cutting)
*(→ `coursera.md`, `udemy.md`, `codecademy.md`, `khan-academy.md`, `brilliant.md`)*

- **Surface model** — *Coursera Coach* (floating circle → slide-in panel, context-aware) vs *Udemy/Codecademy*
  (right-panel **tab**, in-scope to the lesson). For StarCi reading lesson: floating teal sparkle button → drawer
  (keeps content clean). For the 3-pane challenge: a right-panel tab (lesson stays primary). Either way: panel
  slides in, never covers controls, never auto-opens.
- **Grounded + in-scope** — *Udemy/Codecademy* (answers only the current lesson; refuses out-of-context). StarCi
  `askContentAi` already scopes to content body — surface via highlight-to-ask + contextual panel, not a standalone chat page.
- **Socratic by default + hint ladder** — *Khan Academy/Brilliant Koji* (guide, don't give answers), *Codecademy*
  (hint before answer). StarCi: "guide me" (Socratic, cheaper) default vs "explain it" (direct); challenge hint
  ladder (approach → pseudocode → key insight), each hint a small credit cost — monetizes the AI credit system.
- **Context-aware of the current step/code** — *Brilliant Koji* (manipulates the live interactive element).
  Next-level StarCi: inject which lesson step / which code the user wrote into `askContentAi` context.

### 2.8 Trust, credential & "serious dev" tone (cross-cutting)
*(→ `edx.md`, `frontend-masters.md`, `coursera.md`, `freecodecamp.md`)*

- **Trust stacking on course/landing pages** — *Coursera/edX* (logos, enrollment count, rating, difficulty chip,
  cert badge, instructor credential above the fold). StarCi equivalent: learner count, completion %, badge-on-completion,
  AI co-pilot callout, "curated by StarCi" authority, XP-you'll-earn — concrete outcome artifacts are StarCi's "Harvard logo".
- **Practitioner credibility on cards** — *Frontend Masters* (instructor company affiliation as first-class card element).
- **Certificate / public profile as a shareable artifact** — *Coursera* ("Add to LinkedIn" first-class), *Frontend
  Masters* (public profile = portfolio, dark/light cert variants), *freeCodeCamp* (verifiable public URL, GitHub-style
  activity heatmap). StarCi: shareable public profile URL surfacing league rank + badge grid + XP graph + completed
  modules + a contribution heatmap; verifiable certificate URL per completed course.
- **Don't over-gamify the serious tone** — *Frontend Masters* keeps the player clean even though it has zero game layer.
  StarCi: keep gamification prominent (it's the differentiator) BUT keep the lesson/challenge player itself FM-clean.

---

## 3. Mapping a pattern onto the StarCi design system

Once a pattern is chosen, land it on StarCi without inventing primitives.

### 3.1 Pick the archetype (`design/03-layout-archetypes.md`)
- **Course detail** (`max-w-[1280px]`, `grid md:grid-cols-5`, 3/2 split, right-rail EnrollCard) → course-about,
  landing, pricing-adjacent pages.
- **Course learn** (`grid grid-cols-4`: icon sidebar + center module + right ModuleSidebar) → lesson reader,
  module overview, content map.
- **Challenge split** (`Modal size="full"`, `lg:grid-cols-5`, 2/3) → coding challenge, any split + code view.

### 3.2 The 3-tier page shell (`three-tier-page-layout` draft)
Every content page: **Tầng 1 Breadcrumb → Tầng 2 Header (H3, NOT H1/H2; title+desc dính `gap-0`, desc
`body-sm muted`; use `blocks/layout/PageHeader`) → Tầng 3 Content.** Same `h-3` spacer between tiers, same
`gap-3` within a tier, same column cap (`max-w-3xl mx-auto`) for breadcrumb + header + content (no drift). Padding
owned by the block/container (rail/content `p-6`), feature does placement only.

### 3.3 Tokens, color & spacing (`design/01-tokens.md`)
- **Accent teal `--accent` (`#00a898`)** = primary CTA, active nav, rating stars, progress fill, "Save %" — RESERVE
  it (don't use on muted/secondary). One color = one meaning (Khan Academy semantic-token discipline).
- **Semantic chips bright:** want-to-pop chip = `bg-<token>/10 text-<token>`; completion/"Free" = `success` green
  (NOT accent); never default HeroUI secondary (too dark).
- **Spacing by semantic relationship** (not size feel): `gap-1.5` coupled · `gap-3` same-function · `gap-6`
  different-function. Page shell `p-3`; rail/content blocks `p-6`.
- **Radius:** form/modal `rounded-3xl`; content card `rounded-xl`/`rounded-large`; chip `rounded-full`; code block `rounded-xl`.
- **Difficulty palette:** Easy cyan · Medium yellow · Hard red · Insane purple (`pallettes/difficulty.ts`).
- **Light + dark** (default dark + enableSystem): test both; use tokens, never hex.

### 3.4 Reuse blocks, not primitives (`design/02-components.md` + `../../cannon/CONTENT.md`)
HeroUI v3 first (Card default surface — NO shadow, NO `bg-default/40` override; Chip `size="sm" variant="soft"
color="accent"`; Alert/Breadcrumbs/Accordion/Modal/ListBox+ScrollShadow/Stepper/Separator/Spinner). Reusable
inventory: count-chip (BookOpen/Video/Sword + number), meta-chip (Clock "15 phút đọc"), sidebar icon-nav (active =
`text-accent bg-accent/10`), pricing Stepper (Pioneer/Early-Bird/Regular + "Save %"), value-props checklist
(SealCheckIcon), code block (CodeToHtml/Shiki + copy), MarkdownContent. The `TabsCard` block
(`blocks/navigation/TabsCard`) owns the two-secondary-tab-group toolbar (content/challenge left + language right) —
see `tabscard-two-secondary-groups`. Async states via the AsyncContent/EmptyContent/ErrorContent family
(`starci-async` skill). Cannon golden law: data flows DOWN from `features/` into props-only `blocks/`; blocks own
pixels, features own data/i18n.

### 3.5 Honor the existing rule drafts (these are already-won arguments)
- `one-progress-bar-at-a-time` — total bar at top; open accordion group → 1 bar; collapsed → "n/m" muted.
- `rail-long-title-and-spacing` — long nav title = full-width line + truncate + tooltip; meta to line 2; `text-base`; `p-6`.
- `three-tier-page-layout` — breadcrumb → H3 → content, aligned caps, `h-3` rhythm.
- `tabscard-two-secondary-groups` — one toolbar with two tab groups = the `TabsCard` block, both secondary.
- `credit-unified-pool-ui` — one credit pool by WINDOW (5h/7d), not split by lane/source; read-only effectiveMode.

### 3.6 Motion budget
Reserve animation for reward moments (lesson/module/course complete, XP gain, streak increment, league promotion):
<800ms, accent-teal burst, fires before the next CTA. Navigation/page transitions subtle (fade ~150ms). UI otherwise
still — matches the content-first, whitespace-heavy aesthetic (Brilliant's "motion = signal, not noise").

---

## 4. The output artifact (no production code)

Produce a brainstorm doc + chat summary; draw a widget if the layout/component is new. NEVER write production code
in this skill (that's `/ux-apply`).

### 4.1 Doc shape — `<Feature>/UX-BRAINSTORM.md`
```
# <Page/Component> — UX Brainstorm
## Goal lens + objective (the user's one job in ≤30s; who; which lens A–E)
## Inventory (what StarCi data/features exist; legacy pains — inventory only, not the design)
## Refs consulted (../../refs/<slug>.md + the specific pattern pulled from each)
## Directions (≥2–3) — each: name · ref it neon to · sketch · trade-off
## Recommended direction + why
## Section → BE/DB field map (+ unused fields = opportunities)
## States: empty / loading / error / dark mode
## Design-system landing: archetype · blocks reused / new · tokens · which rule drafts apply
## Open questions for thầy
```

### 4.2 Chat summary
Objective · new IA · the directions + the chosen one · section→data table · refs anchored · what's cut/added.

### 4.3 Widget mockup (mandatory for new layout/component)
`mcp__visualize__read_me` (module `mockup`) → `mcp__visualize__show_widget`: 1–3 scenarios side by side, flat, CSS
vars, accent teal, no real-content clutter; each scenario = tagline + trade-off + ref anchor; mark the proposed one
(e.g. info-border). Thầy looks + picks. Then `/ux-apply` builds it.

### 4.4 Capturing feedback
Any time thầy rules on something general, write `.claude/rules/drafts/<temp>.md` (a generalized principle) — do NOT
edit stable rule files (`main.md` / `starci-*.md`) directly. The merge happens via `/merge`.

---

## 5. Quick reference — ref file index

| ref file | platform / topic | open it for |
|---|---|---|
| `../../refs/coursera.md` | MOOC, credential | week-accordion player, trust stacking, Coach AI, certificate-to-LinkedIn, goal onboarding |
| `../../refs/udemy.md` | marketplace | hover-preview cards, sticky purchase sidebar, social-proof saturation, in-player AI tab, fix-the-flat-dashboard |
| `../../refs/duolingo.md` | habit/gamified | streak+freeze, unified XP, leagues (promotion/demotion), deferred signup, friction-as-conversion, path metaphor |
| `../../refs/khan-academy.md` | mastery, free | named mastery tiers, Learner Queue "do this next", progressive hints, Socratic AI, semantic color tokens, weekly streak |
| `../../refs/brilliant.md` | STEM, premium | problem-first, Rive gameboard nodes, streak charges, subject-coded accent, inline paywall, Koji context-aware AI |
| `../../refs/codecademy.md` | learn-to-code | 3-pane editor, in-scope AI assistant, weekly-target+streak pairing, hint-before-answer, two-path onboarding |
| `../../refs/edx.md` | MOOC, institutional | map-vs-player split (2024), audit/paid two-path gate, subject landing SEO pages, credential-as-conversion |
| `../../refs/skillshare.md` | creative, subscription | project-per-module, two-column player + tab architecture, interest-onboarding rails, student-project gallery |
| `../../refs/frontend-masters.md` | premium dev | practitioner credibility on cards, dual-pane player, sparse cards, public-profile-as-portfolio, keep-game-layer |
| `../../refs/freecodecamp.md` | free nonprofit | step-count progress, two-click-to-editor, verifiable public credential URL, test-as-spec, activity heatmap |
| `../../refs/onboarding.md` | cross-cutting | PLG deferred signup, intent funnel, two-persona fork, day-0 gamification container, empty states, DO/DON'T |
| `../../refs/catalog-discovery.md` | cross-cutting | search-first hero, card anatomy, faceted filters, recommendation rails, course-about page, DO/DON'T |
| `../../refs/lesson-player.md` | cross-cutting | two-column layout, accordion outline, transcript, 3-pane code, sticky prev/next, AI panel, StarCi 3-content-type plan |
| `../../refs/gamification.md` | cross-cutting | unified XP, league screen layout, streak-with-freeze, badge split, path metaphor, DO/DON'T, anti-patterns |
| `../../refs/pricing-paywall.md` | cross-cutting | soft gate at success moment, inline modal, 3-tier annual-default, AI-credit gate, freemium+gamification, DO/DON'T |
| `../../refs/dashboard-mobile.md` | cross-cutting | hero "continue" card, top-bar streak/XP, bottom-nav, density restraint, responsive ladder, freemium lock UI |
