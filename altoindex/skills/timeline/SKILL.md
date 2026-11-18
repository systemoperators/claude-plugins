---
name: timeline
description: Show a chronological timeline of activity across all sources
argument-hint: [date or date range]
paths:
  - "**/alto-index/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- timeline

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Cross-source chronological timeline across all Alto Index exports at:
  <alto-index>/

## how to use

Given a date or date range, gather activity across all sources to build a timeline:

1. calendar/ — events and meetings for the date
2. messages/ — messages sent/received (search by date in content)
3. calls/ — calls made/received (by-date/ folder)
4. notes/ — notes created or modified on that date
5. granola/ — meetings held on that date
6. safari-history/ / chrome-history/ — pages visited
7. screen-time/ — app usage for the day
8. screenshots/ — screenshots taken (by date folder)

## search strategy

```
# find everything from a specific date
Grep "2025-01-15" <alto-index>/
Glob "<alto-index>/calls/by-date/2025-01-15*"
Glob "<alto-index>/safari-history/2025-01-15*"
Glob "<alto-index>/screen-time/2025-01-15*"
Glob "<alto-index>/screenshots/2025-01-15*"

# use frontmatter created/modified dates for other sources
Grep "created: 2025-01-15" <alto-index>/notes/
```

## tips

- calls/by-date/ and safari-history/ are organized by date — use Glob
- for messages, search the body for date timestamps
- calendar events have start_date in frontmatter
- screen-time daily files are named by date
- combine multiple sources for a full picture of a day
