---
description: Browse your Apple Reminders
allowed-tools: Read, Glob, Grep
argument-hint: "[list or query]"
---

Work with Apple Reminders synced to `~/Documents/alto-index/reminders/`.

If $ARGUMENTS is provided, search reminders for that query or filter by list name.

If no arguments, show all reminders grouped by list:
- use Glob to find `~/Documents/alto-index/reminders/*/` directories
- count reminders in each list
- highlight reminders with due dates (show due_date from frontmatter)
- highlight flagged reminders

Always include the `x-apple-reminder://` deep link from the `link` frontmatter field.
