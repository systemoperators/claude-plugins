# Outliner for Claude

Outliner is a Mac app that keeps a private index of your Apple Notes, Reminders, Calendar, Contacts, Messages and Mail on your own Mac. This plugin connects Claude to it. Claude can find what you wrote, read a note, see what is due today, and save a note, a reminder or an event for you. Nothing leaves your Mac except what you ask Claude about.

You need Outliner Pro on your Mac: https://outliner.app/download

What the plugin adds:

- the Outliner MCP server (`outliner mcp --stdio`), the tools Claude calls: search and fetch, the lists (list_notes, list_reminders, list_events, list_messages and the rest), and one tool per write (create_note, create_reminder, complete_reminder, send_message and the rest)
- a skill that tells Claude how to use them: search first, link every row it names, and dry run a write it is not sure of. A delete, a send or a share answers with a confirm code, and Claude sends it back only after you say yes

What it runs: the `outliner` command the app installs. It sends nothing to any server. Writes go through the Apple apps and can be undone from Outliner.

Works in Claude Code and in Cowork on the Mac where Outliner Pro is installed. Install it from Claude's directory, or in Claude Code:

```
/plugin marketplace add systemoperators/claude-plugins
/plugin install outliner@system-operator
```

Outliner Pro adds the same plugin itself: Settings › Agents › Claude Code › Connect.

Privacy policy: https://outliner.app/privacy
