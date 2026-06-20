<div align="center">

# ⭐ StarCi · Frontend Skills

### Agent-native design system for shipping production UI at content-creator speed

[![Claude Code](https://img.shields.io/badge/Claude_Code-Plugin-d97757?logo=anthropic&logoColor=white)](https://docs.claude.com/en/docs/claude-code)
[![HeroUI v3](https://img.shields.io/badge/HeroUI-v3-00a898)](https://heroui.com)
[![Next.js](https://img.shields.io/badge/Next.js-App_Router-000000?logo=nextdotjs)](https://nextjs.org)
[![React 19](https://img.shields.io/badge/React-19-149eca?logo=react&logoColor=white)](https://react.dev)
[![License: MIT](https://img.shields.io/badge/License-MIT-22c55e)](LICENSE)

*The exact skills that power **[StarCi Academy](https://github.com/starci-lab)**'s UI 2.0 — extracted, documented, and open-sourced.*

</div>

---

## 👋 Who is StarCi?

We build at the intersection of three things — and we automate everything in between:

| Pillar | What it means |
|---|---|
| 🎓 **Tech KOL & Education** | We teach Fullstack, System Design & DevOps the way they're really practiced — practice-led, production-grade, no fluff. These skills are the same ones our agents use to build the academy itself. |
| 🤖 **Automation Corp** | Agent-first engineering. Pipelines, content, audits, and UI — orchestrated by AI agents on top of strict, machine-readable conventions. This repo *is* that convention layer for the frontend. |
| ⛓️ **Blockchain & DeFi** | On-chain execution, market-making, and high-throughput trading infrastructure. The same rigor we bring to settlement logic, we bring to a button's focus ring. |

> **Why open-source it?** A design system that only humans can read drifts. One that an **agent** can read — and enforce — stays consistent across hundreds of pages and thousands of commits. This is craft, made reproducible.

---

## 📦 What's inside

A [Claude Code](https://docs.claude.com/en/docs/claude-code) plugin: **7 skills** + the full **UI 2.0 design system** they enforce.

```
starci-fe-skills/
├── skills/             # 7 invokable Claude Code skills
│   ├── fe/                     →  /fe          main FE conventions + golden rules (the SSOT entry point)
│   ├── ux-brainstorm/          →  /ux-brainstorm  re-imagine a page's UX from real backend data (Opus, no code)
│   ├── ux-apply/               →  /ux-apply    implement the redesigned information architecture
│   ├── ui-apply/               →  /ui-apply    the "skin" pass — tokens, spacing, radius, look
│   ├── starci-async/           →  loading / error / empty / content via AsyncContent
│   ├── merge/                  →  /merge       fold pending rule drafts into the stable SSOT
│   └── skill-code-example-fe/  →  patterns for lesson FE repos (Vite + React 19)
│
├── rules/              # The strict, enforceable SSOT
│   ├── main.md                 →  16-section law: architecture · style · tokens · a11y · smells
│   └── starci-<element>.md     →  per-element render rules (button, card, chip, form, …)
│
├── design-system/      # Grounded, descriptive design docs (tokens, typography, archetypes, skeletons, modals)
└── patterns/           # Code/architecture patterns (App Router, GraphQL, SWR singletons, Redux, i18n, …)
```

### The one law everything follows

> **Every kind of decision lives in exactly ONE layer. Style flows one direction; features only compose — they never paint.**

| Layer | Lives in | Decides only |
|---|---|---|
| 4 · Features | `components/features/**` | what data to read, what to dispatch, what to compose — **zero styling** |
| 3 · Blocks | `components/blocks/**` | reusable composed pieces that **own their style**, props-only |
| 2 · HeroUI + globals | `@heroui/react` + `globals.css` | how things look (use HeroUI directly; override BEM globally) |
| 1 · Tokens | `globals.css` | semantic CSS vars: color · spacing · radius · type |

If you need `!important` to override your own code, a decision is in the wrong layer.

---

## 🚀 Install

**Install as a Claude Code plugin** — one marketplace, all skills. Every FE dev runs this on their machine:

```bash
# inside Claude Code
/plugin marketplace add starci183/starci-fe-skills
/plugin install starci-fe-skills@starci-fe-skills
/reload-plugins
```

The plugin bundles `decision/` + `design/` + `ui/` + `cannon/`, so the skills' relative reads still resolve after install.
Skills surface namespaced as `/starci-fe-skills:<skill>`:

```
/starci-fe-ux-brainstorm   brainstorm 1–3 layouts for a page (+ widget mockups)
/starci-fe-ux-apply        build the chosen layout on-canon + update the journal (auto, end of task)
/starci-fe-cannon-audit    audit existing FE against the code canon
/starci-fe-cannon-apply    write new FE code on-canon
```

**Author / live-edit (maintainer):** clone the repo, add the LOCAL path as a marketplace
(`/plugin marketplace add D:\Repositories\starci-fe-skills`), edit skills in place, `/reload-plugins` to
test, then `git commit && git push` to publish for everyone. No reinstall needed while iterating.

**Just want the design system?** Read [`rules/main.md`](rules/main.md) → [`design-system/README.md`](design-system/README.md) → [`cannon/CONTENT.md`](cannon/CONTENT.md). It's all grounded in real shipped code, not theory.

---

## 🧠 The drafts → merge workflow

Rules are never edited in place during a build. When a new convention is learned, it lands in `rules/drafts/<name>.md` (newest wins on conflict). `/merge` folds drafts into the right home — general law → `main.md`, element styling → `starci-<element>.md` — then deletes them. Conventions evolve **without** silent drift.

---

## 🧩 Tech stack this targets

Next.js App Router · React 19 · HeroUI v3 (`@heroui/react`) · Tailwind CSS v4 · SWR · Redux Toolkit · zustand · react-hook-form + zod · Phosphor Icons · next-themes · next-intl.

---

## 📜 License

MIT © [StarCi](https://github.com/starci183) — use them, fork them, ship faster.

<div align="center">

**Part of the StarCi skills suite:**
[fe](https://github.com/starci183/starci-fe-skills) ·
[be](https://github.com/starci183/starci-be-skills) ·
[ops](https://github.com/starci183/starci-ops-skills) ·
[content](https://github.com/starci183/starci-content-skills)

*Built by agents. Reviewed by humans. Shipped at KOL speed.*

</div>
