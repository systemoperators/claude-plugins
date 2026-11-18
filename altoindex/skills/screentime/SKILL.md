---
name: screentime
description: Search Screen Time usage data
argument-hint: [app name or date]
paths:
  - "**/alto-index/screen-time/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- screentime

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Screen Time usage data exported by Alto Index to:
  <alto-index>/screen-time/


## layout

- daily files: `{YYYY-MM-DD}.md`
- summary.md with aggregate stats

## frontmatter

title (date), id, created, modified, total_screen_time, app_count

## body

Daily breakdown of app usage with time spent per app, organized by category. Includes pickups count and first/last use times.

## tips

- search by app name with `Grep` to find usage patterns
- daily files show per-app time in descending order
- summary.md has weekly/monthly aggregates
- bundle IDs are resolved to human-readable app names
- combine with screenshots/ to see what you were doing at specific times
