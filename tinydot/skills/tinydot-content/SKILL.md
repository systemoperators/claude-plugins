---
name: tinydot-content
description: Use when working with tinydot sites, pages, markdown content, wikilinks, embeds, frontmatter, or site customization. Activates for any tinydot content editing or publishing task.
user-invocable: false
allowed-tools: Read, Write, Edit, Glob, Grep
---

# tinydot content editing

tinydot is a file-based publishing platform. folders = sites, files = pages. changes publish instantly.

## how it works

- users have a tinydot folder on their Mac (via FileProvider) synced at `~/Library/CloudStorage/tinydot/`
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

### folder settings

a site's settings live in `settings.json` (JSON, comments allowed) at the site's root, and in any folder to change that folder and the folders inside it; the nearest file wins, key by key. a key you leave out keeps its default. older sites may still carry the same settings as root `index.md` frontmatter (`default_view`, `show_file_list`, `header_menu`): they keep working, `settings.json` is where new ones go.

```json
{
  "menu": {
    "header": [
      {
        "label": "Blog",
        "url": "/blog"
      }
    ]
  },
  "list": {
    "view": "cards"
  },
  "header": {
    "sticky": true
  }
}
```

- `title`: text, default empty
- `description`: text, default empty
- `language`: text, default empty
- `menu.header`, `menu.footer`, `menu.sidebar`: lists of `{ "label", "url" }`, empty by default
- `logo.text` (root only): text, default empty
- `logo.font` (root only): text, default empty
- `logo.size` (root only): text, default empty
- `logo.color` (root only): text, default empty
- `logo.width` (root only): text, default empty
- `logo.height` (root only): text, default empty
- `list.view`: list, cards or grid, default "list"
- `list.visible`: true or false, default true
- `list.dates`: created, modified or none, default "created"
- `list.sizes`: true or false, default true
- `list.icons`: true or false, default true
- `list.sort`: name, date or size, default "date"
- `list.order`: asc or desc, default "desc"
- `page.metadata`: true or false, default true
- `page.export`: true or false, default false
- `page.anchors`: true or false, default true
- `page.highlighting`: true or false, default true
- `header.sticky` (root only): true or false, default false
- `footer.links` (root only): true or false, default true
- `ai.train` (root only): true or false, default true
- `ai.answer` (root only): true or false, default true

ref: docs.tinydot.com/customization

## site look

a site's template is picked when the site is made, on tinydot.com or in the app, and changed there; it is not in the folder. each template takes its own colors and sizes as root `index.md` frontmatter, nested (`color:` then `background: "#ffffff"`).

a new site picks `wander` (Wander) or `finder` (Apple Finder); `future`, `romi`, `human`, `branduria`, `plain` still serve the sites already on them.

### wander

- `color.background`: background color (color), default `#ffffff`
- `color.text`: text color (color), default `#000000`
- `color.muted`: muted text (color), default `#374151`
- `color.border`: border color (color), default `#dddddd`
- `color.link`: link color (color), default `#103dff`
- `color.accent`: accent color (color), default `#103dff`
- `color.list`: list background (color), default `#f5f5f5`
- `layout.max_width`: content width (text), default `640px`
- `image.shadow`: image shadow (text), default `none`
- `image.radius`: image radius (text), default `4px`
- `theme.default`: default theme (select, one of light, dark), default `light`
- `theme.toggle`: theme toggle (boolean), default `true`

### finder

- `color.background`: background color (color), default `#ffffff`
- `color.text`: text color (color), default `#000000`
- `color.border`: border color (color), default `#d1d1d1`
- `color.hover`: hover background (color), default `#f6f6f6`
- `color.list`: list background (color), default `#fafafa`
- `color.muted`: muted text (color), default `#666666`
- `image.shadow`: image shadow (text), default `0 2px 8px rgba(0, 0, 0, 0.1)`
- `image.radius`: image radius (text), default `6px`
- `image.border`: image border (text), default `none`
- `header.sticky`: sticky header (boolean), default `false`
- `content.heading_anchors`: heading anchors (boolean), default `false`
- `content.syntax_highlighting`: syntax highlighting (boolean), default `true`
- `theme.default`: default theme (select, one of light, dark), default `light`
- `theme.toggle`: theme toggle (boolean), default `true`

