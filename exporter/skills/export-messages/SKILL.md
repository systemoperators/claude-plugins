---
name: export-messages
description: Export the user's iMessage conversations from the Messages app to Markdown, one file per conversation with attachments, using the Exporter Mac app and its exporter command line. Use when asked to export, save, archive or back up iMessages, text conversations or Messages chat history as markdown or files. macOS only.
---

# export imessage conversations to markdown

Exporter is a Mac app with a command line, `exporter`. It reads the Messages database on the Mac and writes one Markdown file per conversation. macOS only, everything stays on the Mac.

## 1. check the command

    command -v exporter

Not found? `ls -d /Applications/*Exporter*.app`
- no app: ask the human to install Exporter from https://apps.apple.com/us/app/notesexporter/id6741618455?mt=12 and open it.
- app, no command: ask the human to open Exporter, press "copy install command" on the Command Line card and paste it once in Terminal (the sandboxed app cannot write to PATH; the line may need sudo).

The command line never prompts. In the app, the human connects Messages (choosing `~/Library/Messages` itself) and a Messages export folder. Connecting Contacts too links each participant to their contact card.

Then `exporter doctor`: `ok    messages database readable (...)` means ready; a `FAIL` line is followed by its `fix:`.

## 2. export

Into the Messages export folder set in the app, incremental (only conversations that changed):

    exporter sync --source messages --json --quiet

Into another folder inside one the human granted in the app (Command Line card, "add folder"):

    exporter export --source messages --dest ~/Backups/messages --json --quiet
    exporter export --source messages --dest ~/Backups/messages --dry-run

Messages is always every conversation as Markdown: `--folder`, `--tag` and `--format html` are ignored with a note. The first run indexes the Messages database first (`messages: indexing…`), which is the slow part on a large history. `exporter list sources --json` shows `{"source": "messages", "connected": true, "conversations": 1532}`.

While the app is open, `sync` exports nothing and prints `Exporter is running: real-time sync is live, the export root is already current.`

## 3. read the result

JSON summary: `source` "messages", `selected`, `succeeded`, `failed`, `attachmentIssues`, `durationSec`, `format`, `root`, `status` (clean|warnings|failures), `runError`. `sync` wraps it as `{"runs": [...]}`.

Exit codes: 0 ok, 1 conversations failed or none written, 2 not set up (Messages not connected, folder not granted; stderr `error:` says what to do), 64 bad flag.

Files land in `root`: a folder at home level or one below it (~/Documents) gets a `messages-export` subfolder, deeper folders are used as is. One `.md` per conversation, media in `attachments/<chat id>/` (HEIC converted to JPEG), run records in `.exporter/`.

## free allowance

Free: the 50 most recent conversations, newest first. Those keep syncing free; older ones are skipped. The run still exits 0 and prints, unless `--quiet`:

    note: 1522 conversation(s) skipped: free version limit (50 of 50 free conversations). unlock messages in the app to export everything.

`exporter status --json` shows `"messagesTier": "free"` and `"freeConversationsUsed": 50`. Messages is its own one-time in-app purchase inside Exporter, separate from Apple Notes, no subscription, no web checkout. Tell the human; the next run picks it up.

## rules

- conversations are private, and other people's words too: report counts and paths, do not quote messages unless the human asks
- `sync --full` removes the files Exporter wrote, then writes every conversation again; use it only when asked
