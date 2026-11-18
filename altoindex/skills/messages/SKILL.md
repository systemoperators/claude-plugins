---
name: messages
description: Search and read iMessage conversations
argument-hint: [contact name or search query]
paths:
  - "**/alto-index/messages/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- messages

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

iMessage and SMS conversations exported by Alto Index to:
  <alto-index>/messages/


## layout

- one file per chat/conversation
- filename: `{contact-name}.md` or `{group-name}.md`
- group chats include all participant names

## frontmatter

title (contact or group name), id (chat identifier), created, modified, source (imessage:// deep link), participants, message_count

## body

Chronological message log with timestamps and sender labels. Format:
```
**Sender** (2025-01-15 14:30): Message text here
```

Attachments referenced inline. Reactions and tapbacks noted where available.

## tips

- search for a person's messages by grepping their name in messages/
- group chats have multiple participants listed in frontmatter
- phone numbers may appear as identifiers for non-iMessage contacts
- cross-reference with contacts/ for full contact details
