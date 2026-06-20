# refs/ — Course-website UX/UI reference library

A **shared, root-level library** of UX/UI references mined from the leading course / learning
platforms. Each file is a grounded teardown (gathered by parallel research agents, with source
URLs) of how a real product solves a UX problem — so StarCi design work copies *patterns that
proven products use*, not guesses.

## What it's for

- **Primary consumer:** the [`starci-ux-brainstorm`](../skills/starci-ux-brainstorm/SKILL.md)
  skill — when re-imagining a StarCi page it opens 2–4 relevant refs, lifts the parts those
  products do well, and notes what *not* to copy.
- **Also useful for** any FE design/UX decision (component look, layout archetype, gamification,
  pricing/paywall, onboarding) where "how do the best learning apps do this?" is the question.
- **How to use:** don't read all 16. Pick by the page's job (see table), open those, extract
  concrete moves, then map onto the StarCi design system (`../cannon/CONTENT.md` +
  `starci-academy/.claude/design/`). Never design from memory when a ref exists.

> These are *inspiration + evidence*, not StarCi rules. The StarCi rules live in
> [`../cannon/CONTENT.md`](../cannon/CONTENT.md) (code) and the design-system docs (visual).

## The references

### Platform teardowns (one product, end-to-end)
| File | Product | Open it when you need… |
|---|---|---|
| [`coursera.md`](coursera.md) | Coursera | university-MOOC catalog, specialization/certificate landing pages, serious/credential vibe |
| [`udemy.md`](udemy.md) | Udemy | marketplace catalog, search/ratings, sticky pricing card, sales/urgency patterns |
| [`duolingo.md`](duolingo.md) | Duolingo | **gamification gold standard** — streaks, XP, leagues, hearts, lesson path, habit loops |
| [`khan-academy.md`](khan-academy.md) | Khan Academy | mastery learning, skill tree, progress dashboard, free-model UX |
| [`brilliant.md`](brilliant.md) | Brilliant | interactive lessons, premium feel, visual problem-solving, onboarding |
| [`codecademy.md`](codecademy.md) | Codecademy | in-browser IDE, learn-by-doing, paths/projects, coding-challenge UX |
| [`edx.md`](edx.md) | edX | academic program pages, course-about pages, enrollment flow |
| [`skillshare.md`](skillshare.md) | Skillshare | creative discovery feed, community projects, subscription |
| [`frontend-masters.md`](frontend-masters.md) | Frontend Masters | developer-focused course player, workshop format, learning paths |
| [`freecodecamp.md`](freecodecamp.md) | freeCodeCamp | curriculum map, certifications, in-browser challenges, nonprofit/free |

### Aspect cross-cuts (one UX problem, across products)
| File | Aspect | Open it when you're designing… |
|---|---|---|
| [`onboarding.md`](onboarding.md) | Onboarding & activation | first-run, goal/skill selection, time-to-first-value, empty states |
| [`catalog-discovery.md`](catalog-discovery.md) | Catalog & discovery | browse/search/filters, course cards, recommendation rails, course-about pages |
| [`lesson-player.md`](lesson-player.md) | Lesson / content player | video + reading + code-playground layouts, outline sidebar, next/prev, notes |
| [`gamification.md`](gamification.md) | Progress & gamification | streaks, XP, levels, badges, leagues/leaderboards, paths, daily goals |
| [`pricing-paywall.md`](pricing-paywall.md) | Pricing, paywall & upgrade | freemium limits, plan pages, upgrade nudges, social proof, trial, conversion |
| [`dashboard-mobile.md`](dashboard-mobile.md) | Dashboard & mobile | learner home, continue-learning, progress widgets, responsive/mobile nav |

## Keeping it fresh

Regenerate with the `build-ux-brainstorm-refs` workflow (parallel Sonnet research → Opus
synthesis) when the design bar moves or a new pattern is worth capturing.
