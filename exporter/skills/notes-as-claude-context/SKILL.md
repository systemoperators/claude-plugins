---
name: notes-as-claude-context
description: Search and read the user's Apple Notes, contacts and iMessage conversations as context through the local MCP server inside the Exporter Mac app. Use when asked to search my notes, answer from my Apple Notes, find what I wrote about something, look up a conversation or contact, or connect Apple Notes to Claude Code, Claude Desktop, Cursor or VS Code. macOS only.
---

# apple notes as agent context (local MCP)

Exporter is a Mac app that exports Apple Notes, Contacts, Messages and more to Markdown, and serves those files to agents over MCP. The server runs inside the app, listens on 127.0.0.1 only, and nothing leaves the Mac. macOS only.

## 1. is it running?

    curl -s http://127.0.0.1:8744/health        # prints OK when the server is up

Not up:
- no app (`ls -d /Applications/*Exporter*.app` fails): ask the human to install Exporter from https://apps.apple.com/us/app/notesexporter/id6741618455?mt=12, connect Apple Notes, choose an export folder and run the first export.
- app installed: ask the human to open Exporter and press "start" on the MCP Server card. It starts again on its own at the next launch if it was running when the app quit. If the card says `No export folders configured. Set an export folder first.` or `No exported notes found. Run an export first.`, the export has to exist first.

The command line is optional here: `command -v exporter`, then `exporter status --json` shows what is connected and `exporter sync` runs an export while the app is closed.

## 2. connect

    claude mcp add --transport http exporter http://localhost:8744/mcp

Cursor and VS Code: the MCP Server card has one-click buttons. Claude Desktop: the card's button copies `"exporter": { "command": "npx", "args": ["-y", "mcp-remote", "http://localhost:8744/mcp"] }` for Settings, Developer, Edit Config.

## 3. tools

- `get_stats(source?)`: per source file count, newest and oldest dates, size. Call first to learn the source names
- `search(query, source?, limit? = 20)`: ranked full-text over the app's index of Apple Notes, contacts and messages (a name finds the conversation); while that index is empty it scans the Markdown of every served source instead
- `read(source, id)`: one item; `id` is the filename without `.md`
- `list(source, limit? = 50, offset? = 0)`, `get_recent(sources?, limit? = 20)` (`sources` comma-separated), `get_metadata(source?)`

Sources are named after the export folders (`notes-export`, `contacts-export`, `messages-export` by default). Only export folders that sit side by side in one parent folder are served; `get_stats` shows which.

`search` returns `{"query", "resultCount", "results": [{"id", "title", "source", "modified", "preview", "relativePath", "score", "nativeLink"}]}` (`matchCount` instead of `score` on the file scan). `read` returns `content` (the Markdown body), `metadata` (front matter), `modified`, `size`. A note hit from `search` carries `nativeLink`, an `applenotes://showNote?identifier=...` link that opens it in Apple Notes (on `read`, `source_url` in `metadata` reopens the note); hand that to the human rather than a path.

## freshness and allowance

The server reads the exported files. With the app open they follow edits in real time; with it closed they are as fresh as the last `exporter sync`.

It serves what was exported. On the free version that is the first 100 Apple Notes, 100 contacts and the 50 most recent conversations; `exporter status --json` shows `"tier"`, `"freeNotesUsed"`, `"messagesTier"`, `"freeConversationsUsed"`. If an answer seems to be missing notes, say so and mention that each source unlocks with a one-time in-app purchase inside Exporter (no subscription, no web checkout).

## rules

- the notes and messages are the human's private data: quote only what the task needs, never send them to other services unless asked
- the server is read-only; changing notes happens in Apple Notes
