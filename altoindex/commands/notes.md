---
description: Browse or search your Apple Notes
allowed-tools: Read, Glob, Grep
argument-hint: "[query]"
---

Work with Apple Notes synced to `~/Documents/alto-index/notes/`.

If $ARGUMENTS is provided, search notes for that query using Grep. Show matching notes with their folder, title, and `notes://` deep link.

If no arguments, list the note folders and count of notes in each:
- use Glob to find `~/Documents/alto-index/notes/*/` directories
- count .md files in each folder
- show the most recently modified notes (check `modified` frontmatter)

Always include the `notes://` deep link from the `source` frontmatter field so the user can open notes in the native app.
