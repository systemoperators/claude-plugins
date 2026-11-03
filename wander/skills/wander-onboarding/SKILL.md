---
name: wander-onboarding
description: Connect to Wander and choose a vault on first use, explaining how writes and undo work.
---

# Start using Wander

On first use, call list_folder without a path to list only the vaults this OAuth grant can see. Do not assume access to any other vault or account.

If none are visible, offer to create a vault. Once the person agrees, use create_vault; do not create one merely because the list is empty. If several vaults are visible and the intended destination is unclear, ask which one to use.

Say that every write is a new version that can be undone in Wander's history. Note edits take effect directly, with the assistant recorded as the author. There is no pending suggestion to accept and no Claude side panel. For notes, restore_version can bring back an old version, including a deleted note; use the write result's undo details.

Explain only what is needed for the person's next task. Follow wander-notes for reading, editing, attachments, sharing and deletion. Preserve the complete paths returned by list_folder.
