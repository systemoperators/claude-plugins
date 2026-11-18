---
name: podcasts
description: Search podcast subscriptions and episodes
argument-hint: [podcast or episode name]
paths:
  - "**/alto-index/podcasts/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- podcasts

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Apple Podcasts library exported by Alto Index to:
  <alto-index>/podcasts/


## layout

- one folder per podcast: `{podcast-name}/`
- one file per episode inside podcast folder
- podcast artwork in folder as image file
- index.md per podcast with episode table

## frontmatter

title (episode name), id, created (publish date), modified, source (podcasts:// deep link), podcast, author, duration, played, play_count, progress

## body

Episode description and metadata. Play history and progress tracking included.

## tips

- search by podcast name using folder structure
- `played: true` and `play_count` track listening history
- `progress` shows how far through an episode you got
- artwork images are in each podcast's folder
- index.md files have sortable episode tables
