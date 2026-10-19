# Project templates

Create these files at project setup. Keep them short; they are read at the start of every session.

## Folder layout

```
PROJECT.md
STATUS.md
DECISIONS.md
01-facts/
02-personas/
03-brand/
04-structure/wireframes/
05-moodboard/references/
06-directions/
07-design-system/
08-copy/
09-prototype/
10-test/
11-handover/
review/            review pages (<NN>-<folder>-r<round>.html), pasted feedback (…-feedback.md),
                   intermediate stops (<NN>-<folder>-stop<k>.md), setup answers (00-setup.md)
review/screens/    screenshots, named <NN>-<what>-r<round>-<width>.png
```

## PROJECT.md

```markdown
# <Project name>

- Website: <url or "new">
- Type: redesign | new site
- Website language(s): <...>
- Working language: <...>
- Decides: <name(s)>
- Deadline: <date or none>
- Existing brand to keep: <logo, colours, fonts or "none">
- Form of address in the chat: <formal / informal; Sie / du>
- Sources: <folders, repos, documents, urls>

## Notes
<anything the person said that every step should know>
```

## STATUS.md

```markdown
# Status

| # | Step | State | Updated | Note |
|---|---|---|---|---|
| 1 | Facts and inventory | open | | |
| 2 | Personas and goals | open | | |
| 3 | Positioning and brand attributes | open | | |
| 4 | Structure and wireframes | open | | |
| 5 | Moodboard | open | | |
| 6 | Directions as style tiles | open | | |
| 7 | Design system | open | | |
| 8 | Copy in page context | open | | |
| 9 | Prototype with QA loop | open | | |
| 10 | Test with personas | open | | |
| 11 | CMS handover and measurement | open | | |

States: open · in progress · waiting for input · waiting for decision · done · imported · reduced · needs update
(Step 11 before the CMS build is finished: `waiting for input` with a note.)

Next: <step and what is needed from the person; update after every change>
Launch blockers: <what must be solved before going live, or "none">
```

## DECISIONS.md

```markdown
# Decisions

Newest at the bottom. Format: date · step · decision · source
Source: name plus (recommended), (deviation) or (own input); agent (correction) for fixed mistakes.
A change to an earlier step caused by a later one: step as "1 (from 8)".

- 2026-01-01 · setup · Redesign of example.com, English only · Alex (own input)
- 2026-01-03 · 3 · Promise version 2 · Alex (deviation)
```
