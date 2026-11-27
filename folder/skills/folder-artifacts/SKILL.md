---
name: folder-artifacts
description: Publish a page you wrote to Folder as an artifact, share it, read and wait for the notes people leave on it, and change it with a new version.
---

# Publish a page and work from its notes

Use these when the person asks to publish, keep or share a page you made (a report, a chart, a small app), or asks what people said about one. A page needs their folder on Folder, connected with Read and Change. A Claude artifact's body works as it is.

## Publish

Write the page as HTML: index.html, with styles, scripts, data and pictures as other files beside it by relative path. publish_artifact keeps them in Artifacts/{name} in their folder on Folder and answers the page's address, folder.dev/artifact/{code}. Only they can open it until they share it. Give it an icon word for its tab, like chart, calendar or recipe, and give them the address.

- In a chat: pass the files in files, text as {path, text} and a picture or a font as {path, base64}, up to 255 files and 20 MB in one call.
- Where you can run commands, as in Claude Code: zip the page's folder, send the zip with create_upload_link and its one curl, then call publish_artifact with from set to the zip's path. Pass session as $CLAUDE_CODE_SESSION_ID and rex_block as $REX_BLOCK when they are set, so the person can go back to where it was made.
- Over 20 MB: send each file with its own create_upload_link into one folder, then set from to that folder. from may name any folder already in their folder on Folder; it is published where it is.

A version holds up to 511 files and 256 MB; a page or text file up to 16 MB, any other file up to 15 MB.

## Share

share_artifact picks who can open it: only-me, company (people signed in at the email domains in company_domains), link (anyone with the link) or password. It asks first: say who will be able to open it, and go on only after they say yes. stop_artifact takes the page down the same way; its files stay in their folder.

## Notes

People leave numbered notes on the page (#1, #2), each pinned to the words they picked, and write in its chat. list_artifact_notes reads the open ones with the words they were left on. When the person asks you to keep going as notes come in, wait_for_artifact_notes waits for the next ones and finishes with what people wrote. Before you work on them, set_artifact_status says what you are doing, so the people looking at the page see it.

## Change

Read it with get_artifact first: it gives base_version and the files. update_artifact saves the next version from that one, with a one-line summary, and answers naming the notes it settles (#2). Small changes go as edits (old text that appears once in the file, and the new text), whole files as files, and files to delete in remove; a zip through from replaces them all. When someone saved a newer version, it is refused: read again. Then reply_to_artifact_note says what you did, under the note, and resolves it. To keep going, wait again.

list_artifacts lists their pages with each address and who can open it. Report an address or a version only after the tool answers with it.
