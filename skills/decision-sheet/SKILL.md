---
name: decision-sheet
description: Builds a single-file HTML review page that shows a work result and asks for decisions with radio options, a notes field and a "Copy feedback" button whose text the person pastes back into the chat. Use at the end of every website-design step, or whenever a person has to choose between options.
---

# Decision sheet

A review page has two parts: the result to look at, and the decisions to make. The person fills in the form, clicks **Copy feedback** and pastes the text back into the chat. You then log every decision.

Start from `assets/decision-sheet.html`. Fill every `{{…}}` placeholder; translate the labels and the `UI` strings in the script into the working language (keep `lang` correct). Save the page as `review/<NN>-<folder>-r<round>.html`, using the step folder's name (for example `review/05-moodboard-r1.html`, `review/04-structure-r2.html`). If the environment can publish HTML pages (an artifact, a preview server), publish it there; otherwise give the file path and tell the person to open it in a browser. Do not publish test or demo projects to shared galleries.

The page is one file, but it may link to other project files (wireframes, tiles, prototype pages) and embed screenshots from `review/screens/`. Use the `.shots` block for mobile and desktop screenshots side by side; long pages are cut at the first screen and link to the full image. When a step changes files between rounds, keep each round's files (for example `wireframes/r1/`, `wireframes/r2/`) so an older review page still shows what was decided then.

## Part 1: the result

- Open with one sentence on what this step produced and one short paragraph on why the step matters.
- Then the result itself, shown the way it will be used: wireframes as wireframes, copy inside a page mock-up, colours as swatches with contrast ratios. Never a wall of text when a picture or a mock-up says it better.
- Mark anything that is an assumption with `(assumption)`.
- Use the project's own design once step 7 exists: map the template variables to the project tokens as the comment in the template shows, and remove the dark-mode block if the project has no dark mode. Before step 7, keep the neutral template styling.

## Part 2: the decisions

- 3–8 questions. Fewer is better. Ask only what changes the next step. Ratings of many items (references, elements) are not questions each: group them, or use one fieldset per item with a reason field.
- Each question: a short title, one line of context if needed, 2–4 options.
- For decisions, mark exactly one option as recommended (`data-rec` and the badge before the text) and put it first. Say why in a few words. Factual questions ("Is there a changing room?") get no recommendation, or a free answer field.
- Building blocks in the template: a reason field per question (`input.reason`, appended to the answer), checkboxes with `data-max` for "pick three" word tests, and `input.answer` for a free answer. The copied text then shows `[recommended]` or `[deviation]` behind each answer, which goes into the decision log as the source note.
- Options are concrete ("Navigation with 5 top items: Product, Pricing, …"), never "Option A".
- One free notes field at the end.
- Pre-select nothing. The copied text marks unanswered questions as `(open)` or its translation.
- The copied text is always visible under the button, so the person sees what they paste.

## Writing rules

- Plain language, short sentences, the person's working language.
- Explain terms of the trade the first time they appear ("style tile: colours, fonts and elements without a page layout").
- No hype, no filler. Every sentence either shows the result, explains why, or asks.

## After the person answers

1. Save the pasted text as `review/<NN>-<folder>-r<round>-feedback.md` (answers to an intermediate **Stop:** go to `review/<NN>-<folder>-stop<k>-feedback.md`). Treat `(open)` answers (in any language) as undecided; ask about them only if the next step needs them.
2. Append each decision to `DECISIONS.md`: `date · step · decision · source`, with the source as the person's name plus `(recommended)`, `(deviation)` or `(own input)` for notes. Corrections of your own mistakes are logged with the source `agent (correction)`.
3. If notes ask for changes, revise and create round `r2`. Otherwise mark the step done.
