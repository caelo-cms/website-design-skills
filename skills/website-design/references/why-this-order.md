# Why these steps, in this order

Use this when the person asks why a step exists or wants to skip it. Answer in one or two sentences, then offer the shortest version of the step.

**The order.** Classic design practice (Design Thinking, Double Diamond, Google Design Sprint) separates finding the right problem from solving it right. Content comes before visual design ("Design in the absence of content is not design, it's decoration", Jeffrey Zeldman). Structure is settled in plain wireframes before anything looks finished, because polished mock-ups stop people from criticising structure. AI tools that produce good results (Relume, Google Stitch) follow the same order: sitemap, wireframe, then style.

**What changes with AI.**
- Without constraints a model picks the most likely option: the same fonts, purple gradients, three cards in a row. Anthropic calls this distributional convergence. Every step therefore ends in a file the model must follow.
- Variants cost almost nothing, so the bottleneck is the decision. That is why every step ends with a short decision sheet.
- Models invent facts, features and quotes. That is why step 1 exists and step 8 checks every claim against it.
- A model can look at its own output. Step 9 makes it do that.
- Simulated users are useful for finding problems but too friendly to replace people. Step 10 uses them as a filter and keeps real users optional.

**Per step.**
1. *Facts and inventory.* The AI fills gaps with invented details. Baselines from the old site make it possible to say later whether the new one is better.
2. *Personas and goals.* Every later decision needs a yardstick: who is this for? Interviews or a panel would be ideal; a persona picture from the client's knowledge plus AI is good enough to justify decisions. Shared goals end taste debates early.
3. *Positioning and brand attributes.* Design follows the message. Adjectives without an opposite ("modern") fit everything; with an opposite ("calm, not dull") they become a test for every later step.
4. *Structure and wireframes.* Decide what goes where before deciding how it looks. Grey wireframes with real copy invite criticism of structure; finished designs only get comments on colour.
5. *Moodboard.* People are bad at describing taste but good at judging examples. Real references bring something new; AI-generated images only remix what already exists.
6. *Directions as style tiles.* A moodboard is too vague and a full page too literal. Style tiles show colour, type and elements without layout, so the discussion stays on look and feel.
7. *Design system.* Decisions become rules that any person, model or tool can read, and the same tokens move into the CMS theme.
8. *Copy in page context.* A sentence reads differently in a layout than in a list. The fact check stops invented numbers, logos and testimonials.
9. *Prototype with QA loop.* Without screenshots the model works blind. Accessibility and speed are expensive to add at the end.
10. *Test with personas.* Catch the obvious problems before real people see the site.
11. *CMS handover and measurement.* The prototype is thrown away; the system stays. Without measurement nothing is learned after launch.
