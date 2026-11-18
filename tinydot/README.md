# tinydot content plugin

Claude plugin for drafting, editing, reviewing, and publishing content on tinydot sites.

## what it does

- teaches Claude how tinydot works: markdown extensions, wikilinks, content blocks, embeds, frontmatter, customization
- works through the local filesystem (tinydot macOS app FileProvider) - no MCP needed
- changes publish instantly when files are saved

## install

```
claude plugin install tinydot
```

Or during development:

```
claude --plugin-dir ./claude-plugin
```

## commands

- `/tinydot:draft [topic]` - create a new page in a tinydot site
- `/tinydot:edit [page]` - edit an existing page
- `/tinydot:review [site]` - review site content for broken links, missing frontmatter, tag issues
- `/tinydot:customize [site]` - modify site colors, menus, template, spacing through frontmatter

## auto-invoked skill

The `tinydot-content` skill activates automatically when you ask about tinydot content, markdown, wikilinks, embeds, or site customization. It provides Claude with complete knowledge of tinydot's features and conventions.

## documentation

- docs.tinydot.com/getting-started
- docs.tinydot.com/markdown
- docs.tinydot.com/wikilinks
- docs.tinydot.com/customization

Privacy: https://tinydot.com/privacy

<!-- generated from tinydot/claude-plugin by tinydot/scripts/gen-claude-plugin.mts; never edited by hand -->
