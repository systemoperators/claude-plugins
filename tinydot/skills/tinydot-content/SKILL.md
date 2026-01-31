---
name: tinydot-content
description: Use when working with tinydot sites, pages, markdown content, wikilinks, embeds, frontmatter, or site customization. Activates for any tinydot content editing or publishing task.
user-invocable: false
allowed-tools: Read, Write, Edit, Glob, Grep
---

# tinydot content editing

tinydot is a file-based publishing platform. folders = sites, files = pages. changes publish instantly.

## how it works

- users have a tinydot folder on their Mac (via FileProvider) synced at `~/Library/CloudStorage/Tinydot/`
- each subfolder is a site with its own subdomain: `sitename.tinydot.com`
- `.md` files render as pages, images display inline, other files are downloadable
- URL mapping: `docs/intro.md` -> `/docs/intro`, `folder/index.md` -> `/folder/`
- slugs are lowercase with hyphens

## markdown

standard markdown plus tinydot extensions:

### wikilinks

```
[[page-name]]                    links to /page-name
[[folder/page-name]]             links to nested page
[[page-name|custom text]]        custom link text
```

- case-insensitive: `[[About]]` and `[[about]]` resolve to the same page
- broken links render but are not clickable
- creates backlinks automatically (page B shows page A in backlinks when A links to B)

ref: docs.tinydot.com/wikilinks

### content blocks

embed files inline using iA Writer-style syntax:

```
/path/to/file.md                 embed from site root (own line)
photo.jpg                        embed from same folder (own line)
[photo.jpg]                      bracket syntax
[photo.jpg] "my caption"         with caption
```

- `.md` renders as formatted content
- `.jpg`, `.png`, `.gif`, `.webp` display as images
- `.txt`, `.js`, `.css`, `.html` show syntax-highlighted code
- other files show download link
- paths are relative to site root, use lowercase hyphens for slugs

ref: docs.tinydot.com/content-blocks

### embeds

paste a URL on its own line with blank lines around it:

```
some text here.

https://www.youtube.com/watch?v=dQw4w9WgXcQ

more text here.
```

supports 300+ providers via oembed: YouTube, Vimeo, Spotify, SoundCloud, Twitter/X, Instagram, Figma, CodePen, GitHub Gist, and more.

ref: docs.tinydot.com/embeds

## frontmatter

YAML between `---` markers at the top of `.md` files.

### file metadata

```yaml
---
title: My Page Title
date: 2026-01-15
tags: blog, tech, updates
description: A short description for SEO
author: anton
---
```

- `title` overrides filename as page title
- `date` format: YYYY-MM-DD
- `tags` comma-separated; also supports `#hashtags` in content body (both merge)
- each tag auto-generates a page at `/tags/tag-name`
- tag conventions: lowercase, hyphens for multi-word (`machine-learning`)

ref: docs.tinydot.com/file-metadata

### folder metadata

set in `index.md` of a folder:

```yaml
---
default_view: cards
show_file_list: true
title: My Folder
description: What this folder contains
---
```

- `default_view`: `list` (default), `cards`, `grid`
- `show_file_list`: `true` (default) or `false` (hides file listing, shows only index.md content)
- settings inherit from parent folder; child overrides parent

ref: docs.tinydot.com/folder-metadata

## site customization

set in the root `index.md` frontmatter of a site.

### templates

four built-in templates: `finder` (default, file-browser style), `future` (retro web), `romi` (minimal with red accents), `human` (readable)

### colors

```yaml
color:
  background: "#ffffff"
  text: "#1a1a1a"
  border: "#e5e5e5"
  muted: "#666666"
  hover: "#f5f5f5"      # finder template
  list: "#fafafa"        # finder template
  link: "#0066cc"        # future, romi, human templates
```

### menus

three menu areas: `header_menu`, `footer_menu`, `sidebar_menu`

```yaml
header_menu:
  - title: home
    url: /
  - title: blog
    url: /blog
  - title: github
    url: https://github.com/user
```

### images

```yaml
image:
  shadow: "0 4px 12px rgba(0,0,0,0.15)"
  radius: "8px"
  border: "1px solid #eee"
```

### spacing and behavior

```yaml
spacing:
  content_max_width: "800px"
header:
  sticky: true
content:
  headingAnchors: true
show_file_list: false
typography:
  baseFontSize: 14        # human template, range 10-16
```

ref: docs.tinydot.com/customization

## sites

- create at tinydot.com/sites: name + subdomain + template
- subdomain becomes `subdomain.tinydot.com`
- subdomain rules: lowercase letters, numbers, hyphens only
- custom domains supported via site settings
- multiple sites per account, each with own customization
- deleting a site removes public access but preserves files

ref: docs.tinydot.com/sites

## backlinks

- when page A contains `[[page-B]]`, page B shows page A in its backlinks section
- tracked automatically, updated on add/remove/rename
- displayed at the bottom of each page

ref: docs.tinydot.com/backlinks

## working with tinydot files

when editing tinydot content:

1. find the site folder in `~/Library/CloudStorage/Tinydot/` or wherever the user points you
2. `.md` files are pages - edit them directly
3. always preserve existing frontmatter when editing
4. use wikilinks `[[page-name]]` to link between pages (prefer over regular markdown links for internal linking)
5. use content blocks to embed images and files
6. for embeds, put URLs on their own line with blank lines around them
7. changes save and publish instantly through FileProvider sync
