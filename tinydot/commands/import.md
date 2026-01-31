---
description: Import an external website into a tinydot site
allowed-tools: Read, Write, Glob, Grep, WebFetch
argument-hint: "[url]"
---

# import a website into tinydot

Convert an external website into a tinydot site. Follow these steps:

## 1. get the source URL

Use `$ARGUMENTS` as the URL. If empty, ask the user for the URL to import.

## 2. discover pages

Fetch the site and look for pages to import:

1. try `{url}/sitemap.xml` - parse all `<loc>` URLs
2. if no sitemap, try `{url}/rss.xml` or `{url}/feed` or `{url}/feed.xml` - parse all `<link>` entries
3. if neither exists, fetch the homepage and extract internal links from navigation (header, footer, sidebar) and content

Show the user the list of discovered pages and ask which to import (all, or select specific ones).

## 3. determine site name

Suggest a site name based on the domain (e.g., `example.com` -> `example`). Ask the user to confirm or change it. The site folder will be created at `~/Library/CloudStorage/Tinydot/{sitename}/`.

## 4. fetch and convert each page

For each page:

1. fetch with WebFetch, asking it to extract the main content as markdown
2. extract from the page:
   - title (from `<title>`, `<h1>`, or og:title)
   - date (from meta tags, published date, or article:published_time)
   - description (from meta description or og:description)
   - author (from meta author if available)
3. find images in the content:
   - download each image using WebFetch
   - save to `{sitename}/images/{filename}` (use original filename or generate from URL)
   - replace image URLs in markdown with local paths: `images/filename.jpg` (content block syntax)
4. convert internal links to wikilinks where the target page is being imported
5. preserve external links as regular markdown links
6. create the markdown file with frontmatter:

```yaml
---
title: Page Title
date: 2026-01-15
description: Page description
tags: imported
---
```

## 5. create navigation

From the source site's header/footer navigation:
- create matching `header_menu` and `footer_menu` in the root `index.md` frontmatter
- convert navigation links to local paths where pages were imported
- keep external links as-is

## 6. create index.md

Create the root `index.md` with:
- title from the original site
- header_menu and footer_menu from navigation
- `show_file_list: true` so all pages are listed
- tag `imported` for all imported content

## 7. report results

Show the user:
- number of pages imported
- number of images downloaded
- any pages that failed to fetch
- the site URL: `{sitename}.tinydot.com`
- suggest running `/tinydot:review {sitename}` to check for issues

## tips

- for large sites (50+ pages), ask the user if they want to import in batches
- preserve the original URL structure where possible (e.g., `/blog/post` -> `blog/post.md`)
- if a page has no meaningful content (just navigation or redirects), skip it
- set reasonable limits: skip binary files, very large pages, or duplicate content
