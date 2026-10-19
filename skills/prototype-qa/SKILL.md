---
name: prototype-qa
description: Step 9 of website-design. Builds a local HTML prototype from wireframes, tokens and approved copy, then runs a QA loop in which the model checks its own output: screenshots at 390 and 1440 px, anti-defaults, WCAG 2.2 basics, page weight and LCP against the budget. Use when building a website prototype or checking a built page for visual, accessibility and performance problems.
---

# Prototype with QA loop

**Why:** Without looking at the result, a model works blind and reports success on pages that are broken at phone width. Accessibility and speed are cheap to get right while building and expensive to add after launch. The prototype is also where people first experience the site as a whole.

**Needs:** wireframes, `tokens.css`, `components.html`, `DESIGN.md`, `08-copy/`, `anti-defaults.md`, `sitemap.md`.
**Produces:** `09-prototype/` (pages, shared CSS/JS, assets), `09-prototype/qa-report.html`.

## 1. Build

- Plain HTML, one shared stylesheet that imports `tokens.css`, as little JavaScript as possible. The prototype is a reference for the CMS, not the final code.
- Navigation and footer from one source (an include or a build script), so they are identical on every page.
- Build the launch pages from `sitemap.md`; link pages that are not built yet to a placeholder that says so.
- Every value comes from a token. When you need a value that does not exist, stop and decide: add a token (and log it) or use an existing one.
- Real images where available; otherwise neutral placeholders with the intended motif written on them. Never stock photos that suggest real customers or employees.

## 2. QA loop

Run it for every page after building and after every round of changes. Use `references/qa-checklist.md`.

1. **Screenshots** at 390 px and 1440 px (full page), with a browser tool, Playwright or whatever the environment offers. Look at them. Fix overflow, overlaps, cut-off text, broken spacing.
2. **Anti-defaults:** compare against `anti-defaults.md` and `DESIGN.md` don'ts.
3. **Accessibility:** WCAG 2.2 AA basics from the checklist. Run an automatic checker (axe, Lighthouse) if available; automatic checks find only part of the problems, so also check keyboard use and focus by hand.
4. **Performance:** page weight, number of requests, font files, image sizes, LCP on a mobile profile if a tool is available. Compare with the budget in `DESIGN.md`.
5. **Content:** no lorem ipsum, no `draft` markers left, every claim in `claims.md`.

Fix, re-run, and only then show the result. Do not loop endlessly: after two rounds without progress on an item, list it as open in the report.

## 3. Report

`qa-report.html`: per page the screenshots (mobile and desktop), the checklist results, open items with severity (blocks launch / should fix / nice to have).

## Review

Link the prototype and the report. Typical decisions: open findings (fix now or later), pages that need another design round, readiness for the test in step 10.

**Done when** no open item blocks launch and the person approved the prototype for testing.
