---
name: usability-test
description: Step 10 of website-design. Tests the prototype from the point of view of each persona with fixed tasks (five-second impression, one typical task, three words against the brand attributes), with screenshots and findings sorted by severity; real users are optional. Use when a website prototype or page should be tested, reviewed from a user's perspective or audited before launch.
---

# Test with personas

**Why:** Before real people see the site, the obvious problems should be gone: unclear first screen, missing answers, dead ends, wrong tone. Simulated users built from the personas find these reliably. Research (Nielsen Norman Group) shows their limits too: they are too friendly and take the clean path where real people get stuck. So the AI test is asked to be strict, and tests with real users stay an option that is worth doing when access is easy.

**Needs:** prototype, `personas.md`, `brand.md` (attributes), `goals.md`, `sitemap.md`.
**Produces:** `10-test/test-report.md`, `10-test/test-report.html`.

## 1. Plan

For each persona, define:
- an entry point (where they land: home page, a product page from search, pricing from an ad)
- one typical task from their "job on the website" ("Find out whether this works with our CMS and what it costs for 3 editors")
- what success looks like (page reached, question answered, action found)

## 2. Run per persona

Take the persona's perspective strictly: their knowledge, their words, their impatience. Use screenshots of the real prototype, not memory of the code.

1. **Five-second impression:** look at the first screen only. What does this company offer? For whom? What can I do here? Note what is unclear.
2. **Task:** go through the site step by step, as the persona would. At each step note what they look for, what they find, where they hesitate, where they would leave. Take a screenshot of each point of friction.
3. **Three words:** pick three words from a list that mixes the brand attributes and their opposite poles. Record which side wins.
4. **Questions left open:** which of the persona's questions from `personas.md` were not answered?

Be critical on purpose: when in doubt, assume the persona leaves. Do not rate your own work kindly because you built it.

## 3. Findings

Sort by severity:
- **Blocks:** the task fails or the first screen is misunderstood
- **Hurts:** the task succeeds with effort, or the tone contradicts the brand attributes
- **Polish:** small irritations

Each finding: persona, page, screenshot, what happened, suggested fix. Group duplicates across personas; a problem hit by several personas ranks higher.

## Optional: real users

Five people from the target group find most usability problems (Nielsen Norman Group). If the client can reach them, run the same plan: five-second test, the task (think aloud, do not help), three words. Thirty minutes each, by video call with screen sharing. Write findings in the same format and mark them `real user`. They outweigh simulated findings when the two disagree.

## Review

Show the findings with screenshots and suggested fixes. Typical decisions: which findings to fix before launch, whether a real-user round is worth it, whether a finding points back to an earlier step (structure, copy, design).

**Done when** all *blocks* findings are fixed in the prototype (as a new round of step 9 with the QA loop; step 9 stays done) and the person approved launch preparation.
