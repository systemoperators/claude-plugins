---
name: chrome
description: Search Chrome bookmarks and browsing history
argument-hint: [search query]
paths:
  - "**/alto-index/chrome-bookmarks/**"
  - "**/alto-index/chrome-history/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- chrome

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Chrome bookmarks and history exported by Alto Index to:
  <alto-index>/chrome-bookmarks/
  <alto-index>/chrome-history/


## layout

### bookmarks
- organized by folder, prefixed with Chrome profile name
- filename: `{bookmark-title}.md`

### history
- organized by date: `{YYYY-MM-DD}/{title}.md`
- merged across Chrome profiles, deduplicated

## frontmatter

### bookmarks
title, id, created, modified, source (URL), folder, profile

### history
title, id, created (visit time), source (URL), visit_count, domain

## body

Bookmarks contain URL and folder path. History entries contain visit timestamps and page URL.

## tips

- multi-profile support: bookmarks are prefixed with profile name
- history is deduplicated across profiles by (url, visitTime)
- search by domain with `Grep` for common patterns
- combine with safari skill for complete browsing picture
