---
description: Search across all alto.index data sources
allowed-tools: Read, Glob, Grep
argument-hint: "[query]"
---

Search across all alto.index data sources for: $ARGUMENTS

Use Grep to search `~/Documents/alto-index/` recursively for the query. Search in all subdirectories: notes, reminders, contacts, calendar, messages, granola, safari-bookmarks, safari-history, voice-memos, and any others present.

For each match:
- show the source type (note, reminder, contact, event, conversation, meeting, etc.)
- show the file title (from frontmatter `title` field or filename)
- show the matching line with context
- include the deep link if available (notes://, x-apple-reminder://, addressbook://, calshow:)

Group results by data source. If there are many results, show the top 5 per source and mention how many total matches exist.

If $ARGUMENTS is empty, ask the user what they want to search for.
