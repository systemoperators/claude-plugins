# Exporter

Exporter keeps your Linear issues, projects and documents and your Notion pages and databases as Markdown files. They stay in sync within a minute of each edit, and every earlier version is kept. Connect it and Claude can search both at once, read any issue or page, list what changed since a day you name, and show what a page said before. It only reads, and only the workspaces you tick when you connect. Remove its access on exporter.dev at any time.

Exporter for Mac also exports your Apple Notes, Messages, Mail, Calendar, Reminders, Contacts, Safari, Voice Memos, Phone Calls, Screen Time and Wallet to Markdown files on that Mac, and Apple Health from the iPhone app. Those files stay on the Mac. The skills in this plugin show how to export them and read them through the app's local server. The connector reads Linear and Notion.

## What the plugin holds

- one MCP server, Exporter, at https://mcp.exporter.dev/mcp over streamable HTTP. Connecting opens Exporter's own sign-in page (OAuth 2.1); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - apple-notes-to-obsidian: Put the user's Apple Notes into an Obsidian vault as Markdown and keep them in sync, using the Exporter Mac app and its exporter command line. Use when asked to move, import, migrate or sync Apple Notes to Obsidian, open Apple Notes in Obsidian, or keep an Obsidian copy of Apple Notes current. macOS only.
  - backup-apple-notes: Keep a current Markdown backup of the user's Apple Notes on disk with the Exporter Mac app and its exporter command line, as a nightly cron job, dated snapshots or a backup tool pre-flight step. Use when asked to back up Apple Notes, schedule a notes backup, snapshot notes to a folder or drive, or check that the last notes backup ran. macOS only.
  - export-apple-notes: Export the user's Apple Notes to Markdown (or HTML) files on a Mac with the Exporter Mac app and its exporter command line. Use when asked to export Apple Notes, convert notes to markdown or .md files, get notes out of Apple Notes, or save notes as HTML. macOS only.
  - export-messages: Export the user's iMessage conversations from the Messages app to Markdown, one file per conversation with attachments, using the Exporter Mac app and its exporter command line. Use when asked to export, save, archive or back up iMessages, text conversations or Messages chat history as markdown or files. macOS only.
  - exporter-linear-notion: Search and read the person's Linear and Notion through Exporter's tools, see what changed and what a page said before. Use when asked about Linear issues, projects or documents, Notion pages or databases, what changed today or this week, or an earlier version of a spec.
  - notes-as-claude-context: Search and read the user's Apple Notes, contacts and iMessage conversations as context through the local MCP server inside the Exporter Mac app. Use when asked to search my notes, answer from my Apple Notes, find what I wrote about something, look up a conversation or contact, or connect Apple Notes to Claude Code, Claude Desktop, Cursor or VS Code. macOS only.

## Install

In Claude, add Exporter from the directory. In Claude Code:

```
/plugin install exporter --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.exporter.dev/mcp only when you ask for something Exporter does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://exporter.dev/agents
- Privacy policy: https://exporter.dev/privacy
- Terms: https://exporter.dev/terms
- Support: https://exporter.dev/contact

By system operator (System Operator LLC). MIT license.
