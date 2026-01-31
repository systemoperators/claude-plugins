---
description: Summarize a specific alto.index data source
allowed-tools: Read, Glob, Grep
argument-hint: "[source]"
---

Summarize the alto.index data source: $ARGUMENTS

Valid sources: notes, reminders, contacts, calendar, messages, granola, voice-memos, safari-bookmarks, safari-history

Steps:
1. Check if `~/Documents/alto-index/$ARGUMENTS/` exists
2. If it exists, count the files and read the CLAUDE.md if present
3. Provide a summary:
   - total number of items
   - folder/list breakdown (for notes and reminders)
   - date range of content
   - notable items or patterns

If $ARGUMENTS is empty or invalid, list the available data sources with file counts.

Keep the summary concise - a few bullets per source, not a full dump.
