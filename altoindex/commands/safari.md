---
description: Browse your Safari bookmarks and history
allowed-tools: Read, Glob, Grep
argument-hint: "[query]"
---

Work with Safari data synced to `~/Documents/alto-index/safari-bookmarks/` and `~/Documents/alto-index/safari-history/`.

If $ARGUMENTS is provided, search both bookmarks and history for that query.

If no arguments:
- list bookmark folders with item counts from safari-bookmarks/
- show today's browsing history from safari-history/ (if available)
- show the most recent history file date

If the folders don't exist, tell the user to enable Safari Bookmarks and/or Safari History sync in alto.index.
