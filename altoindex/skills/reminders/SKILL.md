---
name: reminders
description: Search and read reminders
argument-hint: [search query]
paths:
  - "**/alto-index/reminders/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- reminders

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Reminders exported by Alto Index to:
  <alto-index>/reminders/


## layout

- organized by reminder list
- filename: `{reminder-title}-{id}.md`
- subtasks nested under parent reminders

## frontmatter

title, id, created, modified, source (x-apple-reminderkit:// deep link), list, due_date, priority, completed, completed_date

## body

Reminder notes/description followed by subtasks and attachments if present.

## tips

- use `x-apple-reminderkit://` URL from frontmatter to open in Reminders
- filter completed vs incomplete by `completed` frontmatter field
- `priority` values: 0 (none), 1 (high), 5 (medium), 9 (low)
- search by list name using folder structure
- due dates are in `due_date` frontmatter field
