---
name: review
description: Review site content for issues and improvements
argument-hint: [site name]
allowed-tools: Read, Glob, Grep
---

# review a tinydot site

Review all content in a tinydot site and report issues. Follow these steps:

1. if no site specified via `$ARGUMENTS`, list available sites in `~/Library/CloudStorage/Tinydot/` and ask which one
2. read all markdown files in the site folder using Glob for `**/*.md`
3. check each page for:
   - missing frontmatter (no `title`, no `date`, no `tags`)
   - broken wikilinks: `[[page-name]]` where the target page doesn't exist in the site
   - inconsistent tags: same concept tagged differently (`tech` vs `technology`)
   - orphan pages: pages with no incoming wikilinks from other pages
   - empty or very short pages
   - content blocks referencing missing files
4. report findings grouped by category:
   - broken wikilinks
   - missing frontmatter
   - tag inconsistencies
   - orphan pages
   - other issues
5. for each issue, suggest a specific fix
6. offer to fix issues automatically (but ask first)

Use the tinydot-content skill for conventions reference.
