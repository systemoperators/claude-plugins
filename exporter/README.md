# Exporter

Exporter keeps your Linear issues, projects and documents and your Notion pages and databases as Markdown files. They stay in sync within a minute of each edit, and every earlier version is kept. Connect it and Claude can search both at once, read any issue or page, list what changed since a day you name, and show what a page said before. It only reads, and only the workspaces you tick when you connect. Remove its access on exporter.dev at any time.

## What the plugin holds

- one MCP server, Exporter, at https://mcp.exporter.dev/mcp over streamable HTTP. Connecting opens Exporter's own sign-in page (OAuth 2.1); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - exporter-linear-notion: Search and read the person's Linear and Notion through Exporter's tools, see what changed and what a page said before. Use when asked about Linear issues, projects or documents, Notion pages or databases, what changed today or this week, or an earlier version of a spec.

## Install

In Claude, add Exporter from the directory. In Claude Code:

```
/plugin install exporter --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.exporter.dev/mcp only when you ask for something Exporter does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://exporter.dev/agents
- Privacy policy: https://exporter.dev/privacy
- Terms: https://exporter.dev/terms
- Support: https://exporter.dev/contact

By system operator (System Operator LLC). MIT license.
