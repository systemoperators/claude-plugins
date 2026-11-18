---
name: mail
description: Search and read Apple Mail messages
argument-hint: [search query]
paths:
  - "**/alto-index/mail/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- mail

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Apple Mail messages exported by Alto Index to:
  <alto-index>/mail/


## layout

- organized by mailbox/folder
- filename: `{subject}-{id}.md`

## frontmatter

title (subject), id, created (date sent), modified, source (message:// deep link), from, to, cc, mailbox

## body

Plain text or converted HTML email body. Attachments listed at the bottom.

## tips

- use `message://` URL from frontmatter to open in Apple Mail
- search by sender with `Grep` for `from:` field
- thread conversations share similar subjects
