# HandyGTM — Content Schema

Every piece of editorial content is a single markdown file with **YAML frontmatter** + a markdown body. The frontmatter is the contract that drives both the **public GEO page** and the **member version** (Phase 2+).

One file = one URL = one source of truth.

---

## Playbook — `playbooks/<slug>.md`

```yaml
---
slug: signal-based-outbound-with-clay
title: "Signal-based outbound with Clay + Smartlead"
summary: "Capture intent signals, enrich them with AI, route them into low-volume, high-relevance sequences."
motion: outbound          # inbound | outbound | product-led | community | revops | abm
difficulty: Intermediate  # Starter | Intermediate | Advanced
useCase: "Founders and small GTM teams who want pipeline without spray-and-pray outbound."
tools:
  - clay
  - smartlead
  - openai
steps:
  - title: "Define the trigger"
    body: "Pick one observable buyer event (job change, funding, hiring spike)."
  - title: "Build the enrichment chain"
    body: "Layer firmographic + technographic + behavioral data in Clay."
  - title: "Write the AI personalization prompt"
    body: "Use a single high-context prompt, not five clever ones."
examples:
  - "A 4-person team booked 32 meetings in 30 days with 600 sends."
faq:
  - q: "Do I need Clay's enterprise tier?"
    a: "No. The starter tier covers the first 90 days for most teams."
  - q: "What if I don't have a CRM yet?"
    a: "Use a Google Sheet. The pattern is what matters."
internalLinks:
  - playbooks/ai-enriched-icp-list-building
  - tools/clay
  - community
seo:
  metaTitle: "Signal-based outbound with Clay + Smartlead — HandyGTM"
  metaDescription: "A repeatable, AI-first outbound playbook for lean teams. Triggers, enrichment, prompts, and sequencing."
  ogImage: ""
  canonical: "/playbooks/signal-based-outbound-with-clay"
member:
  checklist:
    - "Defined one trigger and documented it"
    - "Built enrichment chain in Clay"
    - "Wrote and tested the personalization prompt"
  downloads:
    - label: "Clay table template (CSV)"
      file: "clay-template.csv"
  affiliateBlock: "clay-default"
---

## Why this works

Markdown body goes here. Headings (##, ###), lists, links — all supported. This body powers the long-form public page AND the member view.
Field rules
Field	Required	Notes
slug	yes	kebab-case, must match filename
title	yes	≤ 70 chars
summary	yes	≤ 160 chars; used in cards + meta description fallback
motion	yes	one of the 6 motions
difficulty	yes	Starter / Intermediate / Advanced
tools[]	yes	slugs that match tools/<slug>.md
steps[]	yes	min 3 steps for HowTo schema
faq[]	optional	drives FAQPage JSON-LD
internalLinks[]	yes	min 2 — every playbook links to ≥2 related pages
seo.metaTitle	yes	≤ 60 chars
seo.metaDescription	yes	≤ 155 chars
member.*	optional	gated content; ignored on public page
Blog post — blog/<slug>.md

---
slug: what-is-gtm-engineering
title: "What is GTM Engineering, really?"
excerpt: "A working definition of GTM Engineering and why it's the missing layer between strategy and execution."
category: Guide              # Tactics | Tips | Guide | Notes
readMinutes: 6
publishedAt: 2025-09-12
author: handygtm-team
internalLinks:
  - playbooks/signal-based-outbound-with-clay
seo:
  metaTitle: "What is GTM Engineering? — HandyGTM"
  metaDescription: "A working definition of GTM Engineering and why every lean team needs one."
  ogImage: ""
  canonical: "/blog/what-is-gtm-engineering"
---

Markdown body here. Every blog post must internally link to ≥1 playbook.
Tool — tools/<slug>.md

---
slug: clay
name: "Clay"
description: "AI-native data enrichment + workflow tool."
useCases:
  - "Outbound enrichment"
  - "ICP list building"
install: "https://clay.com"
alternatives:
  - apollo
  - persana
linkedPlaybooks:
  - signal-based-outbound-with-clay
  - ai-enriched-icp-list-building
affiliateUrl: ""             # optional, populated for member affiliate block
---

Markdown body: when to use it, when not to, gotchas.
Tools are referenced by slug from playbooks. Never duplicate tool details inside a playbook.

Author — authors/<slug>.md

---
slug: handygtm-team
name: "HandyGTM Team"
bio: "Operators and engineers building lean GTM systems."
avatar: ""
links:
  twitter: ""
  linkedin: ""
---
index.json (auto-generated)
Generated at build time by walking the content directories. Drives nav/listing without re-parsing every markdown file at runtime.


{
  "playbooks": [{ "slug": "...", "title": "...", "motion": "...", "difficulty": "..." }],
  "blog": [{ "slug": "...", "title": "...", "publishedAt": "..." }],
  "tools": [{ "slug": "...", "name": "..." }]
}
