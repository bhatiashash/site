# Shash Bhatia: personal site

Single-file static site. No framework, no build step: open `index.html` or
serve the folder with any static server.

Design: a full-screen, four-scene portfolio with Newsreader and Geist Mono
type, canvas project visualizations, and an electric #002FA7 accent.
Scenes cover an introduction, FirstFocus, Monitor recruitment, and The one-bit gate.

Use the numbered buttons, left/right arrow keys, or keys 1–4 to switch scenes.
Direct links use `#intro`, `#firstfocus`, `#monitors`, and `#onebit`.
Reduced-motion preferences show static scenes instead of animations.

Google Fonts loads the typefaces; local serif and monospace fallbacks keep the
site usable offline. There are no JavaScript dependencies or build commands.

## Content access

On phones, each scene's takeaway appears at the end of its scrollable content.
It uses the same caption text as the fixed desktop takeaway.

With JavaScript disabled, the page shows static summaries for all four scenes,
project links, and the existing GitHub and LinkedIn contacts. Keep these summaries
aligned with the interactive copy when editing project descriptions or results.
The fallback does not reproduce the canvas animations.

## One-bit audit count

The verified total is **280 audited evaluation runs**, not 280 total games.
The earlier report covered 220 gated evaluation runs: 40 in batch 1 and 60 for
each of the three model batches in the first extension. The GPT-5 mini second
extension added 60 gated runs. Development pilots, smoke tests, and the seed 119
rerun are recorded separately from that evaluation total.

Primary evidence in the experiment repository:

- [Earlier report, section 3](https://github.com/bhatiashash/one-bit-collusion-gate/blob/9c96b3fd69225649264dc25939fa3fbd3368805c/report.md#3-checks-before-results) records 220 of 220 gated evaluation runs.
- [Updated report, section 3 and Appendix C](https://github.com/bhatiashash/one-bit-collusion-gate/blob/384e11c49b160a3367943e357a4fa269a19caabe/report.md#3-checks-before-results) records 280 of 280 and explains the additional GPT-5 mini batch.
- [Evaluation records](https://github.com/bhatiashash/one-bit-collusion-gate/blob/384e11c49b160a3367943e357a4fa269a19caabe/data/one-bit-extension-summary-fields.json) contain the additional model's per-arm, per-seed results.

The audit checks enforcement of the communication budget. It does not establish
an advantage over silence; both displayed uncertainty intervals still cross zero.

## Manual acceptance checks

There is no typechecker, build command, or automated test suite. Validate the
rendered page rather than scene-engine internals:

- Visit all four scenes at 320, 390, 640, and 641 CSS pixels wide, including a
  568-pixel-high viewport. Scroll to each takeaway and check that it does not
  cover navigation, project links, or contacts. Check the desktop layout at
  1280 by 800 as well.
- Disable JavaScript and check phone and desktop layouts. Read all four summaries,
  reach every project and contact link, and confirm the page scrolls normally.
- Enable JavaScript and check that fallback summaries do not appear alongside
  the interactive scenes. Exercise numbered buttons, arrow keys, keys 1–4,
  direct scene links, and keyboard access to links.
- Enable reduced motion and confirm the visualizations stay static while scene
  conclusions and links remain readable.
- Compare the audit wording in desktop captions, mobile takeaways, project facts,
  and the static summary against the primary evidence above.

Verified on November 3, 2026 with temporary browser checks, not a repository test
harness. All 15 viewport and behavior groups passed, including native JavaScript
disablement and reduced motion. The final run reported no new JavaScript errors.

Repeated checks also reproduced an intermittent one-bit animation error,
`Cannot read properties of undefined (reading 'x')`, on both the original commit
`446e946` and the working version. That pre-existing timing issue is outside these
content-access fixes and remains unchanged.

## Publish with GitHub Pages

Repo Settings → Pages → deploy from branch → `main`, `/ (root)` → Save.
The site goes live at `https://bhatiashash.github.io/<repo-name>/`.
