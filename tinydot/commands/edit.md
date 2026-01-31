---
name: edit
description: Edit an existing page in a tinydot site
argument-hint: [page name or path]
allowed-tools: Read, Write, Edit, Glob, Grep
---

# edit a tinydot page

Edit an existing markdown page in a tinydot site. Follow these steps:

1. if no page is specified via `$ARGUMENTS`, ask which page to edit
2. find the page:
   - search by name using Glob in `~/Library/CloudStorage/Tinydot/` or the user's site folder
   - if ambiguous, list matches and ask user to pick
3. read the current content with Read tool
4. show a brief summary of the current content
5. ask what changes to make
6. apply changes using Edit tool:
   - preserve all existing frontmatter fields
   - preserve wikilinks and content blocks
   - maintain tinydot markdown conventions
   - update `date` in frontmatter if the content changes substantially
7. show a summary of what changed

Use the tinydot-content skill for markdown syntax reference.
