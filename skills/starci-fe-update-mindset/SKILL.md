---
name: starci-fe-update-mindset
description: >
  Fold the recorded drafts into the house knowledge so the skill gets smarter — step 3 of the self-learning
  loop. Reads every draft staged by /starci-fe-ux-apply (and mid-coding) and merges it into the right home:
  `journal/drafts/*` → `journal/journal-<block>.md`, `cannon/drafts/*` → `cannon/CONTENT.md`,
  `refs/drafts/*` → `refs/CONTENT.md` (newest-wins), then deletes the merged drafts. Use when the user says
  "/starci-fe-update-mindset", "merge", "cập nhật skill", "gộp drafts", "gộp kinh nghiệm", "update canon",
  "fold rules", or after a batch of drafts has piled up.
---

# /starci-fe-update-mindset — fold drafts into the house knowledge (make the skill smarter)

Step 3 of the loop. This is what turns recorded feedback into a permanently smarter skill. Skill paths
`../../journal`, `../../cannon`, `../../refs`.

## What it merges
| Read drafts from | Fold each into | How |
|---|---|---|
| `../../journal/drafts/*.md` | `../../journal/journal-<block>.md` | add a dated decision entry under "House decisions (newest first)" for the matching block |
| `../../cannon/drafts/*.md` | `../../cannon/CONTENT.md` | the right SLICE (RULE · example · VIOLATION) + Appendix A ledger if it's a new known-drift |
| `../../refs/drafts/*.md` | `../../refs/CONTENT.md` | append/refresh under "Accumulated reference lessons" |

If all three drafts folders are empty, say so and stop.

## How to merge (do it well)
1. Read every draft. Decide its exact home (block file / cannon slice / refs lessons).
2. **Distil, don't paste.** Fold a refinement into an existing entry; add a new one only when genuinely new.
   Keep it tight and in the file's voice.
3. **Newest wins** on conflict — update the stable knowledge, the draft becomes the source of truth for that
   point afterwards.
4. Keep it grounded — cite a real `src/...` path / page / block. An un-evidenced hunch stays a draft (flag it).
5. **Delete merged drafts** (`git rm`). Leave un-mergeable ones in place with a note.

## After
- Report a table: `draft → destination → what changed → conflicts resolved (winner)`.
- **Do NOT push.** Stage the changes; the user reviews and publishes with `.claude/sync-skills.ps1` (or
  `git push` in the skills repo). The next `/starci-fe-ux-brainstorm` now reads the richer knowledge.
