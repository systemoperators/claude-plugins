---
name: contacts
description: Search and read contacts
argument-hint: [contact name]
paths:
  - "**/alto-index/contacts/**"
allowed-tools: Read Grep Glob
---
# Alto Index -- contacts

Alto Index writes an `alto-index` folder inside the folder the person picked in the app. Find it with `find ~ -maxdepth 5 -type d -name alto-index -not -path "*/Library/*" 2>/dev/null | head -1`, or ask them, and read `<alto-index>` below as that folder.

Contacts exported by Alto Index to:
  <alto-index>/contacts/


## layout

- one file per contact
- filename: `{first-name}-{last-name}.md` or `{organization-name}.md`

## frontmatter

title (display name), id (contact identifier), created, modified, source (addressbook:// deep link), organization

## body

Structured sections: Professional (org, title, department), Phone Numbers, Email Addresses, Addresses, Important Dates, Social Profiles, Websites, Notes, Relationships.

## tips

- use `addressbook://` URL from frontmatter to open in Contacts
- phone numbers and emails can cross-reference with messages/ and calls/
- search by organization using `Grep` for the organization field
- contact identifiers link to other exports (messages reference contacts)
