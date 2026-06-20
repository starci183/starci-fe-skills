## Lesson / Content Player — Best-Practice Reference

---

### Dominant Patterns (recurring solutions across all leading platforms)

**1. Two-column master layout (video/content left, outline right)**
The dominant desktop layout is a wide main content area (video or reading, typically 60–70% of viewport width) paired with a persistent right sidebar (30–40%) containing the course outline. Udemy, Coursera, Thinkific, and edX all use this pattern. The sidebar is sticky/fixed so it remains scrollable while the main content scrolls independently. On smaller viewports the sidebar collapses to a drawer or bottom sheet.

**2. Tab strip beneath video for contextual panels**
Rather than stacking everything in one long scroll below the video, platforms attach a horizontal tab bar directly beneath the player. Tabs switch between distinct contexts without navigating away:
- Udemy: Overview / Q&A / Notes / Announcements (accessed via icons top-right; AI assistant button added in 2024–2025)
- Coursera: Course Content / Notes / Discussion / Info
- Thinkific: Lesson / Community / Notes

**3. Transcript as first-class interactive component**
The transcript is not a caption file buried in settings. It lives as a scrollable, auto-highlighting text panel adjacent to or below the video. Clicking any line seeks the video to that timestamp (Coursera, edX, Khan Academy). Coursera adds highlight-to-save-note directly in the transcript, with the video staying visible picture-in-picture (bottom-right corner) while the user scrolls the full-width transcript.

**4. Sticky prev/next navigation — header or bottom bar, never inline-only**
Navigation is anchored either to a sticky top header bar (lesson title + chevron buttons, used by CFI after their March 2025 redesign, Thinkific) or to the bottom of the viewport. Placing next/prev only as text links at the very bottom of the page scroll is the anti-pattern — learners who watch the whole video without scrolling miss it. Udemy puts prev/next arrows to the right of the video progress bar in the player chrome itself (always visible during playback).

**5. Course outline with collapsible section groups + completion checkmarks**
The right/left sidebar outline is an accordion: sections collapse/expand. Each lesson item shows:
- A checkbox or checkmark for completion state (empty square → filled checkmark on Udemy)
- Duration (for video) or item type icon (article, quiz, code exercise)
- The currently active lesson highlighted in accent color
Udemy auto-marks a lecture complete after the user watches a set percentage of the video. Manual toggle also available.

**6. Three-panel split view for code exercises**
Introduced at scale by Codecademy and now standard for coding platforms: left panel = instructions/theory, center panel = code editor, right panel = live output/preview. The gutter between panels is draggable. Codecademy's 2024 update moved the Back/Next buttons from the middle editor panel to the top-right corner — keeping navigation out of the editing zone. LeetCode uses a similar 2-panel model (description left, editor + test console right), with a "Dynamic Layout" vs "Split View" toggle introduced to let users choose.

**7. Linear progression by default, with visible sidebar for free navigation**
Sequential gating (Next unlocks after completing current content) is the dominant pattern for structured courses (Coursera, Udemy, Thinkific). However, the full course outline remains visible and clickable — learners can jump to any already-visited lesson or skip ahead by clicking the sidebar directly. The "locked" state for future content is shown with a lock icon or grayed text, not hidden. Khan Academy takes the opposite stance — free navigation everywhere, mastery percentage shown per unit.

**8. Progress bar always visible, percentage + time estimate**
A top progress bar across the header (or bottom of player) showing percentage complete is present on all platforms. Udemy shows it in the right sidebar header. Coursera shows it per-module in the outline. Best-practice articles consistently cite "progress bars should be visible at all times during a course" with both percentage and estimated time-to-completion.

**9. Autoplay / resume**
Udemy autoplays next lecture by default (toggleable via settings gear). All platforms auto-resume from last position on return to a partially watched video.

**10. Content width constraint for reading lessons**
Reading/article lessons limit line length to approximately 65–75 characters (typically `max-w-2xl` to `max-w-3xl`, i.e., 42–48rem on a 16px base). This is the Bringhurst optimal-reading principle applied to screens. Coursera and Khan Academy keep reading content in a centered, constrained column even when the shell is full-width.

---

### Concrete Examples Per Platform

