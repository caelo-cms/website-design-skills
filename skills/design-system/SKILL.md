---
name: design-system
description: Step 7 of website-design. Turns the chosen direction into a design system that people, models and tools can read: a DESIGN.md with guiding idea and rules, a tokens.css with colour roles (measured contrast), type scale (measured font weight in KB), a fixed spacing scale, shapes and motion, and a components page. Use when a website needs design tokens, a style guide, a design system or a theme.
---

# Design system

**Why:** Decisions become rules. A model that has to guess spacing or colours drifts back to its defaults; a model that reads tokens and rules does not. The same tokens later move one-to-one into the CMS theme, so the site keeps its look when people and AI edit it.

**Needs:** `direction.md`, the tiles, `anti-defaults.md`, wireframes.
**Produces:** `07-design-system/DESIGN.md`, `07-design-system/tokens.css`, `07-design-system/components.css`, `07-design-system/components.html`, `07-design-system/fonts/`.

## 1. Tokens

Write `tokens.css` as CSS custom properties on `:root`, grouped and commented. Use role names, not colour names (`--color-action`, not `--orange`).

- **Colour:** surfaces, text (primary, secondary), lines, link, action (buttons), action hover, focus, states (success, warning, error), plus any brand colours that are only for graphics. For every text/background pair, measure the contrast ratio and write it in a comment. Text needs 4.5:1, large text and UI parts 3:1 (WCAG 2.2 AA). Adjust shades until they pass.
- **Dark mode** only if decided; then the same roles with dark values, measured again.
- **Type:** font families with fallbacks, a type scale (use `clamp()` for headlines), line heights, weights, letter spacing for labels. Download the exact font files you will serve into `fonts/` and measure them; note the KB per file. Extra axes (optical size) and italics can double the size of an estimate. Prefer variable fonts and subsets. Self-host the fonts instead of loading them from a font CDN (privacy law, for example in the EU, and one less connection). Note the licence.
- **Spacing:** one scale based on 4 or 8 px, plus named distances for repeated relations (label → headline, headline → lead, lead → buttons, section padding, card padding). Named distances stop the "a bit more space here" drift.
- **Shape:** radii, borders, shadows, by role (button, card, input).
- **Motion:** durations, easing, and what animates at all. Always a `prefers-reduced-motion` rule.
- **Layout:** max content width, breakpoints or container sizes, grid columns.

## 2. DESIGN.md

The readable contract, for people and for any AI tool working on the site. Keep it to two or three pages:
- **Idea:** the one-sentence guiding idea and where it comes from.
- **Roles:** what each colour is for and what it is never used for ("Action colour only on buttons that commit something").
- **Type rules:** which style for what, maximum line length, how headlines are written.
- **Spacing rules:** the scale and the named distances.
- **Components:** list with when to use each.
- **Imagery:** what kind, how cropped, what to avoid.
- **Don'ts:** the project's anti-defaults, condensed.
- **Accessibility and performance budget:** contrast minimums, focus style, touch target at least 24 × 24 px, page weight and LCP targets (for example home page under 1 MB, LCP under 2.5 s on mobile).

Keep the format plain Markdown so tools that read a DESIGN.md (for example Google Stitch) or a context file (CLAUDE.md, AGENTS.md) can use it.

## 3. Components page

`components.html` uses only `tokens.css` and `components.css` (the component styles that the prototype in step 9 reuses) and shows every building block the wireframes need: navigation (desktop and mobile), hero variants, section header, text block, cards, lists, quote, numbers, buttons and links in all states (hover, focus, disabled), form fields with error state, table, footer. Real copy throughout. Render at 390 and 1440 px and check: no element uses a value that is not a token (unless it is listed as an exception at the top of `components.css`, such as an icon size), focus is visible, nothing overflows.

## Review

Show the components page with a short summary of the rules. Typical decisions: final colours and their roles, type scale, spacing (people often ask for more space; settle it here with named distances), radius and shadow, dark mode yes/no, performance budget.

**Done when** tokens and DESIGN.md are confirmed. From now on, every visual change goes through the tokens or is logged as an exception.
