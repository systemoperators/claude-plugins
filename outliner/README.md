# Outliner for Claude Code

Outliner is a Mac app that keeps a private index of your Apple Notes, Reminders, Calendar, Contacts, Messages and Mail on your own Mac. This plugin teaches Claude Code to use it. Claude can find what you wrote, read a note whole, see what is due today and who is waiting on your reply, and save a note, a reminder or an event through the Apple apps.

You need Outliner Pro on the Mac where Claude Code runs: https://outliner.app/download. It installs the `outliner` command.

## What the plugin holds

One skill, which tells Claude how to use the `outliner` command. Claude searches first and reads the whole note when a line is not enough. It links every note, reminder or message it names, and dry runs a write it is not sure of. The plugin has no MCP server and no hooks.

## What it runs

The `outliner` command, through Claude Code's shell. The skill lets Claude run Outliner's read commands (search, fetch and the lists) without asking each time. Every write asks first, as Claude Code usually does, and a delete, a send or a share also stops in Outliner itself until you say yes.

The command reads the index on your Mac and sends nothing to any server. Writes go through the Apple apps and can be undone from Outliner. What Claude reads reaches Claude like anything else in your conversation.

It works in Claude Code on a Mac. In Claude chat and Cowork the skill can only point you to Outliner.

## Install

Add Outliner from Claude's directory, or in Claude Code:

```
/plugin marketplace add systemoperators/claude-plugins
/plugin install outliner@system-operator
```

Privacy policy: https://outliner.app/privacy
