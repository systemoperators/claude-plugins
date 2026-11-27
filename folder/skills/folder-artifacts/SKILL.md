---
name: folder-artifacts
description: Publish a page you wrote to Folder as an artifact, share it, read and wait for the notes people leave on it, and change it with a new version.
---

# Publish a page and work from its notes

Use these when the person asks to publish, share or keep a page you made (a report, a chart, a small app), or asks what people said about one. They work where Folder offers publish_artifact. A page from this chat is HTML; a Claude artifact's body works as it is.

## Publish

publish_artifact keeps the page's files in Artifacts/{name} in their folder on Folder and answers its address, folder.dev/artifact/{code}. It opens for the person alone until they share it. Give it an icon word, like chart, calendar or recipe, for its tab. Several files (pictures, data, scripts) go up as one zip through create_upload_link, then publish_artifact with from. An artifact over 20 MB goes up file by file, each through its own create_upload_link into one folder, then publish_artifact with from set to that folder. A version holds up to 511 files and 256 MB; a page or text file up to 16 MB, any other file up to 15 MB.

## Share

share_artifact picks who can open it: only them, anyone signed in at a company's domain, anyone with the link, or anyone with a password. It asks first: say who will be able to open it, and go on only after they say yes. stop_artifact ends that the same way.

## Notes

People leave numbered notes on the page (#1, #2), each pinned to the words they picked, and write in its chat. list_artifact_notes reads the open ones with the words they were left on. When the person asks you to keep going as notes come in, wait_for_artifact_notes waits for the next ones and finishes with what people wrote. Before you work on them, set_artifact_status says what you are doing, so the people looking at the page see it.

## Change

update_artifact saves the next version from the version you read (base_version), with a one-line summary of what changed and answers naming the notes it settles (#2). Edit with old and new text that appears once; put and remove whole files. Then reply_to_artifact_note says what you did, under the note. To keep going, wait again.

Report an address or a version only after the tool answers with it.
