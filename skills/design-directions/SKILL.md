---
name: design-directions
description: Step 6 of website-design. Creates three deliberately different visual directions as style tiles or element collages (colours, type, buttons, a hero fragment, a card, imagery, with real copy but no full page layout), spread along named axes, lets the person rate them against the brand attributes and merges the result into one direction. Use when a website needs visual design options, look and feel variants or a style direction.
---

# Directions as style tiles

**Why:** A moodboard is too vague to build on and a full page mock-up is too literal: people start discussing structure that was already decided in step 4. Style tiles (Samantha Warren) and element collages (Dan Mall) sit in between: they show colours, type and interface elements without a page layout, so the discussion stays on look and feel. With AI, variants cost almost nothing, so the choice is the bottleneck. This step therefore spreads the directions on purpose and gives the choice a yardstick.

**Needs:** `brand.md`, `taste-profile.md`, `anti-defaults.md`, `sitemap.md` and one wireframe (for the copy), `personas.md`.
**Produces:** `06-directions/tiles/r<round>/*.html`, `06-directions/direction.md`.

## 1. Choose the axes

Name two or three axes along which the directions differ, taken from open points in the taste profile. Examples: calm ↔ striking, dense ↔ airy, warm ↔ cool, editorial ↔ technical, flat ↔ textured. Place each direction at a different point. Three directions that only differ in accent colour are one direction.

If stage A of the moodboard produced separate boards, start from them.

## 2. Build three tiles

One self-contained HTML file per direction. Each tile shows:
- a name and one sentence on the idea behind it (from the brand, not from a trend)
- colour palette as swatches with roles (background, text, accent, action) and contrast ratio of text and buttons (WCAG AA: 4.5:1 for text)
- type: display and body face with a few sizes, real headline and paragraph from the copy drafts
- interface elements: primary and secondary button, link, input field, navigation bar, one card
- a hero fragment (not a full hero section) and one other characteristic element: a quote, a number, a list, a pricing line
- imagery: style samples or a description of photo, illustration or screen treatment
- one detail that only this brand would have (a shape from the logo, a term from the trade, a unit of measure)

Rules:
- Read `anti-defaults.md` first. Fonts only from sources with a usable licence (Google Fonts, OFL, the client's licensed fonts); note the licence and file size.
- Real copy from the project, never lorem ipsum. Sample interface text uses only facts from `facts.md`: no invented features, offers, availability or numbers.
- No full page layout, no full navigation tree, no footer.
- Render each tile at 390 px and 1440 px and look at it before showing it.

## 3. Rate

On the review page, show the three tiles side by side (or one after another on mobile). For each tile:
- **Word test:** one question per tile. The person (and if possible colleagues) pick three words (checkboxes, `data-max="3"`) from a list that mixes the brand attributes and their opposite poles. Count which side wins.
- **Element by element:** one question per element (colour, type, buttons, imagery, detail): which tile should it come from, A, B, C or none, with a reason field. That keeps the sheet at about eight questions.
- **Optional five-second test:** show a tile for five seconds to someone outside the project and ask "What kind of company is this? Which three words come to mind?"

## 4. Merge

From the ratings, write `direction.md`: the chosen elements per category, what comes from which tile and why, and what stays open for step 7. If the merge is substantial, build one combined tile and show it again in round 2. Do not run more than three rounds; if it does not converge, the problem is usually in the brand attributes, so go back to step 3.

**Done when** `direction.md` is confirmed and the word test for the combined direction points to the brand attributes.
