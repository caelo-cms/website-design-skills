---
name: cms-handover
description: Step 11 of website-design. Moves the approved prototype into a CMS as a system (theme tokens, reusable modules or blocks with named fields, page templates, redirects, SEO basics), checks quality before going live and sets up measurement against the goals. Works with any CMS; includes a guide for Caelo CMS. Use when a website design or prototype should be built in a CMS, migrated or launched.
---

# CMS handover and measurement

**Why:** The prototype is thrown away; the system stays. A site rebuilt page by page drifts apart with every edit. A site built from tokens, modules and templates keeps its look when editors and AI change it later. Without measurement against the goals from step 2, nothing is learned after launch.

**Needs:** prototype, `tokens.css`, `DESIGN.md`, `components.html`, `08-copy/`, `sitemap.md` (incl. redirects), `goals.md`, `baseline.md`, QA and test reports.
**Produces:** `11-handover/handover.md`, `11-handover/measurement.md`, the site in the CMS.

Ask which CMS is used if `PROJECT.md` does not say. For Caelo, follow `references/caelo.md` in addition to this file.

## 1. Map the prototype to the CMS

Write `handover.md` before building:
- **Theme:** which tokens become theme settings or variables. Prefer the CMS's own theme system over a big custom stylesheet.
- **Modules / blocks / components:** one per building block on `components.html`. For each, the named fields an editor fills in (headline, text, button label, button link, image, alt text) instead of one free HTML field. Named fields keep the design intact and let AI edit content safely.
- **Templates:** one per page type from step 4, listing which modules in which order.
- **Content:** which copy goes where; shared content (navigation, footer, contact details) stored once.
- **Redirects:** the list from `sitemap.md`.
- **SEO basics:** titles, meta descriptions, canonical URLs, sitemap.xml, structured data where it fits.

## 2. Build

Build theme first, then modules, then templates, then pages. After each module, compare a screenshot of the CMS rendering with the prototype at 390 and 1440 px. Differences are fixed in the module, not patched on the page.

## 3. Check before going live

Run the QA checklist from step 9 on the CMS version (staging), plus: all redirects work, forms deliver, analytics and consent work, no staging URLs in links, robots and sitemap correct. A person makes the final go-live decision.

## 4. Measurement

Write `measurement.md`: each goal from `goals.md` with metric, where it is measured, baseline, target, first measurement date (typically 4–8 weeks and 6 months after launch). Note what will be compared and who looks at it. Add a short backlog of ideas that came up during the project and were parked.

## Review

Show the CMS staging pages next to the prototype and the measurement plan. Typical decisions: go-live date, open findings, measurement dates.

**Done when** the site is live (decided and clicked by a person) and `measurement.md` exists. While the plan is written but the build or launch is still pending, the step is `waiting for input` with a note on what is open.
