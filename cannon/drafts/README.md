# cannon/drafts/ — staging for new code-pattern rules

Stage new FE **code-pattern** conventions here as `<kebab-name>.md` while coding — never edit
`../CONTENT.md` (the stable canon) in place mid-build.

Each draft should carry, when known:
- a one-line **target**: which `CONTENT.md` SLICE it belongs to (e.g. "§ đích: SLICE 3 Data Fetching")
- the **RULE** + a real `src/...` example + **DO/DON'T** + the **VIOLATION** an audit should flag
- a date, so newest-wins on conflict

Run **`/starci-fe-update-mindset`** to fold every draft here into `../CONTENT.md` (the right slice +
Appendix A ledger), reconcile conflicts (newest wins), then delete the merged drafts.

> Visual / UX rule drafts live in the app repo at `<app>/.claude/rules/drafts/` instead — the same
> skill merges those into the app's `starci-*.md` rules / design docs.
