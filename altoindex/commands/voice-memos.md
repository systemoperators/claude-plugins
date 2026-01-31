---
description: Browse your Voice Memos recordings
allowed-tools: Read, Glob, Grep
argument-hint: "[query]"
---

Work with Voice Memos synced to `~/Documents/alto-index/voice-memos/`.

If $ARGUMENTS is provided, search the index for that query.

If no arguments:
- read `~/Documents/alto-index/voice-memos/index.md` for the full recording list
- show total count, date range, and most recent recordings
- show total storage size

If the voice-memos folder doesn't exist, tell the user to enable Voice Memos sync in alto.index.