**Coursera**
- Layout: video full-width top, tab bar below (Course Content / Notes / Discussion / Info), right sidebar docked with module tree and completion states.
- Transcript: auto-scrolling, clickable timestamps, highlight phrase → "Save Note" pop-up saves to notes panel; video collapses to PiP bottom-right while transcript is in focus.
- Notes: centralized note dashboard on course homepage; notes accessible per-module or all-at-once; screenshot capture from video (single click, no pause needed).
- Reading lessons: constrained column, clean typographic hierarchy, no sidebar clutter during reading.
- Next/prev: fixed at top of content area; course outline is collapsible tree in right panel.
- Source: [Coursera Note-Taking Blog](https://blog.coursera.org/ready-for-retention-presenting-a-unified-note-taking-experience/)

**Udemy**
- Layout: video occupies ~70% left. Right panel = accordion course outline with section headers, lesson rows (checkbox, icon, title, duration). Right panel is fixed height, independently scrollable.
- Below-video tabs: Overview / Q&A / Notes / Announcements. AI Assistant icon added top-right in 2024.
- Prev/Next: embedded in video player chrome (arrow buttons flanking the progress bar). Autoplay toggle in settings gear.
- Completion: empty square beside each lecture row → clicked or auto-marked after watch threshold.
- Source: [Udemy Course Player FAQ](https://support.udemy.com/hc/en-us/articles/34345830524183-Udemy-s-New-Course-Experience-Frequently-Asked-Questions), [Udemy Business Player](https://business-support.udemy.com/hc/en-us/articles/360024140354-How-to-Use-the-Course-Player-and-Start-Your-Course)

**Khan Academy**
- Layout: video or article in center column (constrained ~700px), left nav for unit tree, exercise follows directly below or after the video in a single vertical scroll.
- Transcript: toggleable panel beneath video, click-to-seek. Text version available for all video lessons (community-requested feature).
- No paywall friction in the player itself — all content free.
- Khanmigo AI tutor: contextual AI available per exercise and per video/article ("Khanmigo never gives the answer, guides learners to find it themselves"), accessible via a dedicated button in the exercise interface.
- Progress: mastery % per unit shown in skill tree; no per-lesson lock.
- Source: [Khan Academy UI (ScreensDesign)](https://screensdesign.com/showcase/khan-academy), [Khanmigo](https://www.khanmigo.ai/learners), [KA 2025 Updates](https://blog.khanacademy.org/2025-khan-academy-updates-every-teacher-should-know/)

**Codecademy**
- Layout: strict 3-panel horizontal split. Panel 1 (left, ~33%): lesson instructions + theory text. Panel 2 (center, ~33%): Monaco-based code editor, Run button bottom. Panel 3 (right, ~33%): output/browser preview.
- November 2024 UI update: Course Menu button moved top-left. Back/Next buttons moved to top-right corner (out of the editor zone). Reset Exercise and Copy to Clipboard buttons below editor.
- All navigation stays in persistent top bar across all 3 panels — learner never loses orientation.
- Source: [Codecademy Learning Environment Updates](https://help.codecademy.com/hc/en-us/articles/1260803449210-Updates-to-our-Learning-Environment), [Codecademy 3-panel description (Medium)](https://medium.com/@_dianapham/the-basics-of-learning-to-code-codecademy-50edabf1a96f)

**Brilliant.org**
- Layout: vertical scroll of discrete problem/interactive "cards" — no video as primary medium. Each card is a self-contained interaction (multiple choice, slider, visual puzzle, weight-balance mechanic, etc.).
- Navigation: forward-only within a lesson; no sidebar outline in-lesson. Top shows course pathway visualization showing position in the branching map.
- Feedback: immediate in-card (wrong → interactive explanation with active exploration, not passive text). Completing a lesson triggers XP counter animation + celebratory motion.
- No transcript (no video-first content); density is LOW — one concept per screen.
- Source: [Brilliant UI Breakdown (ScreensDesign)](https://screensdesign.com/showcase/brilliant-learn-by-doing), [ustwo x Brilliant](https://ustwo.com/work/brilliant/)

**Duolingo**
- Layout: single-column centered card (mobile-native mental model even on desktop). One exercise per screen, answer at bottom, progress bar at top.
- No sidebar, no outline — deliberately linear. Skill-level milestones visible as path checkpoints.
- Feedback: immediate (correct/wrong), sound + animation. XP counter updates instantly.
- Reading/Stories: same linear single-card model, dialogue bubbles + tap-to-translate words.
- 2025 unified feed: exercises + stories + practice merged into one feed with Practice Hub tab.
- Source: [Duolingo UI patterns (Banani)](https://www.banani.co/references/apps/duolingo), [Duolingo 2025 UI changes](https://duolingoguides.com/ui-change-that-duolingo-users-want/)

**edX / Open edX**
- Layout: left sidebar groups all learning material with nested navigation; clicking an item loads content on the right.
- Collapsible sections prevent overwhelming long curricula.
- Video player: caption/transcript in an interactive sidebar panel beside the player; benefit noted for accessibility (hearing impaired + non-native speakers).
- Media player controls: reduced chrome during playback to maximize content space.
- Source: [OpenCraft Open edX Themes](https://opencraft.com/designing-better-open-edx-themes/), [edX Accessibility Docs](https://edx.readthedocs.io/projects/edx-partner-course-staff/en/latest/accessibility/best_practices_course_content_dev.html)

**Thinkific**
- Layout: left sidebar (course outline) + main content area right. Clean minimal chrome.
- Standard tab pattern: Lesson / Community / Notes below content.
- Course player is customizable (brand colors, header/footer options, individual course appearance overrides).
- Source: [Thinkific Course Player](https://support.thinkific.com/hc/en-us/articles/360030372514-The-Thinkific-Course-Player)

**LeetCode (coding challenges)**
- Layout: 2-panel split (description/discussion left, editor + test console/submissions right). Resizable gutter.
- 2024 redesign introduced "Dynamic Layout" mode (panels re-organize based on content type) vs classic "Split View" — user-selectable.
- Problem description includes: title, difficulty badge (Easy/Medium/Hard), tags, acceptance rate, description, examples, constraints, hints (collapsible), community solutions tab.
- Source: [LeetCode UI discussion](https://leetcode.com/discuss/interview-question/4770646/Leetcode-UI:-Dynamic-Layout-vs-Split-View-mode)

**CFI (Corporate Finance Institute) — March 2025 redesign**
- Moved lesson title, AI Chat button, like/dislike, and next-lesson control into a single sticky header above the video/content. Previously next was at the bottom — users reported it was obscured by video playback controls.
- Demonstrates the real-world failure of bottom-sticky next/prev when it conflicts with media controls.
- Source: [CFI Course Player Update March 2025](https://help.corporatefinanceinstitute.com/article/1237-course-player-update-march-2025)

---

### DO / DON'T Heuristics

**Layout and structure**
- DO: constrain reading content to 65–75 chars per line (`max-w-2xl`/`max-w-3xl`). Long lines kill reading speed.
- DO: keep all 3 tiers (breadcrumb → title/meta → content) aligned to the same column width. Mismatched max-widths break visual flow.
- DO: give the sidebar its own independent scroll; never let it scroll with the page.
- DON'T: put the lesson outline AND the tab content panel in the same scrollable column — they serve different jobs.
- DON'T: full-bleed reading text on a 1440px screen. Content areas must be capped.

**Navigation (prev/next)**
- DO: put prev/next in a sticky location visible without scrolling — header, video chrome, or (carefully) a fixed footer that does NOT overlap video controls.
- DO: autoplay next lesson by default on video courses; make it cancellable (countdown overlay, 5s).
- DON'T: place next/prev only at the bottom of a long-scroll reading lesson (CFI's lesson: moved to header after user complaints).
- DON'T: hide next until the user scrolls all the way down — it creates artificial friction.

**Sidebar / course outline**
- DO: accordion sections with completion checkmarks per item.
- DO: auto-expand the section containing the current active lesson; auto-scroll sidebar to the current item.
- DO: show item type icons (video, article, quiz, code) — learners plan their time by type.
- DON'T: show only section-level completion bars when individual item state matters (the "n/m" count is supplement, not replacement).
- DON'T: make the sidebar full-height opaque on mobile — use a slide-in drawer or bottom sheet.

**Video player**
- DO: progressive disclosure of controls — hide toolbar until hover/tap; show only essential controls at rest.
- DO: offer playback speed (0.75×, 1×, 1.25×, 1.5×, 2×) — learners use this heavily.
- DO: keyboard shortcuts (space = play/pause, arrow keys = ±5s).
- DON'T: crowd the player with non-player chrome (outlines, tabs, ads) during full-screen.

**Transcript**
- DO: click-to-seek from any transcript line.
- DO: auto-highlight the current speaking line as the video plays (follows along without user action).
- DON'T: put the transcript on a separate page or require navigation to find it. It belongs adjacent to or below the player.

**Notes**
- DO: single-click save from video (screenshot) and from transcript (highlight + save). No modal, no page leave.
- DO: PiP or thumbnail video while the user reads/highlights transcript.
- DO: centralize all saved notes in one accessible dashboard (course-level or per-module filter).
- DON'T: require the user to open a separate note-taking app. In-player note capture has significantly higher retention than external tools.

**Code exercises (3-panel split)**
- DO: instructions in left panel, editor center, output right. Left-to-right reading order mirrors cognitive flow (read → write → see).
- DO: put Reset and Run in the editor panel, Back/Next in the persistent top bar — keep navigation out of the editing context.
- DO: draggable gutters between panels (users have wildly different monitor sizes and comfort with code density).
- DON'T: auto-collapse the instructions panel on narrow viewports without giving a way to toggle it back.

**Progress and gamification**
- DO: show a top progress bar (% complete + estimated remaining time) throughout the lesson, not just on the course home.
- DO: celebrate milestones — lesson complete animation, module complete card, XP increment — but keep them dismissible in ≤3s.
- DON'T: spam progress notifications mid-lesson. One celebration moment per logical unit.

**AI co-pilot**
- DO: place AI chat as a slide-in panel or overlay triggered by a single sticky button — it should not break the layout.
- DO: keep the lesson visible (or minimized/PiP) while the AI panel is open; context-aware AI that knows which lesson/challenge is active is far more useful than a generic chatbot.
- DON'T: put AI in a bottom drawer that covers the video controls (same CFI problem pattern).
- DON'T: auto-open the AI panel — treat it as pull (user-initiated) not push.

**Typography and density**
- Body text: 15–16px base, `line-height` 1.5–1.6. Sans-serif.
- Code text: 13–14px monospaced, higher contrast.
- Content column: `max-w-[65ch]` to `max-w-[75ch]` for articles.
- Section headings inside a reading lesson: H3 at most (H1/H2 compete with the shell chrome hierarchy).
- Source: [UXPin Optimal Line Length](https://www.uxpin.com/studio/blog/optimal-line-length-for-readability/), [LearnUI Font Size Guide](https://www.learnui.design/blog/mobile-desktop-website-font-size-guidelines.html)

---

### Takeaways for StarCi Academy

StarCi has **three distinct content types** that each need a tailored player:

**1. Reading lessons (current primary type)**
- Shell: sticky top bar = `breadcrumb + lesson title (H3, truncate+tooltip) + AI co-pilot icon + prev/next chevrons`. No more than 60px tall.
- Content column: `max-w-3xl mx-auto`, `p-6` container, `text-base` (16px) body, `leading-relaxed`.
- Below content: module outline in a collapsible sidebar (right rail on lg+, drawer on mobile). Use the one-progress-bar-at-a-time rule from your draft: open group → show progress bar; collapsed group → show `n/m` count muted only.
- Notes: floating bookmark icon in top bar → side panel (slide-in) listing auto-captured scroll position + manual text annotations. Do NOT redirect to a separate page.
- Next trigger: bottom of content `+ sticky chevron in top bar`. Both present, both functional.

**2. Coding challenges**
- Three-panel split: left = challenge instructions + AI hint toggle, center = Monaco editor (or custom editor), right = test output + submit panel.
- Top bar persistent across all three panels: `breadcrumb + challenge title + difficulty badge (Easy/Medium/Hard) + AI co-pilot icon + Submit button`.
- Gutter between left/center and center/right draggable with a visible handle.
- Left panel "collapsible to icon rail" on narrow viewports.
- AI co-pilot: Socratic — never gives the answer, guides reasoning. Panel slides in over center, pushes output right (does not cover editor).

**3. Video lessons (if added)**
- Embed in the reading layout shell; video replaces the content column top. Transcript panel as a tab below the video (auto-scroll, click-to-seek).
- PiP video while user reads transcript or notes.
- Autoplay next with 5s countdown banner at the bottom of the player (not a full overlay).

**Cross-cutting concerns:**
- Accent teal `#00a898`: use as the completion checkmark color, active sidebar item left border (2px), progress bar fill. Reserve it — do not use it on secondary/muted elements.
- Sidebar accordion: controlled (open section = whichever section contains the active content). Never open all sections by default on deep courses.
- XP / streak / badge toasts: slide-in from bottom-right, auto-dismiss 3s, NEVER block lesson interaction. Use `z-index` below any sticky header or AI panel.
- AI credit gate: when AI credits are exhausted, the co-pilot button should show a muted state with a tooltip ("Hết credit tuần này — nạp thêm") and a cross-link to the subscription page, NOT a blocking modal mid-lesson.
- Mobile: bottom tab bar for Course / Outline / Notes / AI. Content = full-width single column. No sidebar at all on mobile; the outline becomes a full-screen drawer.
- Dark mode: keep the code editor in a dark-by-default surface regardless of the page theme toggle (editors are nearly always expected dark). Use `data-theme` scoping to prevent flash.

---

### Sources

- [Coursera Note-Taking Blog — unified note-taking experience](https://blog.coursera.org/ready-for-retention-presenting-a-unified-note-taking-experience/)
- [Coursera — updates to learning experience](https://blog.coursera.org/updates-to-your-learning-experience-on-coursera)
- [Udemy — How to Use the Course Player](https://support.udemy.com/hc/en-us/articles/229603648-How-to-Use-The-Course-Player-and-Start-Your-Course)
- [Udemy — New Course Experience FAQ](https://support.udemy.com/hc/en-us/articles/34345830524183-Udemy-s-New-Course-Experience-Frequently-Asked-Questions)
- [Udemy Business — Course Player](https://business-support.udemy.com/hc/en-us/articles/360024140354-How-to-Use-the-Course-Player-and-Start-Your-Course)
- [Udemy — Mark Lectures as Complete](https://support.udemy.com/hc/en-us/articles/229607188-How-to-Mark-or-Unmark-Lectures-as-Complete-on-a-Browser)
- [Khan Academy 2025 Updates for Teachers](https://blog.khanacademy.org/2025-khan-academy-updates-every-teacher-should-know/)
- [Khan Academy UI Showcase (ScreensDesign)](https://screensdesign.com/showcase/khan-academy)
- [Khanmigo AI tutor — learners](https://www.khanmigo.ai/learners)
- [Brilliant UI Breakdown (ScreensDesign)](https://screensdesign.com/showcase/brilliant-learn-by-doing)
- [Brilliant x ustwo case study](https://ustwo.com/work/brilliant/)
- [Codecademy Learning Environment Updates](https://help.codecademy.com/hc/en-us/articles/1260803449210-Updates-to-our-Learning-Environment)
- [Codecademy Tools within the Learning Environment](https://help.codecademy.com/hc/en-us/articles/23368252603163-Tools-within-the-Learning-Environment)
- [The Basics of Codecademy — 3-panel description (Medium)](https://medium.com/@_dianapham/the-basics-of-learning-to-code-codecademy-50edabf1a96f)
- [Thinkific Course Player](https://support.thinkific.com/hc/en-us/articles/360030372514-The-Thinkific-Course-Player)
- [OpenCraft — Designing Better Open edX Themes](https://opencraft.com/designing-better-open-edx-themes/)
- [edX Accessibility Best Practices](https://edx.readthedocs.io/projects/edx-partner-course-staff/en/latest/accessibility/best_practices_course_content_dev.html)
- [CFI Course Player Update March 2025](https://help.corporatefinanceinstitute.com/article/1237-course-player-update-march-2025)
- [LeetCode Dynamic Layout vs Split View discussion](https://leetcode.com/discuss/interview-question/4770646/Leetcode-UI:-Dynamic-Layout-vs-Split-View-mode)
- [UXPin — Optimal Line Length for Readability](https://www.uxpin.com/studio/blog/optimal-line-length-for-readability/)
- [LearnUI — Font Size Guidelines](https://www.learnui.design/blog/mobile-desktop-website-font-size-guidelines.html)
- [Pinlearn — UX Best Practices for eLearning](https://pinlearn.com/ux-best-practices-for-e-learning-platforms/)
- [Viartisan — eLearning UI/UX Design Guide 2025](https://viartisan.com/2025/05/27/elearning-ui-ux-design/)
- [FRAM Creative — UI/UX Trends for eLearning](https://framcreative.com/insights/latest-trends-best-practices-and-top-experiences-in-ui-ux-design-for-e-learning)
- [Duolingo UI 2025 changes](https://duolingoguides.com/ui-change-that-duolingo-users-want/)
- [Duolingo UI screens (Banani)](https://www.banani.co/references/apps/duolingo)
- [eLearning Industry — AI Features Every Platform Needs 2025](https://elearningindustry.com/top-ai-features-every-elearning-platform-needs)
- [eLearning Industry — Navigation Styles Guide](https://elearningindustry.com/top-6-elearning-course-navigation-styles)
- [Stylokit — Top 10 Course Platform Designs 2025](https://stylokit.com/blog/top-10-course-platform-designs-for-2025)
