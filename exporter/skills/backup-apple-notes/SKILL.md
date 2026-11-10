---
name: backup-apple-notes
description: Keep a current Markdown backup of the user's Apple Notes on disk with the Exporter Mac app and its exporter command line, as a nightly cron job, dated snapshots or a backup tool pre-flight step. Use when asked to back up Apple Notes, schedule a notes backup, snapshot notes to a folder or drive, or check that the last notes backup ran. macOS only.
---

# back up apple notes as markdown

Exporter is a Mac app with a command line, `exporter`. It works while the app is closed, with the folders and permissions granted in the app. macOS only.

## 1. check the command

    command -v exporter

Not found? `ls -d /Applications/*Exporter*.app`
- no app: ask the human to install Exporter from https://apps.apple.com/us/app/notesexporter/id6741618455?mt=12, open it, connect Apple Notes and choose an export folder.
- app, no command: ask the human to open Exporter, press "copy install command" on the Command Line card and paste it once in Terminal (the sandboxed app cannot write to PATH; the line may need sudo).

Then `exporter doctor` (exit 0 ready, exit 2 prints a `fix:` under each `FAIL`).

## 2. pick the shape

- a mirror that follows edits: the app's export folder. While the app runs, with its window open or closed, it re-exports notes as they change, and `sync` is then a no-op. When the app is closed, run `exporter sync` from cron. A mirror drops the files of notes deleted in Apple Notes (the summary says `N removed`), so it is not an archive.
- dated snapshots that never change: `export --dest` into a new folder each run. The human grants a parent folder once in the app (Command Line card, "add folder", for example `~/Backups`); the grant covers every subfolder.

## 3. schedule it

`exporter help cron` prints the crontab lines for this Mac with the full path. Cron's PATH may miss the install folder, so copy the lines it prints rather than typing the bare command, and never call the app binary itself (a suspended run then reports exit 19 while it keeps writing). The two shapes:

    0 3 * * * <path from help cron> sync
    0 3 * * * <path from help cron> export --dest ~/Backups/notes-$(date +\%F)

Escape `%` as `\%` in crontab. For both formats, give each its own folder: `--dest ~/Backups/notes-md --format markdown` and `--dest ~/Backups/notes-html --format html`.

Backup tools such as Carbon Copy Cloner: run `exporter sync` as the pre-flight script and branch on the exit code. The command stays attached until the export finishes, even with no one logged in.

## 4. verify

    exporter log --last 5 --json

Each entry: `source`, `finishedAt` ("2026-09-11 03:00"), `selected`, `succeeded`, `failed`, `format`, `status` (clean|warnings|failures), `destination`, `prunedFiles`, `runError`. `log` reads the app's export folders and the granted folders themselves, not dated subfolders under them: for a snapshot, read `<root>/.exporter/last-export.json`, where `root` comes from the export's JSON summary.

Exit codes: 0 ok, 1 notes failed or none written, 2 not set up (folder not granted, source not connected; stderr `error:` says what to do), 64 bad flag. `sync --json --quiet` and `export --json --quiet` print only the JSON summary (`root` is the folder written).

## free allowance

The first 100 Apple Notes are free, and those keep backing up free forever. Notes past the first 100 are skipped; the run exits 0 and prints (not under `--quiet`):

    note: 42 note(s) skipped: free version limit (100 of 100 free notes). upgrade in the app to export everything.

`exporter status --json` shows `"tier": "free"` and `"freeNotesUsed"`. Unlocking is a one-time in-app purchase inside Exporter, no subscription, no web checkout; tell the human so a nightly backup is not silently partial.

## rules

- ask before adding a crontab line; show the exact line first
- `sync --full` removes the files Exporter wrote in the export folder, then writes everything again; use it only when asked
