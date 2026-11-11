---
name: outliner
description: Answer from the person's own Apple notes, reminders, calendar, contacts, messages and mail through Outliner's tools on their Mac. Use when they ask what they wrote, planned, were sent or have due, or ask to save a note, a reminder or an event.
---

Outliner keeps an index of the person's Apple data on their Mac. Its tools read that index and write back through the Apple apps.

How to answer:

- Start with `search` for anything they wrote, were sent or planned; it answers lines, each with its path, two links and `item`, the note, mail or message the line is in. Then `fetch` that `item` when the line alone does not answer (`fetch` also takes `@today` for today's note, or a person's name).
- The lists take field filters: `list_reminders` (due today, overdue or a day; open or done), `list_events` (from and until), `list_messages` (state unreplied: who waits on a reply), `list_notes`, `list_mail`, `list_files`. For what is on today, ask `list_events` from today until today, `list_reminders` due today and overdue, and `list_messages` unreplied.
- When you name a row, write it as a markdown link to its `url` (or `links.apple`), else `links.outliner`, with the row's own title as the text.
- `create_note` takes `title` and `body`, or markdown for a formatted note: headings, lists, checklists, bold, links and tables. `append_to_note` adds lines to a note, `@today` for today's note.
- Every write takes `dry_run`. Use it when the person has not said exactly what to change. A write answers with the row's link: name that row the same way. A create takes `request_id`, so a retry makes it once.
- Deleting, sending a message and sharing answer what they would do and a confirm code first. Tell the person in words what will happen; call again with the code only after they say yes.
- A line Outliner marks private (credentials, card numbers, ids) comes back as dots. Do not ask to reveal it.
- When a step can only be done by the person, put it on its own line starting `For you:`.

If the tools are missing or answer that Outliner is not running, say that this needs the Outliner app for Mac (https://outliner.app) and stop: there is no other way to reach their Apple data.
