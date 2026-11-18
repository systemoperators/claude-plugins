---
name: notes
description: Search and read Apple Notes
argument-hint: [search query]
paths:
  - "**/alto-index/notes/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- notes

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Apple Notes exported by Alto Index to:
  <alto-index>/notes/


## layout

- folder structure mirrors Apple Notes folders
- filename: `{note-title}-{id}.md`
- attachments in `attachments/` subfolder per folder

## frontmatter

title, id, created, modified, source_url (notes:// deep link), tags (folder path)

## body

Markdown converted from Apple's proprietary note format. Includes inline images, tables, checklists, and drawings where available.

## tips

- use the `notes://showNote?identifier={id}` URL from frontmatter `source_url` to open in Apple Notes
- folder path is in `tags` frontmatter field
- search across all notes with `Grep` on the notes/ directory
- attachments are embedded as wikilinks (`![[attachments/file.png]]`) relative to the note's folder
