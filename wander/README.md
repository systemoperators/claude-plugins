# Wander

Use your Wander notes in Claude. Search and read notes, summarize what you've written, and save conversations as new notes. Edit a section, append text, add images from a URL or an uploaded file, and organize notes into folders.

View your note history, see what changed and who changed it, and restore earlier versions. Changes save directly to Wander as new versions you can undo. Publish notes to the web when you want to share them. Publishing and deletion require your approval.

Connect your Wander account and choose which vaults Claude can access.

## What the plugin holds

- one MCP server, Wander, at https://mcp.wander.md/mcp over streamable HTTP. Connecting opens Wander's own sign-in page (OAuth 2.1); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - wander-notes: Search, read, create, edit and organize Wander notes, attach images, inspect history, undo changes and publish when asked.
  - wander-onboarding: Connect to Wander and choose a vault on first use, explaining how writes and undo work.

## Install

In Claude, add Wander from the directory. In Claude Code:

```
/plugin install wander --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.wander.md/mcp only when you ask for something Wander does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://wander.md
- Privacy policy: https://wander.md/privacy
- Terms: https://wander.md/terms
- Support: https://wander.md/contact

By system operator (System Operator LLC). MIT license.
