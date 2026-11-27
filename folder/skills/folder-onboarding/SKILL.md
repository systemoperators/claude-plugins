---
name: folder-onboarding
description: "Start with Folder: the folders this connection reaches, reading or changing, connecting again, guest folders, the apps, and undo."
---

# Start using Folder

Folder keeps a person's files in folders they see in Finder, in the Files app on iPhone and iPad, and on the web at folder.dev. Every overwrite and delete is kept.

## The folders this connection reaches

Call list_folders first. It names the folders the person ticked when they connected, where each lives (on Folder, or in their own Cloudflare), and whether you may change files there. Never assume any other folder. A folder kept only on their Mac is never reachable here.

Read Only lets you find and read. Read and Change also lets you save, edit, put versions back, make links and publish pages, and sell. To add a folder or switch to Read and Change, they connect Folder again: disconnect it in Claude's connector settings and connect it, and the Connect Folder page asks again. folder.dev › Settings › Connected Apps disconnects it from Folder's side.

When no folders are listed, say so and tell them to connect again and tick one. This connection cannot make a folder.

## Someone new to Folder

- Signing in with Apple or Google starts an account with 5 GB free on Folder, stored in the EU. Folder Pro adds 200 GB and their own domains, on folder.dev › Settings.
- Try Without an Account makes a guest's folder that lasts 24 hours. Each change you make in one answers until when, and the link where they keep it with Apple or Google. Tell them both, once.
- When a folder holds nothing yet, offer to save one real thing from the chat: a note, a plan or a draft.
- Folder for Mac (Mac App Store, macOS 27 or later) puts the folder in Finder's sidebar. Folder for iPhone and iPad (App Store, iOS 27 or later) puts it in the Files app. What you save shows there and at folder.dev.

## A folder's own instructions

A folder may hold the person's instructions for it: INSTRUCTIONS.md, AGENTS.md, CLAUDE.md or CHATGPT.md. When list_files shows one, read it before working there and follow it. When they start a project with you, offer to write one that says what it is for and how they like things done.

## Changes and undo

Every change is a new version in the file's history, and restore_version puts any version back. Changes land at once; there is nothing to accept. This connection never deletes, moves or renames a file: they do that in Finder, the Files app or on folder.dev.

Explain only what the next task needs. Then follow folder-files for files, folder-sharing for links, folder-artifacts for pages, folder-websites for websites, and folder-selling to sell.
