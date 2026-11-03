# system operator Claude plugins

Claude Code plugin marketplace by [system operator](https://systemoperator.com).

## Install

In Claude Code, go to Browse Plugins > Add marketplace from GitHub and enter: `https://github.com/systemoperators/claude-plugins`

## Plugins

### alto.index

Work with your macOS app data synced by [alto.index](https://altoindex.com) ([download from Mac App Store](https://apps.apple.com/us/app/alto-index/id6746674846?mt=12)).

Commands:
- `/altoindex:today` - daily briefing across all sources
- `/altoindex:search [query]` - search across all sources
- `/altoindex:summary [source]` - summarize a data source
- `/altoindex:notes [query]` - browse or search Apple Notes
- `/altoindex:reminders [list]` - browse Apple Reminders
- `/altoindex:calendar [date]` - browse Apple Calendar events
- `/altoindex:messages [contact]` - browse iMessage conversations
- `/altoindex:contacts [name]` - look up a contact
- `/altoindex:safari [query]` - browse Safari bookmarks and history
- `/altoindex:meetings [query]` - browse Granola meeting notes
- `/altoindex:voice-memos` - browse Voice Memos recordings

### tinydot

Draft, edit, review, and publish content on [tinydot](https://tinydot.com) sites.

Commands:
- `/tinydot:draft [topic]` - create a new page
- `/tinydot:edit [page]` - edit an existing page
- `/tinydot:review [site]` - review site content for issues
- `/tinydot:customize [site]` - modify site appearance
- `/tinydot:sites` - list sites with URLs and page counts
- `/tinydot:import [url]` - import an external website into a tinydot site

### Superclock

Real alarms on your iPhone, set from a conversation, with [Superclock](https://superclock.app). Connects to Superclock's MCP server at `https://mcp.superclock.app/mcp` (sign in on Superclock's own page), with skills for setting, changing and removing alarms. See [superclock/README.md](superclock/README.md).

### Folder

Find, read, save and edit files in your [Folder](https://folder.dev) folders. Connects to Folder's MCP server at `https://mcp.folder.dev/mcp` (sign in on Folder's own page and choose the folders it may use), with skills for working with files and setting up. See [folder/README.md](folder/README.md).