### future

- `color.background`: background color (color), default `#ffffff`
- `color.text`: text color (color), default `#000000`
- `color.link`: link color (color), default `#0000EE`
- `color.link_visited`: visited link color (color), default `#551A8B`
- `color.border`: border color (color), default `#000000`
- `color.muted`: muted text (color), default `#666666`
- `image.shadow`: image shadow (text), default `0 2px 8px rgba(0, 0, 0, 0.1)`
- `image.radius`: image radius (text), default `6px`
- `image.border`: image border (text), default `none`
- `content.syntax_highlighting`: syntax highlighting (boolean), default `true`
- `theme.default`: default theme (select, one of light, dark), default `light`
- `theme.toggle`: theme toggle (boolean), default `true`

### romi

- `color.background`: background color (color), default `#ffffff`
- `color.text`: text color (color), default `rgba(4, 4, 4, 0.85)`
- `color.link`: link color (color), default `rgba(255, 0, 0, 0.85)`
- `color.link_visited`: visited link color (color), default `rgba(180, 0, 0, 0.85)`
- `color.border`: border color (color), default `rgba(4, 4, 4, 0.15)`
- `color.muted`: muted text (color), default `rgba(4, 4, 4, 0.5)`
- `image.shadow`: image shadow (text), default `0 2px 8px rgba(0, 0, 0, 0.1)`
- `image.radius`: image radius (text), default `6px`
- `image.border`: image border (text), default `none`
- `content.syntax_highlighting`: syntax highlighting (boolean), default `true`
- `theme.default`: default theme (select, one of light, dark), default `light`
- `theme.toggle`: theme toggle (boolean), default `true`

### human

- `color.background`: background color (color), default `#ffffff`
- `color.text`: text color (color), default `#000000`
- `color.link`: link color (color), default `#0084ff`
- `color.border`: border color (color), default `#000000`
- `image.shadow`: image shadow (text), default `0 2px 8px rgba(0, 0, 0, 0.1)`
- `image.radius`: image radius (text), default `6px`
- `image.border`: image border (text), default `none`
- `content.syntax_highlighting`: syntax highlighting (boolean), default `true`
- `theme.default`: default theme (select, one of light, dark), default `light`
- `theme.toggle`: theme toggle (boolean), default `true`

### branduria

- `color.background`: background (color), default `#ffffff`
- `color.text`: text color (color), default `#3d3d3d`
- `color.link`: link color (color), default `#3d3d3d`
- `color.muted`: muted text (color), default `#999999`
- `color.border`: border color (color), default `#000000`
- `image.shadow`: image shadow (text), default `none`
- `image.radius`: image radius (text), default `0`
- `image.border`: image border (text), default `none`
- `content.syntax_highlighting`: syntax highlighting (boolean), default `true`
- `theme.default`: default theme (select, one of light, dark), default `light`
- `theme.toggle`: theme toggle (boolean), default `true`

### plain

- `color.background`: background color (color), default `#ffffff`
- `color.text`: text color (color), default `#222222`
- `color.link`: link color (color), default `#0000EE`
- `color.border`: border color (color), default `#dddddd`
- `color.muted`: muted text (color), default `#666666`
- `image.shadow`: image shadow (text), default `none`
- `image.radius`: image radius (text), default `0`
- `image.border`: image border (text), default `none`
- `content.syntax_highlighting`: syntax highlighting (boolean), default `true`

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

1. find the site folder in `~/Library/CloudStorage/tinydot/` or wherever the user points you
2. `.md` files are pages - edit them directly
3. always preserve existing frontmatter when editing
4. use wikilinks `[[page-name]]` to link between pages (prefer over regular markdown links for internal linking)
5. use content blocks to embed images and files
6. for embeds, put URLs on their own line with blank lines around them
7. changes save and publish instantly through FileProvider sync
