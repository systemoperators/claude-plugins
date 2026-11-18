---
name: people
description: Look up a person across all sources (messages, calls, contacts, calendar, notes)
argument-hint: [person name]
paths:
  - "**/alto-index/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- people

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Cross-source person lookup across all Alto Index exports at:
  <alto-index>/

## how to use

Given a person's name, search across all sources to build a complete picture:

1. contacts/ — full contact card (phone, email, address, organization)
2. messages/ — conversation history
3. calls/ — call history (by-contact/ folder)
4. calendar/ — shared events and meetings
5. granola/ — meeting transcripts mentioning them
6. notes/ — notes mentioning them
7. mail/ — email threads

## search strategy

```
# find all mentions of a person
Grep "Person Name" <alto-index>/

# check their contact card
Glob "<alto-index>/contacts/*person-name*"

# find their messages
Glob "<alto-index>/messages/*person-name*"

# check call history
Glob "<alto-index>/calls/by-contact/*person-name*"
```

## tips

- start with contacts/ for the canonical name and identifiers
- phone numbers and emails link across messages, calls, and mail
- case-insensitive grep catches variations in name spelling
- calendar events list attendees — search for the person in calendar/
- granola transcripts have speaker labels
