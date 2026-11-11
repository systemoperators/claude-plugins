# Deepcalc

Ask about your spreadsheets in deepcalc and get answers from the actual cells: what a model assumes, whether a total leaves out a row, what happens to cash if growth changes. Claude reads your workbooks, runs the same checks as the Check tab in deepcalc, and tries numbers on a copy without writing anything. Give it an .xlsx or .csv and it opens it as a private workbook. When it changes cells, the changes go on a branch of their own, never into the workbook itself: you keep them or not in Changes, on the web or in deepcalc for Mac. Keeping a branch, deleting one and publishing ask you first, every time.

## What the plugin holds

- one MCP server, Deepcalc, at https://mcp.deepcalc.com/mcp over streamable HTTP. Connecting opens Deepcalc's own sign-in page (OAuth 2.1); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - deepcalc-onboarding: Connect to deepcalc on first use, find the person's workbooks and explain how changes wait on a branch.
  - deepcalc-workbooks: Read, check and change deepcalc workbooks, try numbers without writing, review branches and publish when asked.

## Install

In Claude, add Deepcalc from the directory. In Claude Code:

```
/plugin install deepcalc --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.deepcalc.com/mcp only when you ask for something Deepcalc does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://deepcalc.com
- Privacy policy: https://deepcalc.com/privacy
- Terms: https://deepcalc.com/terms
- Support: https://deepcalc.com/contact

By system operator (System Operator LLC). MIT license.
