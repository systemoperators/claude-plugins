---
name: customize
description: "Change a site's settings and look: settings.json for menus, lists and pages, root index.md frontmatter for its template's colors"
argument-hint: [site name]
allowed-tools: Read, Glob
---

# customize a tinydot site

1. if no site specified via `$ARGUMENTS`, list available sites in `~/Library/CloudStorage/tinydot/` and ask which one
2. read the site's root `settings.json` (it may not exist yet) and root `index.md`
3. show what is set now: the settings that differ from their defaults, and the look keys in the frontmatter
4. ask what to change, then write it where it lives (the tinydot-content skill lists every key):
   - menus, the file list (view, sort, dates, visible), page options (metadata, anchors, highlighting), sticky header, footer links, AI crawlers: `settings.json`, only the keys that change; a folder's own `settings.json` changes that folder and the ones inside it
   - colors, image corners and shadow, width and the light or dark default: root `index.md` frontmatter, only the keys the site's template takes; keep every other frontmatter field as it is
   - the template itself is not in the folder: the person changes it on tinydot.com or in the app
5. say what changed and that it is live once the file syncs
