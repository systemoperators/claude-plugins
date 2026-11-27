# Folder

Use the files in your Folder folders in Claude. Find files by name, read them, and answer from what they say. Save a summary of the chat as a new file, save a file you uploaded, or edit the text of one.

Every change is a new version in the file's history, so any of it can be put back. Make a share link for any file; Claude asks you before a link reaches anyone. Nothing is deleted or moved.

Sign in with Apple or Google and choose which folders Claude can use, and whether it may change them. New to Folder? Start without an account: a folder for 24 hours, kept any time with Apple or Google.

## What the plugin holds

- one MCP server, Folder, at https://mcp.folder.dev/mcp over streamable HTTP. Connecting opens Folder's own sign-in page (OAuth 2.1); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - folder-artifacts: Publish a page you wrote to Folder as an artifact, share it, read and wait for the notes people leave on it, and change it with a new version.
  - folder-files: Find, read, save and edit files in Folder, bring in a file from the chat or the computer, see a file's history and put a version back.
  - folder-onboarding: Start with Folder: the folders this connection reaches, reading or changing, connecting again, guest folders, the apps, and undo.
  - folder-selling: Sell or give away files and folders from Folder: connect Stripe, what can be sold, prices, free downloads and emails, previews, changes, and how a product did.
  - folder-sharing: Share a file or a folder from Folder with a link: anyone with the link, a password, anyone, an end date; stop a link; and where company sharing and invites are set.
  - folder-websites: Put a folder from Folder online as a website, at a free name on folder.dev or at a domain the person owns, and take it down.

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
