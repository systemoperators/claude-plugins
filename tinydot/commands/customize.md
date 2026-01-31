---
name: customize
description: Modify site appearance through frontmatter
argument-hint: [site name]
allowed-tools: Read, Edit, Glob
---

# customize a tinydot site

Modify site appearance by editing the root `index.md` frontmatter. Follow these steps:

1. if no site specified via `$ARGUMENTS`, list available sites in `~/Library/CloudStorage/Tinydot/` and ask which one
2. find and read the site's root `index.md`
3. show current customization settings (colors, menus, template, images, spacing)
4. ask what to change. common options:
   - colors: background, text, border, muted, hover, list, link
   - menus: header_menu, footer_menu, sidebar_menu
   - template: finder, future, romi, human
   - images: shadow, radius, border
   - spacing: content_max_width
   - behavior: sticky header, heading anchors, show/hide file list
   - typography: baseFontSize (human template, 10-16)
5. update the frontmatter in `index.md` using Edit tool
   - merge new settings with existing frontmatter (don't overwrite unrelated fields)
   - use proper YAML formatting
6. explain what changed and how it affects the site
7. link to docs.tinydot.com/customization for more options

Use the tinydot-content skill for customization reference.
