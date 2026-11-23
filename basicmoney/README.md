# Basic Money

Basic Money reads your bank, credit card and brokerage statements from their PDFs. It lists every transaction and checks that each statement's opening balance and transactions come to its closing balance, or says by how much it is off. Save the result as Excel or CSV. It reads statements from banks in the US, the UK, India, South Africa and more, and a statement locked with a password opens on its upload page. No account is needed, and what it reads is deleted after 24 hours.

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
