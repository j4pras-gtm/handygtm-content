# handygtm-content (PUBLIC)

The editorial content for **HandyGTM** — playbooks, blog posts, tools, and authors. Pure markdown. No code.

> **Visibility: PUBLIC.** This repo is intentionally public so editors (and contributors) can add content via the GitHub web UI without any developer setup. The site application code lives in a separate **private** repo (`handygtm-site`).

## Structure

```
handygtm-content/
├── playbooks/          # one .md per playbook
├── blog/               # one .md per blog post
├── tools/              # one .md per tool (referenced from playbooks)
├── authors/            # one .md per author
├── index.json          # auto-generated manifest
└── EDITORS_GUIDE.md    # how to add content from the GitHub web UI
```

Every file is **YAML frontmatter + a markdown body**. The frontmatter drives both the public GEO page and the (future) member version on the site.

## Adding content (no code needed)

See [`EDITORS_GUIDE.md`](EDITORS_GUIDE.md). Quick version:

1. Click **Add file → Create new file** at the top of this repo.
2. Name it `playbooks/your-slug.md` (or `blog/...`, `tools/...`).
3. Paste the template from `EDITORS_GUIDE.md`.
4. Fill in the fields and write the body.
5. Open a Pull Request. On merge, the site rebuilds and your content goes live.

## How the site uses this repo

The site (`handygtm-site`, private) consumes this repo at **build time**:

- **Local dev:** added as a git submodule under `content/`.
- **Production (Hostinger / Lovable):** GitHub Action clones this repo, then builds the site.
- **Trigger rebuild:** every merge to `main` here fires `repository_dispatch` → site rebuilds.

This repo is never touched at runtime — the deployed site is fully static.

## License

Content is licensed CC BY 4.0 — see [LICENSE](LICENSE). Re-use freely with attribution to HandyGTM.

## Contributing

PRs welcome. Check [`CONTRIBUTING.md`](CONTRIBUTING.md) for tone, structure, and SEO/GEO rules.
