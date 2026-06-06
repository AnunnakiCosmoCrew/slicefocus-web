# slicefocus-web

Public showcase site for **SliceFocus** — a visual day planner on a 24-hour
radial clock with zero-touch auto-advance between focus blocks.

Served via GitHub Pages at <https://slicefocus.app>.

This is a **showcase**, not a web version of the app — its only job is to turn
post/link traffic into App Store interest. A single static page, no build step:
edit, commit, push; GitHub Pages redeploys automatically (~1 minute).

## Files

| File | Purpose |
|------|---------|
| `index.html` | The page |
| `styles.css` | Design tokens + layout |
| `hero-poster.png` / `.svg` | **Placeholder** for the hero video slot. Replace the `<video>` sources with the [#311](https://github.com/AnunnakiCosmoCrew/SliceFocus/issues/311) clip (`hero.mp4` / `hero.webm`); the poster shows until then. |
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
