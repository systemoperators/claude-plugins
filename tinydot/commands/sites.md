---
name: sites
description: List tinydot sites with their URLs and page counts
allowed-tools: Read, Glob, LS
---

# list tinydot sites

Show an overview of the user's tinydot sites. Follow these steps:

1. list folders in `~/Library/CloudStorage/tinydot/` - each top-level folder is a site
2. for each site folder:
   - read its root `settings.json` and `index.md` frontmatter for its settings and look
   - count `.md` files using Glob for `**/*.md`
   - count total files using Glob for `**/*`
   - note the subdomain: folder name becomes `foldername.tinydot.com`
3. display a summary table with:
   - site name (folder name)
   - URL (`name.tinydot.com`)
   - page count (number of .md files)
   - total files
4. if user asks about a specific site, show more detail:
   - its settings (`settings.json`) and look (root `index.md` frontmatter); the template is on tinydot.com, not in the folder
   - list of pages with their titles and dates
   - tags used across the site

Use the tinydot-content skill for reference on site structure and metadata.
