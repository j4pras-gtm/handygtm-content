# Editor's Guide — Adding content from the GitHub web UI

You don't need to install anything. You don't need a developer. You just need a GitHub account.

## Add a new playbook (5 minutes)

1. Go to this repo on GitHub.
2. Open the `playbooks/` folder.
3. Click **Add file → Create new file**.
4. In the filename box, type: `your-slug.md` (lowercase, hyphens, no spaces).
5. Paste this template into the body and fill it in:

```yaml
---
slug: your-slug
title: "Your playbook title"
summary: "One-sentence summary, under 160 characters."
motion: outbound          # inbound | outbound | product-led | community | revops | abm
difficulty: Starter       # Starter | Intermediate | Advanced
useCase: "Who this is for and what they get."
tools:
  - clay
  - smartlead
steps:
  - title: "First step"
    body: "What to do, in one or two sentences."
  - title: "Second step"
    body: "..."
  - title: "Third step"
    body: "..."
examples:
  - "A real-world example, one or two sentences."
faq:
  - q: "A question a reader will ask"
    a: "A direct answer."
internalLinks:
  - playbooks/another-related-playbook
  - tools/clay
  - community
seo:
  metaTitle: "Your playbook title — HandyGTM"
  metaDescription: "Same as summary, under 155 chars."
  ogImage: ""
  canonical: "/playbooks/your-slug"
member:
  checklist:
    - "Did the first thing"
    - "Did the second thing"
  downloads: []
  affiliateBlock: ""
---

## Why this works

Write a few paragraphs in plain markdown. Headings (##), lists (- item), links ([text](url)) all work.

## The system

Explain the playbook clearly. Operator tone. No fluff.
```

6. Scroll down. In **Commit changes**, choose **Create a new branch** and click **Propose changes**.
7. On the next screen, click **Create pull request**.
8. Wait for review + merge. Site goes live within minutes after merge.

## Add a blog post

Same flow, but in `blog/` and use this template:

```yaml
---
slug: your-post-slug
title: "Your post title"
excerpt: "One-sentence hook, under 160 characters."
category: Guide          # Tactics | Tips | Guide | Notes
readMinutes: 4
publishedAt: 2025-04-19
author: handygtm-team
internalLinks:
  - playbooks/signal-based-outbound-with-clay
seo:
  metaTitle: "Your post title — HandyGTM"
  metaDescription: "Same as excerpt, under 155 chars."
  ogImage: ""
  canonical: "/blog/your-post-slug"
---

Your post body in markdown. Every blog post must internally link to at least 1 playbook.
```

## Tone + style rules

- Operator voice. Direct. No hype.
- No keyword stuffing.
- Every playbook links to ≥ 2 related pages (other playbooks, tools, community).
- Every blog post links to ≥ 1 playbook.
- One H1 per page (the `title` field — don't add another `#` heading at the top of the body).
- Use `##` and `###` for sections.

## Common mistakes

- **Filename mismatch** — `slug:` in the frontmatter must equal the filename without `.md`.
- **Missing `summary` / `excerpt`** — required for cards and meta descriptions.
- **Tool slug typo** — every entry in `tools:` must match a file in `tools/`.
- **Adding a brand-new tool** — create `tools/your-tool.md` in the same PR.
