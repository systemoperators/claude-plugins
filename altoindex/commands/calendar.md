---
description: Browse your Apple Calendar events
allowed-tools: Read, Glob, Grep
argument-hint: "[date or query]"
---

Work with Apple Calendar events synced to `~/Documents/alto-index/calendar/`.

If $ARGUMENTS is a date, show events for that date. If a query, search events for that text.

If no arguments, show upcoming events:
- check today's and tomorrow's date folders across all calendars
- show event title, time, location, and attendees
- list which calendars are synced

Always include the `calshow:` deep link from the `link` frontmatter field.

If the calendar folder doesn't exist, tell the user to enable Calendar sync in alto.index.
