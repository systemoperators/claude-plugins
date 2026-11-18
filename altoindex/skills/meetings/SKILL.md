---
name: meetings
description: Search and read Granola meeting notes and transcripts
argument-hint: [meeting topic or date]
paths:
  - "**/alto-index/granola/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- meetings

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Granola meeting notes and transcripts exported by Alto Index to:
  <alto-index>/granola/


## layout

- one file per meeting
- filename: `{meeting-title}-{id}.md`

## frontmatter

title, id, created (meeting date), modified, source (granola:// deep link), duration, participants

## body

Meeting notes (user-edited) followed by full transcript with speaker labels and timestamps.

## tips

- search meeting content by topic or participant name
- transcripts include speaker labels — grep for a person's name to find their contributions
- meeting notes section is user-curated, transcript is auto-generated
- cross-reference participants with contacts/
- use date-based search to find meetings in a time range
