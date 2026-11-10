# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Public showcase site for SliceFocus (slicefocus.app): plain HTML and one stylesheet at the repo root, no build step, served by GitHub Pages. See [README.md](README.md) for the file map.

## Accessibility

Canonical text: luvita-docs ADR 0011 §5.1.

- **Surface and standard:** browser, WCAG 2.2 Level AA; semantic landmarks, a skip link, visible focus, `prefers-reduced-motion`, `prefers-color-scheme`, `lang` on `<html>`.
- **Automated check and where it runs:** `AnunnakiCosmoCrew/project-templates/actions/a11y-check` (axe-core at WCAG 2.2 AA, serious and critical violations fail) in `.github/workflows/ci.yml`, job "Accessibility check", on every PR. It serves the repo root and tests every `.html` page. Exceptions go in `.a11y-allow.json` at the repo root, each with a reason; never add one to get green.
- **Manual pass per release:** keyboard-only walk of the home page and one moment page (skip link first and lands in `main`, every control reachable with a visible ring); VoiceOver on macOS for a release that changes a main task.
- **Colour token file:** `:root` in `styles.css` (the focus ring and skip link use `--accent`, `--btn`, `--btn-fg`). Swap to the vendored `cosmocrew-web/packages/design` build when it ships (ADR 0011 §5.2).
- **Last manual pass:** 2026-11-10, keyboard only in Chrome on macOS (home and `/pomodoro/`: the skip link is the first Tab stop and moves focus to `main`; the header button, footer links and App Store badge show the focus ring). axe-core 4.14.0 at WCAG 2.2 AA found no violations on all nine pages in light and dark mode (the footer note had needed its opacity removed to reach 4.5:1). VoiceOver pass: not done yet.

Definition of Done for any UI change:

- The automated check is green in required CI.
- Text keeps 4.5:1 contrast (3:1 for large text and UI components).
- A release that changes a main task updates **Last manual pass** above, or says in the PR body under `Not verified` that the pass is still owed.
- Every new page has the skip link as the first element in `<body>` (`<a class="skip-link" href="#main">`) and `<main id="main" tabindex="-1">`.
- No hard-coded colours outside the `:root` token block in `styles.css`.
