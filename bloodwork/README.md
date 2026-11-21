# Bloodwork

Bloodwork keeps the blood test reports you add, each value with the range and flag your lab printed on that report. With this plugin, Claude can tell you how one of your values changed, what was out of range in your last test, and which tests you have added. It can also look up any marker: what it measures, the ranges named labs publish for it by sex and age, the tests in a panel, and the tests followed for a condition. It only reads. Bloodwork is not a medical device and gives no medical advice.

## What the plugin holds

- one MCP server, Bloodwork, at https://mcp.bloodwork.md/mcp over streamable HTTP. Connecting opens Bloodwork's own sign-in page (OAuth 2.1, Sign in with Apple or an email code); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - bloodwork-own-results: read the person's own reports, one marker over time, and what the lab flagged high or low
  - bloodwork-reference: look up what a marker measures, its published reference ranges, the tests in a panel and the tests followed for a condition

## Install

In Claude, add Bloodwork from the directory. In Claude Code:

```
/plugin install bloodwork --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.bloodwork.md/mcp only when you ask for something Bloodwork does, and the call carries only what that tool needs. It reads only the signed-in person's own reports. Data handling is in the privacy policy below.

## Links

- Documentation: https://bloodwork.md/agents
- Privacy policy: https://bloodwork.md/privacy
- Terms: https://bloodwork.md/terms
- Support: https://bloodwork.md/contact
