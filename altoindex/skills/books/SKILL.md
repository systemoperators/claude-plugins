---
name: books
description: Search Apple Books library, highlights, and annotations
argument-hint: [book title or author]
paths:
  - "**/alto-index/books/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- books

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Apple Books library exported by Alto Index to:
  <alto-index>/books/


## layout

- one file per book: `{title} - {author}.md`
- highlights file: `{title} - {author}_highlights.md`
- cover images in `images/` subfolder

## frontmatter

title, id, created, modified, source (ibooks:// deep link), author, genre, format (epub/pdf), pages, progress, has_content, rating

## body

Book metadata and reading progress. For DRM-free books, full extracted text. Highlights files contain all annotations and bookmarks with page/location references.

## tips

- use `ibooks://` URL from frontmatter to open in Books app
- `has_content: true` means full text was extracted (DRM-free only)
- highlights files have `_highlights` suffix
- search annotations across all books with `Grep` in books/
- `progress` field shows reading completion percentage
- cover images are in `images/` subfolder
