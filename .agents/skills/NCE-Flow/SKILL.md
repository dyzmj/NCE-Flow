```markdown
# NCE-Flow Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development patterns, coding conventions, and operational workflows for the NCE-Flow repository. NCE-Flow is a JavaScript-based project (no framework detected) focused on generating and serving static educational content, with backend features for data management and SEO optimization. The repository emphasizes static site generation, SEO best practices, and modular backend integration.

## Coding Conventions

- **File Naming:**  
  Use kebab-case for all file names.  
  _Example:_  
  ```
  assets/lesson-utils.js
  scripts/generate-lesson-pages.py
  ```

- **Import Style:**  
  Always use relative imports in JavaScript files.  
  _Example:_  
  ```js
  import { getLesson } from './lesson-utils.js';
  ```

- **Export Style:**  
  Use named exports for all modules.  
  _Example:_  
  ```js
  // assets/lesson-utils.js
  export function getLesson(id) { ... }
  export function listLessons() { ... }
  ```

- **Commit Messages:**  
  Follow the [Conventional Commits](https://www.conventionalcommits.org/) format, using `feat` as the prefix for new features.  
  _Example:_  
  ```
  feat: add support for lesson progress tracking
  ```

## Workflows

### Static Content Generation
**Trigger:** When new lesson content is added or existing content is updated, and static HTML pages need to be (re)generated for SEO or indexing.  
**Command:** `/generate-static-pages`

1. Update or add source data (e.g., `data.json`, `.lrc` files).
2. Run the static page generation script:
   ```bash
   python scripts/generate_lesson_pages.py
   ```
3. The script outputs hundreds of new or updated HTML files in `NCE1/`, `NCE2/`, `NCE3/`, `NCE4/` directories.
4. Update `index.html` files for each book directory.
5. Update `sitemap.xml` to reflect new URLs.

**Files Involved:**  
`scripts/generate_lesson_pages.py`, `NCE1/*.html`, `NCE2/*.html`, `NCE3/*.html`, `NCE4/*.html`, `NCE1/index.html`, `NCE2/index.html`, `NCE3/index.html`, `NCE4/index.html`, `sitemap.xml`

---

### SEO Metadata Update
**Trigger:** When improving SEO for main site pages or after adding new major pages.  
**Command:** `/update-seo`

1. Edit HTML files (e.g., `index.html`, `lesson.html`, `about.html`) to add or update:
   - `<title>`
   - `<meta name="description">`
   - OpenGraph tags (`<meta property="og:...">`)
   - Twitter Card tags
   - JSON-LD structured data
   - Canonical URLs
2. Update or add `robots.txt` and `sitemap.xml` as needed.
3. Mark private or non-indexable pages with `<meta name="robots" content="noindex">`.

_Example:_
```html
<!-- index.html -->
<head>
  <title>NCE-Flow: English Lessons</title>
  <meta name="description" content="Comprehensive English lessons for all levels.">
  <meta property="og:title" content="NCE-Flow: English Lessons">
  <meta property="og:description" content="Comprehensive English lessons for all levels.">
  <link rel="canonical" href="https://nce-flow.example.com/">
</head>
```

**Files Involved:**  
`index.html`, `lesson.html`, `about.html`, `favorites.html`, `book.html`, `robots.txt`, `sitemap.xml`

---

### Backend Feature Addition
**Trigger:** When implementing new backend functionality such as user data sync or API endpoints, and connecting it to the frontend.  
**Command:** `/add-backend-feature`

1. Implement backend logic (e.g., update `lua/userdata.lua`, configure `nginx.conf` for OpenResty endpoints).
2. Update `Dockerfile` and `docker-compose.yml` for backend dependencies and volumes.
3. Update frontend JS modules to use new backend APIs (e.g., `assets/storage.js`, `assets/lesson.js`, `assets/favorites.js`).
4. Update HTML pages to load new or updated JS modules.
5. Update `sw.js` (service worker) to handle new routes or caching rules.
6. Document backend usage in `DOCKER.md`.

_Example API call in JS:_
```js
import { syncUserData } from './storage.js';

syncUserData().then(() => {
  console.log('User data synced with backend.');
});
```

**Files Involved:**  
`lua/userdata.lua`, `nginx.conf`, `Dockerfile`, `docker-compose.yml`, `assets/storage.js`, `assets/lesson.js`, `assets/favorites.js`, `index.html`, `lesson.html`, `favorites.html`, `sw.js`, `DOCKER.md`

## Testing Patterns

- **Test File Naming:**  
  Test files follow the `*.test.*` pattern (e.g., `lesson.test.js`).
- **Testing Framework:**  
  Not explicitly detected; review test files for framework usage.
- **Test Example:**  
  ```js
  // lesson.test.js
  import { getLesson } from './lesson-utils.js';

  test('getLesson returns lesson data', () => {
    expect(getLesson(1)).toBeDefined();
  });
  ```

## Commands

| Command                | Purpose                                                    |
|------------------------|------------------------------------------------------------|
| /generate-static-pages | Generate or update static HTML pages from source data      |
| /update-seo            | Add or update SEO metadata for core site pages             |
| /add-backend-feature   | Add or enhance backend features and integrate with frontend|
```
