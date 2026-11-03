# Folder

Use the files in your Folder folders in Claude. Find files by name, read them, and answer from what they say. Save a summary of the chat as a new file, save a file you uploaded, or edit the text of one.

Every change is a new version in the file's history, so any of it can be put back. Make a share link for a file in a folder in your own Cloudflare; Claude asks you before a link reaches anyone. Nothing is deleted or moved.

Connect your Folder account and choose which folders Claude can use, and whether it may change them.

## What the plugin holds

- one MCP server, Folder, at https://mcp.folder.dev/mcp over streamable HTTP. Connecting opens Folder's own sign-in page (OAuth 2.1); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - folder-files: Find, read, save and edit files in Folder, see their history, put a version back and share a link when asked.
  - folder-onboarding: Start with Folder: see which folders this connection reaches and how changes and undo work.

## Install

In Claude, add Folder from the directory. In Claude Code:

```
/plugin install folder --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.folder.dev/mcp only when you ask for something Folder does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://folder.dev
- Privacy policy: https://folder.dev/privacy
- Terms: https://folder.dev/terms
- Support: https://folder.dev/about

By system operator (System Operator LLC). MIT license.
