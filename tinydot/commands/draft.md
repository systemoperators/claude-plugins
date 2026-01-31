---
name: draft
description: Create a new page in a tinydot site
argument-hint: [topic]
allowed-tools: Read, Write, Glob, Grep
---

# draft a new tinydot page

Create a new markdown page in a tinydot site. Follow these steps:

1. if no site folder is specified, list available sites in `~/Library/CloudStorage/Tinydot/` and ask which one to use
2. ask for the topic or title (use `$ARGUMENTS` if provided)
3. ask where in the site to create the file (root, or a subfolder)
4. scan existing pages in the site using Glob for `**/*.md` to find related content for wikilinks
5. generate the markdown page with:
   - frontmatter: `title`, `date` (today YYYY-MM-DD), `tags` (relevant tags)
   - well-structured content using standard markdown
   - wikilinks `[[page-name]]` to link to existing related pages where relevant
   - content blocks for any images or files if applicable
6. save the file with a kebab-case filename: `my-page-title.md`
7. confirm the page is live and show its URL: `sitename.tinydot.com/path/to/page`

Use the tinydot-content skill for markdown syntax reference.
