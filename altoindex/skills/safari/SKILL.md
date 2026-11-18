---
name: safari
description: Search Safari bookmarks and browsing history
argument-hint: [search query]
paths:
  - "**/alto-index/safari-bookmarks/**"
  - "**/alto-index/safari-history/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- safari

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Safari bookmarks and history exported by Alto Index to:
  <alto-index>/safari-bookmarks/
  <alto-index>/safari-history/


## layout

### bookmarks
- organized by bookmark folder hierarchy
- filename: `{bookmark-title}.md`

### history
- organized by date: `{YYYY-MM-DD}/{title}.md`
- grouped by day with visit timestamps

## frontmatter

### bookmarks
title, id, created, modified, source (URL), folder

### history
title, id, created (visit time), source (URL), visit_count, domain

## body

Bookmarks contain the URL and folder path. History entries contain visit timestamps and the page URL.

## tips

- search bookmarks by folder name or URL domain
- history is grouped by day — use `Glob` with date patterns like `2025-01-*` to find activity in a time range
- visit_count in history shows how frequently a page was visited
- cross-reference URLs between bookmarks and history
