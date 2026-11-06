# slicefocus-web

Public showcase site for **SliceFocus**: a day planner on a 24-hour clock, with
a Pomodoro timer that runs its rounds by itself on iPhone and Mac.

Served via GitHub Pages at <https://slicefocus.app>.

This is a **showcase**, not a web version of the app — its only job is to turn
post/link traffic into App Store interest. A single static page, no build step:
edit, commit, push; GitHub Pages redeploys automatically (~1 minute).

## Files

| File | Purpose |
|------|---------|
| `index.html` | The page |
| `styles.css` | Design tokens + layout |
| `hero.webm` / `hero.mp4` / `hero-poster.{webp,jpg}` | Hero loop (about 33 s, silent, every width since #37): a tour of the Mac and iPhone apps with a ring at every tap: plan a block on the 24-hour canvas, start it, the Pomodoro hands over to the break by itself (time-compressed), the same session on the iPhone beside the Mac, a Live Activity on an iPhone lock screen (a separate clip, not that session), Focus Shield, Manage Categories, calendar export. The poster is the still at every width and the reduced-motion / Save-Data view. Built by `tool/videos/hero/compose.sh` in SliceFocusFE from real takes; brief: `slicefocus-docs/plans/hero-video-brief.md` (section 5). Played by the inline script at the end of `index.html`, which also plays the feature clips while on screen; both obey `prefers-reduced-motion` and Save-Data; the hero loads no video bytes until it is on screen. |
| `study-day/`, `time-blocking/`, `pomodoro/`, `planned-vs-actual/` | One plain page per moment of need (#51), in the layout of the Focus Shield guide (`focus-shield/`). The wording comes from `slicefocus-docs/plans/moment-pages.md`: change it there first. Each page's App Store links carry their own campaign label (`study_day`, `time_blocking`, `pomodoro`, `planned_actual`). Every page's footer lists these four and the Focus Shield guide; keep that row the same on all pages. |
| `screen-planned-actual.png` | Picture on `/planned-vs-actual/`: App Store screenshot 4 (`slicefocus-docs/screenshots/ios/6.9/04-actual-vs-planned.png`) resized to 760 px wide |
| `og.png` / `.svg` | 1200×630 link-preview (Open Graph) card |
| `download-on-the-app-store.svg` | Official Apple badge |
| `icon.svg` / `apple-touch-icon.png` | Favicons |
| `CNAME` | Custom domain (`slicefocus.app`) |
| `.nojekyll` | Serve files as-is (skip Jekyll) |

## Before going public

- Replace the App Store `href` placeholders in `index.html` with the live
  `https://apps.apple.com/app/idXXXXXXXXXX` listing URL.
- Point DNS for `slicefocus.app` at GitHub Pages, then set the custom domain in
  repo **Settings → Pages**.

## Design

Visual language follows
[ADR-042 — Minimal & sincere marketing design language](https://github.com/AnunnakiCosmoCrew/slicefocus-docs/blob/main/adr/042-minimal-sincere-marketing-design-language.md):
warm cream canvas, near-black editorial serif headlines, a single clay accent,
a narrow centered reading column, and the product as the only saturation on the
page. Built for [#312](https://github.com/AnunnakiCosmoCrew/SliceFocus/issues/312).
