---
name: kindle
description: Search Kindle library, highlights, and annotations
argument-hint: [book title or author]
paths:
  - "**/alto-index/kindle/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- kindle

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Kindle library exported by Alto Index to:
  <alto-index>/kindle/


## layout

- one file per book: `{title} - {author}.md`
- highlights included in the same file

## frontmatter

title, id, created, modified, source (kindle:// deep link), author, asin, pages, progress, has_highlights

## body

Book metadata followed by highlights and annotations with location references. Each highlight includes the highlighted text and any user notes.

## tips

- search highlights across all Kindle books with `Grep`
- `asin` field is the Amazon identifier
- author data may be enriched from external sources
- combine with books/ skill for complete reading library
- highlights are ordered by location within the book
