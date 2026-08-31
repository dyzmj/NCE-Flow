---
name: seo-metadata-update
description: Workflow command scaffold for seo-metadata-update in NCE-Flow.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /seo-metadata-update

Use this workflow when working on **seo-metadata-update** in `NCE-Flow`.

## Goal

Add or update SEO metadata (title, meta description, OpenGraph, robots.txt, sitemap) for core pages.

## Common Files

- `index.html`
- `lesson.html`
- `about.html`
- `favorites.html`
- `book.html`
- `robots.txt`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit HTML files for core pages (index.html, lesson.html, about.html, etc.) to add/update meta tags, canonical URLs, OpenGraph, Twitter Card, and JSON-LD
- Update or add robots.txt and sitemap.xml as needed
- Mark private or non-indexable pages with noindex

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.