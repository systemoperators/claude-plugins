# Bigmission

The books, taxes and dates of a one-person company, kept for you. Bigmission reads your bank, Stripe and the App Store, files every row, checks the books against each statement to the cent, and puts what needs you on one list.

Connect it here and ask: how the month is going and how much cash there is, what you paid someone and how each row is filed, the profit and loss of a month or a year, what each product brought in after fees and costs, which dates are coming up, whether you owe estimated tax, and whether your connections are syncing. Every answer is the number bigmission.com shows, with a link to the page.

Allow Read and File, and it can also suggest a category for a row, which waits for you to confirm on bigmission.com, and keep a receipt or invoice you hand it. It never moves money, connects an account or changes a category you chose.

## What the plugin holds

- one MCP server, Bigmission, at https://mcp.bigmission.com/mcp over streamable HTTP. Connecting opens Bigmission's own sign-in page (OAuth 2.1); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - bigmission: Answer questions about a company's books from Bigmission: cash, rows, statements, products, tax, dates and documents, and suggest categories or keep receipts when the person allows it.

## Install

In Claude, add Bigmission from the directory. In Claude Code:

```
/plugin install bigmission --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.bigmission.com/mcp only when you ask for something Bigmission does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://bigmission.com/docs/chatgpt-and-claude
- Privacy policy: https://bigmission.com/privacy
- Terms: https://bigmission.com/terms
- Support: https://bigmission.com/about

By system operator (System Operator LLC). MIT license.
