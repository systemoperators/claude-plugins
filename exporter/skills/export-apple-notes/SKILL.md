---
name: export-apple-notes
description: Export the user's Apple Notes to Markdown (or HTML) files on a Mac with the Exporter Mac app and its exporter command line. Use when asked to export Apple Notes, convert notes to markdown or .md files, get notes out of Apple Notes, or save notes as HTML. macOS only.
---

# export apple notes to markdown

Exporter is a Mac app ("Exporter: Notes to Markdown" on the App Store) with a command line, `exporter`. It writes one Markdown file per note. macOS only, everything stays on the Mac.

## 1. check the command

    command -v exporter

Not found? Look for the app: `ls -d /Applications/*Exporter*.app`
- no app: ask the human to install Exporter from https://apps.apple.com/us/app/notesexporter/id6741618455?mt=12, open it, connect Apple Notes and choose an export folder. The command line never prompts; every permission is granted in the app.
- app, no command: the sandboxed app cannot write to PATH, so the human pastes one line once. Ask them to open Exporter, press "copy install command" on the Command Line card and paste it in Terminal (it may use sudo).

Then `exporter doctor`. Exit 0 is ready. Exit 2: each `FAIL` line is followed by `fix:` with the step.

## 2. export

The export configured in the app (its export folder, its folder and tag selection), incremental:

    exporter sync --source apple --json --quiet

A one-off export to any folder inside one the human granted in the app (Command Line card, "add folder"; see `exporter list dests`):

    exporter export --dest ~/Backups/notes --json --quiet
    exporter export --dest ~/Backups/work --folder "Work" --format html
    exporter export --dest ~/Backups/notes --dry-run

Export flags: `--folder "Name"` and `--tag name` (repeatable; `list folders --json` and `list tags --json` show the names), `--organize folders|tags|smart`, `--format markdown|html`. `sync --full` removes only the files Exporter wrote and re-exports everything.

While the app is open, `sync` exports nothing and prints `Exporter is running: real-time sync is live, the export root is already current.` The files are already up to date.

## 3. read the result

`--json` prints a summary (`sync` wraps it as `{"runs": [...]}`); `--quiet` drops the progress lines so stdout is only JSON:

    {"attachmentIssues": 0, "durationSec": 2.4, "failed": 0, "format": "markdown",
     "root": "/Users/me/Backups/notes", "runError": null, "selected": 100,
     "source": "apple-notes", "status": "clean", "succeeded": 100}

Exit codes: 0 ok, 1 some notes failed or none were written, 2 not set up (folder not granted, source not connected, folder or tag not found; the stderr `error:` line says what to do), 64 bad flag.

Files land in `root`. A folder chosen at home level or one below it (~/Documents, ~/Backups) gets a `notes-export` subfolder; a deeper folder is used as is. Inside: one `.md` per note in the same folders as Apple Notes, images and files in an `attachments` folder next to the notes, YAML front matter (title, id, created, modified, source_url back to the note), and the run record in `.exporter/last-export.json`.

## free allowance

Free: the first 100 Apple Notes. Notes already exported keep re-syncing free; the limit only skips new ones. The run still exits 0 and prints, unless `--quiet`:

    note: 42 note(s) skipped: free version limit (100 of 100 free notes). upgrade in the app to export everything.

With `--quiet`, check `exporter status --json`: `"tier": "free"` and `"freeNotesUsed": 100` mean the allowance is used up.

Unlocking is a one-time in-app purchase inside Exporter, no subscription. Tell the human to buy it in the app; there is no web checkout or license key. The next run picks it up.

## rules

- the notes are the human's own data: show paths and counts, do not paste note contents anywhere unless asked
- use `sync --full` only when the human asks for a clean re-export
