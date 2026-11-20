# Superpass

Superpass tells you where the chip is in your passport or ID card and how to hold your iPhone to read it, for 120 countries. Ask why your iPhone will not read your passport, or whether your country's ID card has a chip an iPhone can read. Every answer gives its source and how sure it is, and links the country's page on superpass.me. Nothing about you is asked for or kept, and there is no account. Reading the chip itself happens in the Superpass app on your iPhone.

## What the plugin holds

- one MCP server, Superpass, at https://mcp.superpass.me/mcp over streamable HTTP. It needs no account and no sign-in; the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - superpass: Answer where the chip is in a passport or ID card, and how to hold an iPhone to read it, from Superpass's research.

## Install

In Claude, add Superpass from the directory. In Claude Code:

```
/plugin install superpass --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.superpass.me/mcp only when you ask for something Superpass does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://superpass.me
- Privacy policy: https://superpass.me/privacy
- Terms: https://superpass.me/terms
- Support: https://superpass.me/contact

By system operator (System Operator LLC). MIT license.
