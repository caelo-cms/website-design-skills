---
name: page-copy
description: Step 8 of website-design. Writes the website copy page by page in the voice from brand.md, always shown inside a page mock-up instead of as loose sentences, checks every claim against the fact base (fact gate) and removes typical AI writing patterns. Use when writing or reviewing website copy, headlines, CTAs or page texts.
---

# Copy in page context

**Why:** A sentence reads differently in a layout than in a list: length, rhythm and what stands next to it change its effect. So copy is always shown in place. And AI copy has two typical failures: invented facts (numbers, customers, quotes, features) and recognisable AI patterns that make readers stop trusting the text. The fact gate and the pattern check address both.

**Needs:** `facts.md`, `personas.md`, `brand.md` (voice), `sitemap.md` with message order, wireframes, `tokens.css`.
**Produces:** `08-copy/<page>.md` per page, `08-copy/claims.md`.

## 1. Write

Per page, follow the message order from `sitemap.md`. For each section: headline, text, call to action, any labels, alt texts and meta title/description.
- Write for the primary persona of the page; answer their question at that point.
- Use the persona's words from `personas.md` and the terms from `facts.md`.
- Concrete beats general: describe what happens, with numbers and examples from the fact base.
- Headlines say something on their own; buttons say what happens ("Book a 30-minute demo", not "Learn more").

## 2. Fact gate

Every factual claim (numbers, features, customers, awards, comparisons, guarantees) gets a reference to `facts.md`. Collect them in `claims.md`: claim, page, source. Claims without a source are either removed, rephrased into something provable, or listed as an open question for the person. No invented testimonials, ratings, customer logos or usage numbers, ever.

Check derived wording, not just numbers: "from", "only", "always", "all", "cheapest", "most" and comparisons must be true against every option in `facts.md`. "From €16 per class" is false if another plan is cheaper, even when 160/10 = 16 is correct.

## 3. Pattern check

Check every text against `references/ai-writing-patterns.md` and rewrite what matches. Then read it once more with the question: *Who would write this, at this point on this page?* If the answer is "a template", rewrite.

If a humanizer skill for the language is installed, run it on the final copy as well.

## 4. Show in context

Put the copy into page mock-ups built the same way as the step-9 prototype (same tokens, same `components.css`, ideally the same build script), so the person reads it where it will stand and step 9 does not build everything twice. Later copy changes go into `08-copy/` first, then the pages are rebuilt. Mark open claims visibly. For headlines with real alternatives, show up to three variants in the same spot.

## Review

Per page: the mock-up, the open claims, headline variants if any. Typical decisions: headline per page, CTA wording, open claims (keep with source, rephrase, drop), tone adjustments.

**Done when** all key pages have approved copy and `claims.md` has no open items.
