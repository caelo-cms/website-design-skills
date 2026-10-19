---
name: fact-base
description: Step 1 of website-design. Collects verified facts about a company and its offer with a source for each, inventories the existing website (what stays, what goes, which URLs need redirects) and records baseline numbers. Use before writing any website copy or concept, or when a project needs a single source of truth.
---

# Fact base and inventory

**Why:** An AI fills every gap with something plausible, and plausible is often wrong: old features, invented numbers, customers that never agreed to be named. A fact base with sources is what every later step checks against. Baseline numbers from the old site are the only way to say later whether the new one works better.

**Needs:** `PROJECT.md` (sources, website address).
**Produces:** `01-facts/facts.md`, `01-facts/inventory.md`, `01-facts/baseline.md`.

## 1. Facts

Read every source listed in `PROJECT.md`: documents, folders, code repositories, sales decks, the current website. Ask for access to anything that is missing rather than guessing.

Write `facts.md` in these sections (skip what does not apply):
- Company: name, legal entity, founding year, location, team size, history.
- Offer: products and services, each with what it does, for whom, what it costs (if public), what it explicitly does **not** do.
- Proof: numbers, customers that may be named, certifications, awards, press.
- Process: how someone becomes a customer (contact, demo, trial, purchase).
- Words: terms the company and its customers use, and terms to avoid.

Rules:
- One fact per bullet, each with a short source: `[source: pricing.pdf p.2]`, `[source: repo README, 2026-03]`, `[source: Alex, chat 2026-05-01]`.
- Separate facts from assumptions: mark interpretations `(assumption)`.
- Code beats documentation, newer beats older. When sources disagree, list both under **Open questions** at the end and ask; do not resolve it yourself.
- Customer names and quotes only with a note whether they may be shown publicly: `public: yes / no / unclear`.
- No private personal data (private e-mails or phone numbers, customers' contact persons). Business contact details and names that must be published anyway (imprint, team page) are fine.

## 2. Inventory (redesigns only)

Crawl or list the existing site's pages. For each page note: URL, purpose, traffic if known, and a verdict: **keep** (content moves over), **merge**, **drop**, or **rewrite**. Mark pages with external links or strong rankings: their URLs need redirects. Note assets worth keeping (photos, illustrations, videos, downloads) and their licence if known.

The old site is material, not a template. Do not copy its structure or wording unless the person asks for it.

## 3. Baseline

Record what can be measured today, with date and source: visits per month, top entry pages, conversions (contact requests, sign-ups, sales), search clicks and top queries, Core Web Vitals or Lighthouse scores. If no data is accessible, write which data would be needed and ask for it; a missing baseline is fine if it is written down. Read scores in context: a very small old site can score 100 in Lighthouse and still fail its visitors, so note page weight and content alongside the scores.

## Review

Build the review page with `decision-sheet`. Show: number of facts by section, the open questions, the inventory verdicts as a table, the baseline. Typical decisions:
- Resolve each open question (offer the likely answer as recommended).
- Confirm the inventory verdicts for pages with traffic.
- Which customers and numbers may be shown publicly.

**Done when** open questions are answered or explicitly parked, and the person confirmed the inventory.
