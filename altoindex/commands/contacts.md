---
description: Look up an Apple Contact
allowed-tools: Read, Glob, Grep
argument-hint: "[name]"
---

Work with Apple Contacts synced to `~/Documents/alto-index/contacts/`.

If $ARGUMENTS is provided, search for that contact by name using Glob and Grep. Show their full details: phone numbers, emails, addresses, organization, birthday, notes.

If no arguments, show a count of total contacts and list a few recent ones.

Always include the `addressbook://` deep link from the `link` frontmatter field so the user can open the contact in the native app.
