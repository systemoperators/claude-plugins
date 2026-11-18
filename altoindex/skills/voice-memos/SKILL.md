---
name: voice-memos
description: Search and read voice memo transcriptions
argument-hint: [search query]
paths:
  - "**/alto-index/voice-memos/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- voice-memos

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Voice Memos exported by Alto Index to:
  <alto-index>/voice-memos/


## layout

- one markdown file per recording
- filename: `{memo-title}.md`
- audio files (.m4a) copied alongside metadata
- index.md contains a table of all recordings

## frontmatter

title, id, created (recording date), modified, source (file path), duration, has_audio

## body

Recording metadata including duration, date, and file size. Audio file linked for playback.

## tips

- index.md has a sortable table of all memos with dates and durations
- audio files are .m4a format, playable in any media player
- search memo titles and metadata with `Grep`
- duration is in seconds in frontmatter
