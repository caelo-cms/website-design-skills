# Website design skills

Free agent skills that guide you through designing a website with AI, from facts and personas to a tested prototype and the handover into your CMS. You install them, tell your agent "I want to design a new website for my company", and it leads you step by step. You decide; the agent does the work.

The skills use the open [Agent Skills](https://agentskills.io) format (`SKILL.md`) and work with any agent that supports it, for example Claude Code, Codex, Cursor, GitHub Copilot or Gemini CLI.

Overview of the steps and a case study: [Design a website with AI](https://caelo-cms.com/guides/design-a-website-with-ai/).

## Why a process

Ask an AI to "build me a website" and you get a page that looks like a thousand others: the same fonts, purple gradients, three cards in a row. Without constraints, a model picks the most likely option. These skills replace the missing constraints with decisions: each step produces a file the next step must follow, and ends with a short decision sheet for you.

The order follows established design practice (Design Thinking, the Double Diamond by the Design Council, content-first, wireframes before visual design) and adds what is specific to AI: a fact base against invented claims, explicit anti-defaults, a design contract in `DESIGN.md` and tokens, and a QA loop in which the model looks at its own screenshots.

## The steps

| # | Phase | Step | Skill |
|---|---|---|---|
| | | Leads the whole project | `website-design` |
| 1 | Understand | Facts and inventory | `fact-base` |
| 2 | Understand | Personas and goals | `personas` |
| 3 | Define | Positioning and brand attributes | `positioning` |
| 4 | Define | Structure and wireframes | `sitemap-wireframe` |
| 5 | Develop | Moodboard | `moodboard` |
| 6 | Develop | Directions as style tiles | `design-directions` |
| 7 | Develop | Design system | `design-system` |
| 8 | Develop | Copy in page context | `page-copy` |
| 9 | Deliver | Prototype with QA loop | `prototype-qa` |
| 10 | Deliver | Test with personas | `usability-test` |
| 11 | Deliver | CMS handover and measurement | `cms-handover` |
| | | Review pages with decisions | `decision-sheet` |

Each step ends with an HTML review page: the result, why the step matters, and a few decisions with a recommended option. You click "Copy feedback", paste it into the chat, and the agent logs your decisions and moves on. The project state lives in `STATUS.md` and `DECISIONS.md`, so you can stop and continue days later.

## Install

Copy the skill folders into your agent's skills directory.

Claude Code (all projects):
```
git clone https://github.com/caelo-cms/website-design-skills
cp -r website-design-skills/skills/* ~/.claude/skills/
```

Claude Code (one project): copy into `.claude/skills/` in the project. Other agents: see your agent's documentation for the skills folder.

## Start

Open an empty folder for the project and say:

> I want to design a new website for my company.

or, for a redesign:

> Let's redesign example.com.

The agent asks a few setup questions, creates the project files and starts with step 1. To continue later, open the same folder and say "Let's continue".

## What you need

- An agent that can read and write files. A browser tool (for screenshots) makes steps 5, 9 and 10 much better.
- Your material: existing website, documents, sales decks, anything that describes the offer.
- About 10 minutes for the persona questionnaire and 20–30 references you like or dislike for the moodboard.

## Related skills

These focus on single parts of the process and work well alongside:
- [Impeccable](https://impeccable.style/) – frontend design commands and checks for typical AI patterns
- [Vercel web design guidelines](https://github.com/vercel-labs/agent-skills) – review rules for accessibility, UX and performance
- [Anthropic skills](https://github.com/anthropics/skills) – including `frontend-design`

## Where the design comes to life

Step 11 works with any CMS. It includes a guide for [Caelo](https://caelo-cms.com), the open-source CMS for websites run with AI, where theme tokens, modules with named fields and a quality gate keep the design intact when people and AI edit the site.

## License

MIT
