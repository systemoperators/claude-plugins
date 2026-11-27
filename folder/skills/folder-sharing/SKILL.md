---
name: folder-sharing
description: "Share a file or a folder from Folder with a link: anyone with the link, a password, anyone, an end date; stop a link; and where company sharing and invites are set."
---

# Share a file or a folder

Use these when the person asks for a link someone else can open, or asks to stop one. Never share what they did not ask to share.

## Make a link

create_share_link makes a link to a file, or to a folder and everything in it. Pick who can open it from the person's words:

- link, the default: anyone who has the link. Its address carries a random part nobody can guess.
- password: anyone with the link and the password the person gives you. Never make one up, and tell them to send it apart from the link.
- anyone: everybody, at a clean address made of the name.

name is a short name for the address: lowercase letters, digits and hyphens. expires_in_days is 1 to 365; left out, the link opens until they stop it.

The first call says who will be able to open it and answers a confirm code. Ask the person, and only after they say yes call again with the same choices and that code. Give them the link it returns.

## Stop a link

revoke_share stops every link to a file, and asks first the same way. The file itself is never touched. Shared Links, on folder.dev and in the Folder apps, lists every link they made and the ones that ended.

## Set outside this chat

- Anyone at a company: only people signed in to Folder with an email at the company's domain, never free mail like gmail.com. They pick it in the file's Share panel on folder.dev. For a page, share_artifact takes it.
- Invites: a folder in their own Cloudflare can appear in someone else's Finder. On folder.dev, the folder's Links and Invites › Invite Someone. Folders on Folder cannot be shared this way yet.
- In Finder: right-click a file › Copy Link or Share…. On iPhone and iPad: Copy Link in a file's menu in Folder.
- Anyone who pays: selling, in folder-selling.
