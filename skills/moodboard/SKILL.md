---
name: moodboard
description: Step 5 of website-design. Builds a moodboard in three stages: mood words with opposite poles, about 24 real references (websites and also print, photography, architecture, products) rated keep/partly/avoid with a reason, then a taste profile and an anti-defaults list of things the AI must not do. Use when a website or brand needs a visual feel, inspiration, references, a moodboard or taste profile.
---

# Moodboard

**Why:** People are bad at describing taste and good at judging examples. A rated set of references turns "I'll know it when I see it" into a profile the AI can follow. References must be real: AI-generated images only remix what is already common, real references bring something new. And without explicit don'ts, the AI falls back to its defaults (Anthropic calls this distributional convergence), so this step also writes down what to avoid.

**Needs:** `brand.md` (attributes), `personas.md`.
**Produces:** `05-moodboard/references/`, `05-moodboard/moodboard.html`, `05-moodboard/taste-profile.md`, `05-moodboard/anti-defaults.md`.

## Stage A: words and references

1. **Mood words.** From the brand attributes, derive 4–5 mood words for the look and feel, each with an opposite pole ("airy, not empty"; "warm, not cosy"). Show them to the person first; they are the brief for collecting.
2. **Collect about 24 references** (12–16 are enough for a small business). Ask the person for their own, preferably as screenshots, photos or scans rather than links (many sites block automated captures with cookie walls or bot checks), and add your own to reach the number. Mix on purpose:
   - about half websites, of which at most a quarter direct competitors (otherwise the moodboard becomes a competitor analysis)
   - the other half from outside the web: print and editorial design, photography, architecture and interiors, products and packaging, signage, art
   - include the client's existing brand material if it must be kept

   **Stop:** send the mood words and the request for references in one message and wait (state `waiting for input`). Offer to start with your own collection if the person has none.
3. **Capture each reference** in `references/` as an image, and list them all in one table `references/README.md`: number, source URL or origin, what it shows, which mood word it relates to. Take website screenshots yourself if the environment has a browser (see `website-design/references/screenshots.md`, section on references); remove cookie banners and personal data. Replace references that cannot be captured instead of spending time on them.
4. **Contradictory moods go on separate boards.** If references pull in clearly different directions, group them into 2–3 boards instead of one mixed board. These groups often become the directions in step 6.

## Stage B: rate, then profile

5. **Rate.** `moodboard.html` is the plain board: all references in a grid with number and note. The rating form is the review page `review/05-moodboard-r1.html`: one fieldset per reference with *keep*, *partly*, *avoid* and a reason field (`input.reason`), no recommendation. The reason is the important part. The copied feedback then lists every reference with rating and reason. **Stop:** wait for the ratings.
6. **Taste profile.** Cluster the reasons, not just the ratings, into `taste-profile.md`:
   - colour (light/dark, saturation, number of colours, accent use)
   - typography (serif/sans, contrast, width, size of headlines)
   - density and whitespace
   - imagery (photography, illustration, product screens, none)
   - shape and detail (corners, lines, shadows, textures)
   - motion (none, subtle, expressive)
   Each finding with the references it is based on: "Large type, little colour (keep: 3, 7, 12; avoid: 5)". Mark interpretations `(assumption)`.
7. **Anti-defaults.** Write `anti-defaults.md` from `references/common-ai-defaults.md` plus everything rated *avoid*. Keep only what is relevant for this project and add the reason. Later steps must read this file before producing anything visual.
8. **Optional AI synthesis.** Only now, and only as a summary of the profile, you may generate images or style sketches. Each generated item names the references it draws on. It is never a source for the profile.

## Stage C: feedback with reasons

Show the taste profile and the anti-defaults on review round 2 (`review/05-moodboard-r2.html`). Ask per finding: *keep, change, drop*, never "Do you like it?". Then a word test (checkboxes, `data-max="3"`): list the brand attributes mixed with their opposite poles and ask the person (and, if possible, two or three colleagues) to pick the three words that fit the profile best. If people pick opposite poles, the profile does not match the brand; go back to the references.

## Pitfalls

- A moodboard without mood words is a collection of taste, not a brief.
- Only websites, or only competitors: the result looks like the market, not like the brand.
- Ratings without reasons: the profile becomes guesswork.
- AI images as references: they show the average, the opposite of what this step is for.

**Done when** the taste profile and the anti-defaults are confirmed and the word test points to the brand attributes.
