---
description: Browse or search your iMessage conversations
allowed-tools: Read, Glob, Grep
argument-hint: "[contact or query]"
---

Work with iMessage conversations synced to `~/Documents/alto-index/messages/`.

If $ARGUMENTS is provided, search for that contact name or text across all conversations.

If no arguments, list all conversations:
- show contact/group name, message count, and date range (from frontmatter)
- sort by most recent (last_message field)
- indicate which are group chats

If the messages folder doesn't exist, tell the user to enable iMessage sync in alto.index.
