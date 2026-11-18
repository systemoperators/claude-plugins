---
name: today
description: Show today's activity summary across all sources
argument-hint: [none]
paths:
  - "**/alto-index/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- today

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Today's activity summary across all Alto Index exports at:
  <alto-index>/

## how to use

Gather today's activity across all sources. Use today's date (today's date (`date +%F`)) to search:

1. calendar/ — today's events and meetings
2. reminders/ — reminders due today
3. calls/ — calls made/received today (by-date/ folder)
4. messages/ — recent messages
5. screen-time/ — today's app usage
6. notes/ — notes created or modified today
7. screenshots/ — screenshots taken today

## search strategy

```
# today's calls
Glob "<alto-index>/calls/by-date/today's date (`date +%F`)*"

# today's screen time
Read "<alto-index>/screen-time/today's date (`date +%F`).md"

# today's screenshots
Glob "<alto-index>/screenshots/today's date (`date +%F`)/*"

# today's calendar events
Grep "start_date: today's date (`date +%F`)" <alto-index>/calendar/

# notes modified today
Grep "modified: today's date (`date +%F`)" <alto-index>/notes/
```

## tips

- start with calendar and screen-time for a structured overview
- check calls/by-date/ for today's date
- recent messages are at the bottom of conversation files
- reminders with today's due date may be across multiple list folders
