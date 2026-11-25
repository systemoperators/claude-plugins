# Outliner for Claude

Outliner is a Mac app that keeps a private index of your Apple Notes, Reminders, Calendar, Contacts, Messages and Mail on your own Mac. This plugin connects Claude to it: Claude finds what you wrote, reads a note, sees what is due today, and saves a note, a reminder or an event for you through the Apple apps.

You need Outliner Pro on your Mac: https://outliner.app/download

What the plugin adds:

- the Outliner connector, https://mcp.outliner.app/mcp: Claude on the web, on iPhone and in Cowork reaches your Mac through it. You sign in with the same Outliner account as on the Mac, and turn on Settings › AI › Use Outliner from Claude and ChatGPT there. Your Mac answers; Outliner's servers pass the request through and never keep what it says
- a skill for the connector's tools: search first, fetch the whole item, dry run a change you are not sure of
- a skill for Claude Code on the same Mac, which runs the `outliner` command Outliner Pro installs. Claude Code asks before each command

A send, a share or a delete asks for your yes in the chat before it runs. Locked notes are never read, and lines Outliner marks private come back as dots.

Privacy policy: https://mcp.outliner.app/privacy

<!-- generated from outliner/src/claude/outliner and outliner/src/mcp/skills by outliner/scripts/gen-claude-plugin.mts; never edited by hand -->
