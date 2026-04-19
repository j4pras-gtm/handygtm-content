Every PR you open must include this exact template in its description:

```markdown
## What changed
<one-paragraph summary>

## Why
<reason / source request>

## Files touched
- path/to/file.md (created | edited | renamed)

## Sources
- <URL or citation for every factual claim>
- "None — opinion/synthesis only" if applicable

## Self-check
- \[ ] Filename matches `slug`
- \[ ] All required frontmatter fields present
- \[ ] `metaTitle` ≤ 60 chars
- \[ ] `metaDescription` ≤ 155 chars
- \[ ] ≥ 2 entries in `internalLinks` (playbooks only)
- \[ ] ≥ 3 entries in `steps` (playbooks only)
- \[ ] All referenced tool slugs exist in `tools/`
- \[ ] All `internalLinks` resolve to existing files
- \[ ] No raw HTML in body
- \[ ] No secrets, PII, or credentials in diff
- \[ ] \[CITATION NEEDED] markers flagged below if any

## Open questions for owner
<bullet list, or "None">
```

PRs missing this template will be rejected without review.
