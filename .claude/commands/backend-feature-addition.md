---
name: backend-feature-addition
description: Workflow command scaffold for backend-feature-addition in NCE-Flow.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /backend-feature-addition

Use this workflow when working on **backend-feature-addition** in `NCE-Flow`.

## Goal

Add or enhance backend features (e.g., data sync, API endpoints) and integrate with frontend.

## Common Files

- `lua/userdata.lua`
- `nginx.conf`
- `Dockerfile`
- `docker-compose.yml`
- `assets/storage.js`
- `assets/lesson.js`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Implement backend logic (e.g., lua/userdata.lua, nginx.conf for OpenResty endpoints)
- Update Dockerfile and docker-compose.yml for backend dependencies and volumes
- Update frontend JS modules to use new backend APIs (e.g., assets/storage.js, assets/lesson.js, assets/favorites.js)
- Update HTML pages to load new/updated JS modules
- Update service worker (sw.js) to handle new routes or caching rules

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.