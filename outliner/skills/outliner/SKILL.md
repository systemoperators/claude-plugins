---
name: outliner
description: Answer from the person's own Apple notes, reminders, calendar, contacts, messages and mail with Outliner on their Mac, and save notes, reminders and events through the Apple apps. Use when they ask what they wrote, planned, were sent or have due, who is waiting on their reply, or ask to save a note, a reminder or an event.
allowed-tools: Bash(outliner search:*), Bash(outliner fetch:*), Bash(outliner sources:*), Bash(outliner help:*), Bash(outliner commands:*), Bash(outliner note list:*), Bash(outliner folder list:*), Bash(outliner tag list:*), Bash(outliner reminder list:*), Bash(outliner event list:*), Bash(outliner message list:*), Bash(outliner mail list:*), Bash(outliner file list:*)
---

Outliner keeps an index of the person's Apple data on their Mac. The `outliner` command, which Outliner Pro installs, reads that index and writes back through the Apple apps.

Run it as `outliner <command> --json` in the shell. `outliner help <command>` shows a command's flags with examples, and `outliner commands --json` lists every command. Where Outliner's tools are connected instead of a shell, each command's help names its tool (`search`, `fetch`, `list_reminders`, `create_note` and the rest), with the same arguments.

Finding:

- Start with `outliner search "<words>" --json` for anything they wrote, were sent or planned. It answers lines, best first, each with its `path`, its `links` and `item`, the note, mail or message the line is in. Narrow it with `--kind`, `--person`, `--folder`, `--tag`, `--from` and `--state`.
- Then `outliner fetch <item> --json` when a line alone does not answer. It also takes a person's name, `@today` for today's note and `day:2026-11-07` for everything on a day. Fetch ids and names from an answer rather than guessing them.
- What is on today: `outliner event list --from now --until today`, `outliner reminder list --due today,overdue` and `outliner message list --state unreplied` (who waits on a reply).
- The lists answer `items` and `next`; pass `next` as `--cursor` for more.

Naming what you found: write each row as a markdown link to its `links.apple` (it opens in its own app), else `links.outliner`, with the row's own title as the text.

Writing:

- `note create` takes a title and `--body`, or markdown through `--body-file -` for a formatted note. `note append @today "<line>"` adds to today's note. `reminder create "<title>" --due "tomorrow 9:00"` and `event create "<title>" --at "2026-11-20 14:00"`; `--about` links either to the email, message or note it is about.
- Every write takes `--dry-run`. Use it when the person has not said exactly what to change. Give a create an `--idempotency-key`, so a retry makes it once. A write answers with the row's link: name it the same way.
- A delete, a send or a share stops before it runs and exits 5. Tell the person in words what will happen, and run it again with `--yes` only after they say yes.
- A line Outliner marks private (passwords, card numbers, ID numbers) comes back as dots. Do not try to reveal it.
- Exit codes: 2 the command or a flag is wrong (the message names the right one), 3 nothing by that name, 4 not in this version of Outliner, 5 needs the person's yes.
- When a step can only be done by the person, put it on its own line starting `For you:`.

If `outliner` is not found, or answers that Outliner is not running, say that this needs Outliner for Mac (https://outliner.app) and stop: there is no other way to reach their Apple data.
