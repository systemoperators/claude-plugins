# Tinydot

Write, edit, review and customize your tinydot sites with Claude. Every folder in the tinydot folder on your Mac (~/Library/CloudStorage/tinydot, from the tinydot app) is a site and every markdown file a page; a saved change publishes at once. Where that folder is not on the computer (Claude on the web or a phone, Cowork), the tinydot connector does the same work through tinydot's server.

## What the plugin holds

- one skill, tinydot-content: how tinydot reads markdown, wikilinks, embeds, frontmatter, settings.json and each template's look
- commands that work on the files in the tinydot folder, with no server and no sign-in: nothing leaves your Mac except what Claude itself is sent and the pages tinydot publishes
- Claude reads the folder on its own; it asks you before it writes or changes a file, and before /tinydot:import fetches a page
- one MCP server, tinydot, at https://mcp.tinydot.com/mcp, and the skill tinydot-sites that names its tools. Connecting opens tinydot's own sign-in page (OAuth 2.1), and you choose whether it may make changes; the plugin carries no key, token or password. A new page is a draft until you publish it, and publishing, taking a page down and deleting ask you first

## Install

In Claude Code:

```
/plugin install tinydot --marketplace systemoperators/claude-plugins
```

## Commands

- `/tinydot:sites`: your sites with their addresses and page counts
- `/tinydot:draft [topic]`: a new page in a site
- `/tinydot:edit [page]`: change an existing page
- `/tinydot:review [site]`: broken links, missing frontmatter, tag issues
- `/tinydot:customize [site]`: menus, lists and pages in settings.json, the template's colors in the root index.md
- `/tinydot:import [url]`: bring an existing website into a tinydot site

## Documentation

- https://docs.tinydot.com/getting-started
- https://docs.tinydot.com/markdown
- https://docs.tinydot.com/customization

Privacy: https://tinydot.com/privacy

<!-- generated from tinydot/claude-plugin by tinydot/scripts/gen-claude-plugin.mts; never edited by hand -->
