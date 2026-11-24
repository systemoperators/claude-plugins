# Supersurf

Supersurf tells you where and when to surf, at 2,435 surf spots in 46 countries. Ask where the surf is best tomorrow morning near a town, or how the waves and wind look at a spot this week. Ask when the tide is low, or where to take a lesson or rent a board. Each answer gives the wave height, the period and the wind in plain words. It says which forecast model the numbers come from and when they were made. No account is needed.

## What the plugin holds

- one MCP server, Supersurf, at https://mcp.supersurf.app/mcp over streamable HTTP. Connecting opens Supersurf's own sign-in page (OAuth 2.1); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - supersurf: Answer where and when to surf, a spot's forecast and tides, and the surf schools near it, from Supersurf's forecasts.

## Install

In Claude, add Supersurf from the directory. In Claude Code:

```
/plugin install supersurf --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.supersurf.app/mcp only when you ask for something Supersurf does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://supersurf.app
- Privacy policy: https://supersurf.app/privacy
- Terms: https://supersurf.app/terms
- Support: https://supersurf.app/contact

By system operator (System Operator LLC). MIT license.
