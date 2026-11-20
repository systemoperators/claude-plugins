# Borders

Borders tells you how long the wait is at a land border crossing or an airport's passport control, from the border agencies' own numbers and drivers' phones. Ask how long the line is at Medyka now, or when the wait is usually shortest at San Ysidro on Saturday. Tell it when you need to be through, and it says when to join the line. It also ranks the crossings into a country by the drive from your town plus the wait. Every number says who made it and when. No account is needed.

## What the plugin holds

- one MCP server, Borders, at https://mcp.borders.me/mcp over streamable HTTP. It needs no account and no sign-in; the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - borders: Answer how long the wait is at a border crossing or an airport, when it is usually short, when to join the line and which crossing to take.

## Install

In Claude, add Borders from the directory. In Claude Code:

```
/plugin install borders --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.borders.me/mcp only when you ask for something Borders does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://borders.me
- Privacy policy: https://borders.me/privacy
- Terms: https://borders.me/terms
- Support: https://borders.me/contact

By system operator (System Operator LLC). MIT license.
