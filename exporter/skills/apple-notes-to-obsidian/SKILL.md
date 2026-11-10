---
name: apple-notes-to-obsidian
description: Put the user's Apple Notes into an Obsidian vault as Markdown and keep them in sync, using the Exporter Mac app and its exporter command line. Use when asked to move, import, migrate or sync Apple Notes to Obsidian, open Apple Notes in Obsidian, or keep an Obsidian copy of Apple Notes current. macOS only.
---

# apple notes into obsidian, kept in sync

Exporter is a Mac app with a command line, `exporter`. It writes Apple Notes as Markdown with YAML front matter, which Obsidian reads as Properties. macOS only.

## 1. check the command

    command -v exporter

Not found? `ls -d /Applications/*Exporter*.app`
- no app: ask the human to install Exporter from https://apps.apple.com/us/app/notesexporter/id6741618455?mt=12 and open it once.
- app, no command: ask the human to open Exporter, press "copy install command" on the Command Line card and paste it once in Terminal (the sandboxed app cannot write to PATH; the line may need sudo).

Then `exporter doctor` (exit 0 ready, exit 2 prints a `fix:` under each `FAIL`).

## 2. point the export at the vault (in the app, once)

The command line never prompts, so the human does this in Exporter: connect Apple Notes, then choose as the Apple Notes export folder a dedicated folder inside the vault, for example `~/Obsidian/Vault/Apple Notes`. Keep the format Markdown (`exporter help sync` shows `apple currently: markdown`).

Use a dedicated subfolder, not the vault root, so the human's own notes and the export stay apart. `sync --full` removes only the files Exporter wrote before writing; anything else in the folder stays.

A folder at home level or one below it (~/Vault) gets a `notes-export` subfolder added; deeper folders are used as is.

## 3. export and keep it current

    exporter sync --source apple --json --quiet

- app open: it keeps the vault current on its own (real-time sync re-exports notes as they are edited). `sync` then prints `Exporter is running: real-time sync is live, the export root is already current.` Suggest launch at login and menu bar mode in the app's settings.
- app closed: schedule `sync`. `exporter help cron` prints the exact crontab line for this Mac, with the full path cron needs.

One-off export into a vault folder the human granted in the Command Line card ("add folder"):

    exporter export --dest ~/Obsidian/Vault/Apple\ Notes --format markdown --json --quiet

## 4. check the result

- `exporter status --json`: `"apple-notes": {"connected": true, "lastExport": "2026-09-11 03:00"}`
- JSON summary: `succeeded` of `selected`, `status` clean|warnings|failures, `root` is the folder written
- exit codes: 0 ok, 1 some notes failed, 2 not set up (stderr `error:` says what to do), 64 bad flag

In the vault: one `.md` per note in Apple Notes' folder tree, `attachments` next to the notes, `bases/` with `all-notes.base`, `photo-notes.base` and `all-attachments.base` views, and `.exporter/` run records. The app's Obsidian card opens the vault and installs a companion plugin (sync status, open a note back in Apple Notes).

## free allowance

The first 100 Apple Notes are free and keep syncing free. New notes past 100 are skipped; the run exits 0 and prints (not under `--quiet`):

    note: 42 note(s) skipped: free version limit (100 of 100 free notes). upgrade in the app to export everything.

`status --json` shows `"tier": "free"` and `"freeNotesUsed"`. Unlocking is a one-time in-app purchase inside Exporter, no subscription, no web checkout. Bear and Logseq export to Markdown free with no limit (`--source bear`, `--source logseq`).

## rules

- set the export folder or `--dest` to a dedicated subfolder of the vault, not the vault root
- do not paste note contents anywhere unless asked
