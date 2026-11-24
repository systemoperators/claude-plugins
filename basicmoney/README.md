# Basic Money

Basic Money converts bank, credit card and brokerage statement PDFs to Excel or CSV. It checks whether the transactions and opening balance come to the closing balance and shows any difference. The upload page also accepts PDFs locked with a password. You can convert statements and look up bank guides without an account. Conversion results expire after 24 hours. Sign in to open your Basic Money library. Statements you convert from a PDF attached in chat while signed in are saved to your library.

## What the plugin holds

- one MCP server, Basic Money, at https://mcp.basicmoney.app/mcp over streamable HTTP. Connecting opens Basic Money's own sign-in page (OAuth 2.1); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - basicmoney: Turn bank, credit card and brokerage statement PDFs into transactions as Excel or CSV, checked to add up, and say how to download statements from a bank.

## Install

In Claude, add Basic Money from the directory. In Claude Code:

```
/plugin install basicmoney --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.basicmoney.app/mcp only when you ask for something Basic Money does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://basicmoney.app
- Privacy policy: https://basicmoney.app/privacy
- Terms: https://basicmoney.app/terms
- Support: https://basicmoney.app/contact

By system operator (System Operator LLC). MIT license.
