---
name: screenshots
description: Search screenshots by OCR text or metadata
argument-hint: [search query]
paths:
  - "**/alto-index/screenshots/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- screenshots

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Screenshots exported by Alto Index to:
  <alto-index>/screenshots/


## layout

- organized by date: `{YYYY-MM-DD}/`
- filename: `{screenshot-name}.md` (metadata file)
- images: `{screenshot-name}.png` alongside metadata
- OCR data: `{screenshot-name}.ocr.json` sidecar files

## frontmatter

title, id, created (capture date), modified, source (photos:// deep link), width, height, ocr_text_preview

## body

OCR-extracted text from the screenshot (via Vision framework). Full text searchable.

## tips

- search screenshot content with `Grep` — OCR text is in the body
- `.ocr.json` sidecars contain structured OCR data with bounding boxes
- images are in the same folder as their metadata .md files
- use date-based folders to narrow search to a time range
- combine with screen-time data to understand what app was active
