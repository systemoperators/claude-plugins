---
name: folder-websites
description: Put a folder from Folder online as a website, at a free name on folder.dev or at a domain the person owns, and take it down.
---

# Put a folder online as a website

Use these when the person asks to put a site, a portfolio or a folder of pages on the web, at a folder.dev name or at a domain they own.

A website is a folder in their folder on Folder that anyone can open at an address. Its index.html is the home page, a folder's own index.html is that folder's page, and 404.html shows for a page that is not there. For one page with notes that starts private, use folder-artifacts instead.

Write the pages into one folder, like Sites/blog: text with create_file, pictures with save_file or create_upload_link. A guest's folder and a folder in their own Cloudflare cannot be a website.

## Where it opens

list_domains lists their websites and domains, what each shows, whether it is live, and how many free names are left.

- A free name on folder.dev: their handle (anna.folder.dev) or a name joined to it (blog-anna.folder.dev). It opens at once. Pages there run sandboxed, with no cookies and no saved data of their own.
- A domain they own: add_domain adds it (Folder Pro, up to 5) and answers the DNS record to add where the domain is managed. It opens once the record is in place, and list_domains says when it is live. Until a website goes there, it shows their share links and shop.

## Publish and take down

publish_site takes the folder, the path of the site's folder inside it, and domain: one of theirs, a free name, or left out for the name Folder offers. The first call says who will be able to open it and answers a confirm code. Ask the person, and only after they say yes call again with that code. Give them the address it returns.

unpublish_site takes a website down the same way. The folder and its files stay; a free name is let go, and their own domain shows their share links and shop again. Removing a domain from Folder is done in Settings › Domains on folder.dev.
