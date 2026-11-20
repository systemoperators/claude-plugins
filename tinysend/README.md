# Tinysend

Read how your newsletter issues did, who subscribed and who opened. Turn notes into a draft, change it, and send it when you ask: tinysend asks before every send, every new subscriber and every removal, and a sent email cannot be taken back. Your tinysend address gets a new label per site, so Claude can fill in a sign-up form and read the code the site sends, and only mail to a label is readable.

## What the plugin holds

- one MCP server, Tinysend, at https://mcp.tinysend.com/mcp over streamable HTTP. Connecting opens Tinysend's own sign-in page (OAuth 2.1); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - tinysend-newsletters: Read how newsletters and issues did, write and edit drafts, send when asked, and manage subscribers in tinysend.
  - tinysend-onboarding: Start with tinysend: find the newsletters this connection may use and explain what sending does.

## Install

In Claude, add Tinysend from the directory. In Claude Code:

```
/plugin install tinysend --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.tinysend.com/mcp only when you ask for something Tinysend does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://tinysend.com
- Privacy policy: https://tinysend.com/privacy
- Terms: https://tinysend.com/terms
- Support: https://tinysend.com/contact

By system operator (System Operator LLC). MIT license.
