---
description: Browse your Granola meeting notes
allowed-tools: Read, Glob, Grep
argument-hint: "[query]"
---

Work with Granola meeting notes synced to `~/Documents/alto-index/granola/`.

If $ARGUMENTS is provided, search meetings for that query - check titles, participants, transcripts, and notes.

If no arguments:
- read `~/Documents/alto-index/granola/index.md` for the full meeting list
- show the most recent meetings with date and title
- highlight any meetings from this week

If the granola folder doesn't exist, tell the user to enable Granola sync in alto.index.
