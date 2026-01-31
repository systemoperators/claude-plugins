---
description: Daily briefing from your alto.index data
allowed-tools: Read, Glob, Grep
---

Build a daily briefing from alto.index data. Today's date should be determined from the system.

Read the following in parallel to build the briefing:

1. Reminders due today: search `~/Documents/alto-index/reminders/` for files with `due_date` matching today
2. Notes modified today: use Glob to find `~/Documents/alto-index/notes/**/*.md` and check which have today's date in `modified` frontmatter
3. Granola meetings today: look for files matching `~/Documents/alto-index/granola/{today's date}*.md`
4. Calendar events today: check `~/Documents/alto-index/calendar/` for today's date folders
5. Voice memos today: check `~/Documents/alto-index/voice-memos/index.md` for today's recordings
6. Safari history today: check `~/Documents/alto-index/safari-history/{today's date}.md`

Present the briefing in this format:

```
# Today - {date}

## Calendar
{events or "no events synced yet"}

## Reminders Due
{due reminders with deep links, or "none due today"}

## Notes Updated
{recently modified notes with deep links}

## Meetings
{granola meetings or "none"}

## Messages
{recent conversations or "none"}

## Browsing
{safari history highlights or "none"}
```

Include deep links (notes://, x-apple-reminder://, addressbook://, calshow:) so the user can click through to native apps. Keep it concise - one line per item.
