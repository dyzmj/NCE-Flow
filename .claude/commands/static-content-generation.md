---
name: static-content-generation
description: Workflow command scaffold for static-content-generation in NCE-Flow.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /static-content-generation

Use this workflow when working on **static-content-generation** in `NCE-Flow`.

## Goal

Generate or update large sets of static HTML pages from source data for SEO or content updates.

## Common Files

- `scripts/generate_lesson_pages.py`
- `NCE1/*.html`
- `NCE2/*.html`
- `NCE3/*.html`
- `NCE4/*.html`
- `NCE1/index.html`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update or add source data (e.g., data.json, .lrc files)
- Run static page generation script (e.g., scripts/generate_lesson_pages.py)
- Output hundreds of new/updated HTML files in NCE1/, NCE2/, NCE3/, NCE4/ directories
- Update index.html files for each book
- Update sitemap.xml to reflect new URLs

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.