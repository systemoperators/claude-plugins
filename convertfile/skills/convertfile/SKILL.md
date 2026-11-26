---
name: convertfile
description: "Answer what a file format is and how a conversion goes in the Convertfile app: what it keeps and loses, the settings, the steps and whether it is free."
---

# File formats and conversions with Convertfile

Use Convertfile when the person asks what a file format is, whether a file can be opened or converted, how to convert one format into another, what a conversion keeps or loses, or whether it is free in Convertfile. General questions and writing do not need Convertfile.

search_file_formats says what a format is, whether Convertfile opens and makes it on the Mac and on the iPhone and iPad, and what it converts into; with only a kind (image, video, audio, document, text, sheet, font) it lists that kind. get_conversion_guide says how one conversion goes: the devices, what changes in the file, the settings, the steps in the app, the cost and the page on convertfile.io; when Convertfile cannot, what the format becomes instead.

The server converts no file and receives none: the person converts in the Convertfile app, on their own device, where nothing is uploaded. Never say a file was converted. Images, audio and fonts are free forever; 10 videos and 10 documents are free for life, then Convertfile Pro, one purchase, never a subscription.

send_feedback tells the person who makes Convertfile what was wrong or missing (a format it should open, a conversion that went wrong), only when the person asks or a tool could not do what they asked; never the conversation.

## Available tools

Generated from ops-registry.json: 3 tools. Only v1 operations are available.

| Read tool | Returns |
|---|---|
| search_file_formats | file formats whose name or extension match the words in any order, case or a typo (webp, .heic, Word, Keynote): each with its id, name, extensions, kind, whether Convertfile opens and makes it on the Mac and on the iPhone and iPad, what it keeps (transparency, animation, lossless), the formats it converts to, and its page on convertfile.io; every format of a kind when only kind is given; the closest names when nothing matches; at most 50 |
| get_conversion_guide | how Convertfile turns one format into another: whether it can, on the Mac and on the iPhone and iPad, what changes in the file (what is kept and what is lost), whether it is free or counts toward the 10 free videos or 10 free documents, the settings it offers, the steps in the app, and the pair's page on convertfile.io; when it cannot, what the first format can become instead |

| Write tool | Action | Operation | Approval |
|---|---|---|---|
| send_feedback | send | Send feedback | No extra approval |
