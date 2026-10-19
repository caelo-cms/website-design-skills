---
name: personas
description: Step 2 of website-design. Builds 2–4 personas from a short questionnaire the client fills in about their top customers, completes them with AI and marks every addition as an assumption, and sets 2–4 measurable website goals. Use when a website project needs target groups, personas, user needs or success criteria.
---

# Personas and goals

**Why:** Every later step needs a yardstick: who is this structure, this copy, this design for? Interviews or a representative panel would be ideal, but for most website projects that is too much effort. A persona picture built from what the client knows about their best customers, completed by AI, is not perfect, but good enough to justify decisions. Shared goals end taste debates before they start.

**Needs:** `01-facts/facts.md`.
**Produces:** `02-personas/personas.md`, `02-personas/goals.md`.

## 1. Questionnaire

Send the questions from `references/questionnaire.md` in one message. Tell the person: short answers are fine, bullet points are fine, ten minutes is enough. Offer to fill in a first draft from `facts.md` that they only correct, if they prefer that. Save questions and answers as `review/02-personas-questionnaire.md`.

**Stop:** wait for the answers (state `waiting for input`).

## 2. Build the personas

From the answers and `facts.md`, write 2–4 personas. Fewer is better; merge groups that want the same thing from the site. For each:

- **Name and role:** a role label, for example "Head of Marketing, mid-size insurer". A first name is fine if it makes the personas easier to talk about; no invented biography, age or hobbies.
- **Situation:** what they are responsible for, what triggers their visit.
- **Job on the website:** what they want to find out or get done, in their words.
- **What they value** and **what puts them off**.
- **Questions they need answered** before they act, in order of importance.
- **Words they use** for the problem and the solution.
- **How they decide:** alone or with others, how long, what proof they need.
- **Where they come from:** search, recommendation, ads, events, AI assistants.

Mark everything that came from the client as such, and every AI addition with `(assumption)`. Use industry knowledge for additions, never invented statistics.

Add one short **anti-persona**: who the site is explicitly not for. This keeps later steps from trying to please everyone.

## 3. Goals

Ask, if not answered in the questionnaire: *How will we know in six months that the new site works?* Turn the answer into 2–4 goals in `goals.md`, each with metric, baseline from `01-facts/baseline.md` (or "unknown") and target. Example: "Demo requests per month: 12 → 20". Add the date for the first measurement.

## Review

Show each persona as a compact card, assumptions visibly marked. Typical decisions:
- Are these the right personas, and which is primary?
- Which assumptions are wrong?
- Confirm the goals and the measurement date.

Below the decisions, add one short note: if the client can easily reach one real person per persona, a 15-minute call checks the assumptions (guide in `references/questionnaire.md`, section "Validation call"). It is optional and does not block the next step.

**Done when** the person confirmed the personas, picked a primary one and agreed on the goals.
