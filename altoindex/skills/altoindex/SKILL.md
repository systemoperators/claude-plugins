---
name: altoindex
description: Use when the user asks about their personal data, Apple Notes, Reminders, Calendar, Contacts, Messages, Safari bookmarks or history, Voice Memos, or Granola meetings. Also use when the user references alto.index or alto-index data.
allowed-tools: Read, Glob, Grep
---

# alto.index Data

alto.index is a macOS app that syncs data from Apple apps to `~/Documents/alto-index/` as markdown files. This skill teaches you how to work with the synced data.

## Base Path

All data lives in `~/Documents/alto-index/`. Each data source has its own subfolder with a `CLAUDE.md` containing source-specific details. Always read the relevant `CLAUDE.md` first when working with a source you haven't seen yet.

## Native App Links

Most exported files contain deep links back to the original item in the native macOS app. When referencing any item, always include the native link so the user can click through to the source app. The link is typically in the frontmatter `link` or `source` field, or at the bottom of the file body. Supported link schemes: `notes://`, `x-apple-reminder://`, `addressbook://`, `calshow:`.

## Data Sources

### notes/

Apple Notes exported as markdown files.

- path: `notes/{folder}/{title}.md`
- folders match Apple Notes folder names, nested folders supported
- frontmatter: title, id, created, modified, folder, attachments, links, source
- deep link: `notes://showNote?identifier={uuid}` (in `source` field)
- body contains the note content in markdown, with a link back to the original note at the bottom

### reminders/

Apple Reminders (active/non-completed only).

- path: `reminders/{list}/{title}.md`
- lists match Apple Reminders list names
- frontmatter: title, reminder_id, list, priority (none/low/medium/high), flagged, url, images, created_date, modified_date, link
- deep link: `x-apple-reminder://{reminder_id}` (in `link` field)
- body may contain URLs and images sections

### calendar/

Apple Calendar events.

- path: `calendar/{calendar-name}/{YYYY-MM-DD}/{event}.md`
- organized by calendar name, then by date
- frontmatter: title, event_id, calendar, start_date, end_date, all_day, location, url, organizer, attendees (list with name/status/role), status, availability, alarms, recurrence, created_date, modified_date, link
- deep link: `calshow:{timeIntervalSinceReferenceDate}` (in `link` field)
- body includes time/location info, notes, and attendee list

### messages/

iMessage conversations.

- path: `messages/{contact-or-group-name}.md`
- one file per conversation (individual or group chat)
- frontmatter: title, chat_id, participants (array), is_group, message_count, first_message, last_message
- messages are in chronological order within each file
- contact names resolved from Contacts when available (shows "Name (phone/email)")
- attachments noted inline where media was sent

### contacts/

Apple Contacts.

- path: `contacts/{name}.md`
- flat folder, no subfolders
- frontmatter: title, contact_id, link, last_modified
- deep link: `addressbook://{contact_id}` (in `link` field)
- body contains structured sections: phone numbers, email addresses, physical addresses, birthdays, notes, social profiles
- use contacts to resolve names in messages and calendar events

### safari-bookmarks/

Safari bookmarks as markdown lists.

- path: `safari-bookmarks/{folder}.md`
- each Safari bookmark folder exported as a separate markdown file
- no frontmatter - content is markdown lists with clickable links
- nested folders represented as subsections with ## headings

### safari-history/

Safari browsing history grouped by day and hour.

- path: `safari-history/{YYYY-MM-DD}.md`
- one file per day
- no frontmatter - starts with `# Safari History - {date}` and total visit count
- grouped by hour (## HH:00 - HH:59 headings), latest first
- each entry: time, linked title, visit count if > 1

### voice-memos/

Voice Memos recordings.

- path: `voice-memos/index.md` (table of all recordings) + `.m4a` audio files
- index.md contains a markdown table with columns: Recording, Date, Duration, Size, Link
- audio files are in `.m4a` format alongside the index
- no frontmatter on individual files - the index is the main entry point

### granola/

Granola meeting notes.

- path: `granola/{YYYY-MM-DD}-{title}.md`
- flat folder with date-prefixed files
- no frontmatter - content starts with `# title` heading
- contains: meeting title, date, participants, overview, AI summary, your notes, full transcript
- `granola/index.md` lists all meetings

### Not yet available

- `mail/` - Apple Mail (coming soon, placeholder only)
- `screenshots/` - Screenshots (coming soon, placeholder only)

## Working with the Data

### Reading data
- use Glob to find files: `~/Documents/alto-index/notes/**/*.md`
- use Grep to search across sources: search in `~/Documents/alto-index/`
- read individual files with Read tool
- always check for a CLAUDE.md in the subfolder for source-specific guidance

### Cross-referencing
- contact names in reminders/calendar/messages can be resolved via contacts/
- dates can be cross-referenced across calendar, reminders, notes (by modified date), safari history, and granola meetings
- reminder URLs may link to relevant websites or resources
- safari history can provide context for what you were researching on a given day

### Deep links
- notes: `notes://showNote?identifier={uuid}`
- reminders: `x-apple-reminder://{reminder_id}`
- contacts: `addressbook://{contact_id}`
- calendar: `calshow:{timeIntervalSinceReferenceDate}`
- always include deep links when referencing items so the user can jump to the native app

### Privacy
- this is personal data - handle with care
- don't expose contact details or private notes unnecessarily
- summarize rather than dump raw content when possible
