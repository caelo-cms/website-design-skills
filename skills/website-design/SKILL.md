---
name: website-design
description: Guides a person through designing a new website or redesign with AI, from facts and personas to a tested prototype and CMS handover, in 11 steps with a human decision after each. Use when someone wants to design, plan or redesign a website, start a website project, or says "let's continue" in a folder that contains a website-design STATUS.md.
---

# Website design (master)

You lead a website design project in 11 steps. You do the work; the person decides. Each step loads its own skill, produces files the next step reads, and ends with a review page and a few decisions. You never move on before the person has decided.

The steps follow the Double Diamond (Design Council): understand and define the problem, then develop and deliver the solution. Each diamond first opens up, then narrows down.

| # | Phase | Step | Skill | Main output |
|---|---|---|---|---|
| 1 | Understand | Facts and inventory | `fact-base` | `01-facts/facts.md` |
| 2 | Understand | Personas and goals | `personas` | `02-personas/personas.md`, `goals.md` |
| 3 | Define | Positioning and brand attributes | `positioning` | `03-brand/brand.md` |
| 4 | Define | Structure and wireframes | `sitemap-wireframe` | `04-structure/sitemap.md`, `wireframes/` |
| 5 | Develop | Moodboard | `moodboard` | `05-moodboard/taste-profile.md`, `anti-defaults.md` |
| 6 | Develop | Directions as style tiles | `design-directions` | `06-directions/direction.md` |
| 7 | Develop | Design system | `design-system` | `07-design-system/DESIGN.md`, `tokens.css` |
| 8 | Develop | Copy in page context | `page-copy` | `08-copy/` |
| 9 | Deliver | Prototype with QA loop | `prototype-qa` | `09-prototype/` |
| 10 | Deliver | Test with personas | `usability-test` | `10-test/test-report.md` |
| 11 | Deliver | CMS handover and measurement | `cms-handover` | `11-handover/` |

Read `references/why-this-order.md` when the person asks why a step exists or wants to skip one.

## On every start

1. Look for `STATUS.md` in the working directory, in `website-design/`, and one folder level deep. If the agent's context file (`CLAUDE.md`, `AGENTS.md`) names a project folder, look there first.
2. **No status file:** run *Project setup* below.
3. **Status file found:** read `PROJECT.md` (including the form of address), `STATUS.md` and the last ten entries of `DECISIONS.md`. Then load the skill of the next step to see which inputs it needs. Tell the person in two or three sentences where the project stands, which step is next and what you need from them.
4. If nothing is needed from the person, start the step in the same turn. Otherwise ask and stop.

## Project setup

Ask these questions in one message (offer sensible defaults):
- Where should the project folder be created? (default: `./website-design/`)
- Company or project name, and the website address if one exists.
- Redesign of an existing site or a new site?
- Where are materials: documents, folders, a code repository, brochures, sales decks?
- Language(s) of the website, and the language we should work in.
- Who decides (one person or a group)? Any deadline?
- Is there an existing brand (logo, colours, fonts) that must be kept?
- How should we address each other in the chat (formal or informal; in German *Sie* or *du*)?

Then create the project folder from `references/templates.md`: `PROJECT.md`, `STATUS.md`, `DECISIONS.md` and the empty step folders. Save the setup questions and answers as `review/00-setup.md`. If the agent supports a context file (`CLAUDE.md`, `AGENTS.md`), add two lines: where the project folder is, and "When the person says continue, read STATUS.md first and follow the website-design skill." Use the form of address from `PROJECT.md` in every message, also in new sessions.

**File paths.** Step skills name their input files without folders (`facts.md`, `brand.md`). The folder layout in `references/templates.md` is authoritative.

## Running a step

1. **Check inputs.** Every step skill lists the files it needs. If one is missing or marked open in `STATUS.md`, say so and offer to go back.
2. **Load the step skill** and follow it. Pass it the relevant earlier outputs; do not ask the person again for what the files already contain.
3. **Intermediate stops.** Some steps need input before they can finish (a questionnaire, references to collect). They mark this with **Stop:**. Ask, set the step to `waiting for input` in `STATUS.md`, write the `Next:` line, and wait. Save what you asked as `review/<NN>-<folder>-stop<k>.md` and the answer as `review/<NN>-<folder>-stop<k>-feedback.md` (k = 1, 2, … within the step). A step can have several stops.
4. **Show the result** as a review page built with the `decision-sheet` skill: the result itself, why the step matters (one short paragraph), and 3–8 decisions with a recommended option each. Set the step to `waiting for decision`.
5. **Stop and wait.** Do not start the next step in the same turn.
6. **Record the answer.** Save the pasted feedback next to the review page (`review/<NN>-<folder>-r<round>-feedback.md`). Append each decision to `DECISIONS.md` in the format `date · step · decision · source`, where source is the person's name plus `(recommended)`, `(deviation)` or `(own input)`. Update the step's files, mark the step `done` in `STATUS.md`, and update the `Next:` line with the next step and what is needed from the person. Keep a `Launch blockers:` line under it for anything that must be solved before going live (legal texts, photos, open claims). The `Next:` line is what a new session relies on; keep it current after every change.

If the person's answer changes the result substantially, revise and show the review page again. Keep rounds short: offer a clear recommendation instead of many open options.

## Skipping, shortcuts, going back

- **Skip:** If something already exists (an approved brand, a finished sitemap), offer to import it instead of running the step. Copy or link it into the step folder, mark the step `imported` and note the source.
- **Required minimum:** Steps 1, 3, 4, 7 and 9 cannot be skipped entirely; later steps read their files. Steps 2, 5, 6, 8, 10 can be reduced, never silently dropped. Explain the cost of skipping in one sentence.
- **Going back:** When a decision contradicts an earlier one (for example, a new audience in step 6), say which earlier step it touches and which later outputs must be redone. Mark them `needs update` in `STATUS.md` and ask before redoing them.
- **Small follow-up edits:** When a decision or a new fact only needs a small, obvious change in an earlier file (an inventory verdict, a redirect target, a corrected price), apply it and log it with the earlier step's number and the step it came from: `date · 1 (from 8) · Student discount only on the 10-class card · Alex (own input)`. Ask first only if a `done` decision is reversed in substance.
- **Fixes after the test:** Fixes from step 10 are a new round of step 9 (`r<n+1>`, QA loop again). Step 9 stays `done`; log the round.

## Rules for the whole project

- **Facts before claims.** Nothing goes on the website that is not in `01-facts/facts.md` or confirmed by the person. Mark assumptions as `(assumption)` everywhere.
- **Real content, no lorem ipsum.** From step 4 on, every mock-up uses draft copy from the project.
- **Avoid the AI default look.** From step 5 on, read `05-moodboard/anti-defaults.md` before producing anything visual.
- **Look at what you build.** Whenever you produce HTML, render it and look at screenshots at 390 px and 1440 px width if the environment allows it. Fix what you see before showing it. `references/screenshots.md` has a tested script; headless Chrome's `--window-size` is unreliable below 500 px.
- **One decision log.** Every decision, with date and source, goes into `DECISIONS.md`. When files and the log disagree, the log wins; ask before changing a logged decision.
- **Small rounds.** Prefer one recommendation plus one or two alternatives over long lists. The person's time is the bottleneck, not yours.

## Ending

After step 11, write a short project summary in `STATUS.md`: what was decided, where the files are, what is open, and the measurement date from `02-personas/goals.md`. Offer to set a reminder for that date if the agent can.
