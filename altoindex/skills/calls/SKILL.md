---
name: calls
description: Search phone call history
argument-hint: [contact name or date]
paths:
  - "**/alto-index/calls/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- calls

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Phone call history exported by Alto Index to:
  <alto-index>/calls/


## layout

- organized by contact: `by-contact/{contact-name}.md`
- organized by date: `by-date/{YYYY-MM-DD}.md`
- each file contains a table of calls

## frontmatter

title (contact name or date), id, created, modified, source (tel: or facetime: deep link)

## body

Table of calls with columns: date, time, duration, direction (incoming/outgoing/missed), type (phone/facetime audio/facetime video).

## tips

- two views: by-contact (all calls with one person) and by-date (all calls on one day)
- cross-reference phone numbers with contacts/ for full contact details
- direction field distinguishes incoming, outgoing, and missed calls
- duration is in seconds
- FaceTime calls include audio/video type distinction
