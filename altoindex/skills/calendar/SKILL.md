---
name: calendar
description: Search and read calendar events
argument-hint: [date or event name]
paths:
  - "**/alto-index/calendar/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- calendar

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Calendar events exported by Alto Index to:
  <alto-index>/calendar/


## layout

- organized by calendar name, then by date
- filename: `{event-title}-{id}.md`
- recurring events exported as individual occurrences

## frontmatter

title, id, created, modified, source (calshow:// deep link), calendar, start_date, end_date, location, all_day, recurrence

## body

Event description/notes followed by attendee list and location details.

## tips

- use `calshow:` URL from frontmatter to open in Calendar app
- search by date range using `Glob` with date patterns in folder names
- all-day events have `all_day: true` in frontmatter
- recurring events appear as separate files per occurrence
- cross-reference attendees with contacts/
