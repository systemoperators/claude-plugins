# tinysend

[ANTON'S WORDS: what it does, from docs/CHATGPT_PLUGIN.md: read how issues did, write drafts, send when asked (Claude asks first), add and remove subscribers; nothing about plans or prices]

## What the plugin holds

- one MCP server, tinysend, at https://mcp.tinysend.com/mcp over streamable HTTP. Connecting opens tinysend's own sign-in page (OAuth 2.1); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - tinysend-newsletters: Read how newsletters and issues did, write and edit drafts, send when asked, and manage subscribers in tinysend.
  - tinysend-onboarding: Start with tinysend: find the newsletters this connection may use and explain what sending does.

## Install

In Claude, add tinysend from the directory. In Claude Code:

```
/plugin install tinysend --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.tinysend.com/mcp only when you ask for something tinysend does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://tinysend.com
- Privacy policy: https://tinysend.com/privacy
- Terms: https://tinysend.com/terms
- Support: https://tinysend.com/contact

By system operator (System Operator LLC). MIT license.
