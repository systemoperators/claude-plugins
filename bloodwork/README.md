# Bloodwork Reference

Look up any blood test: what a marker measures, its LOINC code and sample, the reference ranges named labs publish for it (ARUP, Mayo Clinic Laboratories, LabCorp, ABIM) by sex and age, and what a high or low result can be associated with; the tests in a lab panel; and the blood tests followed for a condition, with a guideline's monitoring plan where one is cited. The same words as the pages of bloodwork.md, each answer with its page. No account and no personal data: it never takes your values. Bloodwork is not a medical device and gives no medical advice.

## What the plugin holds

- one MCP server, Bloodwork Reference, at https://mcp.bloodwork.md/mcp over streamable HTTP. Connecting opens Bloodwork Reference's own sign-in page (OAuth 2.1); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - bloodwork-own-results: Read the person's own blood test results in Bloodwork: their reports, one marker over time, and what the lab flagged high or low.
  - bloodwork-reference: Look up blood tests in the Bloodwork reference: what a marker measures, its published reference ranges, the tests in a panel and the tests followed for a condition.

## Install

In Claude, add Bloodwork Reference from the directory. In Claude Code:

```
/plugin install bloodwork-reference --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.bloodwork.md/mcp only when you ask for something Bloodwork Reference does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://bloodwork.md/agents
- Privacy policy: https://bloodwork.md/privacy
- Terms: https://bloodwork.md/terms
- Support: https://bloodwork.md/contact

By system operator (System Operator LLC). MIT license.
