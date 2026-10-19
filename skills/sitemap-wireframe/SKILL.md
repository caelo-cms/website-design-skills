---
name: sitemap-wireframe
description: Step 4 of website-design. Builds the page tree, navigation and URL scheme, defines for each page the question it answers and the order of its messages, and produces grey low-fidelity HTML wireframes with real draft copy for the key page types. Use when planning information architecture, sitemap, navigation, page structure or wireframes, before any visual design.
---

# Structure and wireframes

**Why:** Content comes before design. Decide what goes where before deciding how it looks. Wireframes in plain grey invite criticism of structure; as soon as something looks finished, people only comment on colours. AI site builders that produce good results (Relume, Google Stitch) also go sitemap → wireframe → style, for the same reason.

**Needs:** `01-facts/facts.md`, `01-facts/inventory.md` (redesigns), `02-personas/personas.md`, `03-brand/brand.md`.
**Produces:** `04-structure/sitemap.md` (page tree, navigation, URL rules, redirects, message order), `04-structure/wireframes/r<round>/*.html`.

This step has two parts with a review each, because structure and wireframes are too much for one round: part 1 settles the page tree, part 2 shows the wireframes.

## 1. Page tree

Start from the personas' questions, not from the old site or the org chart. Each page answers one main question for one main persona.

In `sitemap.md`, for each page: URL, title, main question, primary persona, primary action, status (launch / later). Then:
- **Navigation:** top-level items (aim for 5–7), what goes in the footer, whether a mega menu is needed.
- **URL rules:** language prefix, trailing slash or not, lower case, words not IDs.
- **Redirects:** old URL → new URL for every page marked in the inventory.
- **Launch scope:** the smallest set of pages that answers the primary persona's questions. Empty sections ("Blog – coming soon") stay out.

Keep it as small as the offer allows. Every page has to be written, designed and maintained.

**Review, part 1** (`review/04-structure-r1.html`): page tree, navigation, URL rules, redirects, launch scope. **Stop:** wait for the decisions before building wireframes.

## 2. Message order per key page

Write it into `sitemap.md`, one block per page. For the home page and each page type (product, pricing, about, contact, article, …): list the sections top to bottom. For each section: the visitor's question at that point, the answer in one line, the proof from `facts.md`, and what leads to the next section. The first screen states the promise and the primary action.

## 3. Wireframes

Build one HTML wireframe per key page type, mobile first, also checked at desktop width. In the first wireframe round show at most four: the home page and the three most important page types. Further types follow in the next round. Save each round in its own folder (`wireframes/r2/`, …) and share one stylesheet.
- Greys only, one system font, boxes with a cross for images, no brand colours, no icon sets, no shadows.
- **Real draft copy** from `brand.md` and `facts.md`, never lorem ipsum. Headlines may still be rough; mark them `draft`.
- Real lengths: if a list will have 12 items, show 12.
- Label each section with the question it answers, in small grey text above it.
- Render and look at each wireframe at 390 px and 1440 px before showing it.

## Review, part 2

Show the message order and the wireframes as screenshots side by side (mobile and desktop), each linked to its HTML file. Typical decisions: section order per page, page types that are missing or redundant, what the first screen must contain.

**Done when** page tree, navigation, URL rules, redirects and the section order of the key pages are decided. Copy is refined in step 8; layout details may change in step 9.
