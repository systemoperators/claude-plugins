---
name: bear
description: Search and read Bear notes
argument-hint: [search query]
paths:
  - "**/alto-index/bear/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- bear

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Bear notes exported by Alto Index to:
  <alto-index>/bear/


## layout

- organized by tag hierarchy
- filename: `{note-title}-{id}.md`

## frontmatter

title, id, created, modified, source (bear:// deep link), tags, pinned, archived

## body

Note content in markdown format, preserving Bear's markdown extensions where possible.

## tips

- use `bear://x-callback-url/open-note?id={id}` to open in Bear
- tags are in frontmatter as an array
- search across all notes with `Grep`
- pinned and archived status available in frontmatter
- Bear uses nested tags (e.g., `work/projects`) reflected in folder structure
