---
name: deepcalc-onboarding
description: Connect to deepcalc on first use, find the person's workbooks and explain how changes wait on a branch.
---

# Start using deepcalc

On first use, call list_workbooks to see the workbooks this connection can open. Use the owner/name it returns (or the id) in every later call; never invent one.

If there are none, offer to make one with create_workbook, or to open an attached xlsx or csv with import_workbook. Do not make a workbook merely because the list is empty.

Say once how changes land: change_cells never writes into main. It writes on a branch of its own, and the person keeps it or throws it away in Changes at deepcalc.com, or asks you to with merge_branch, which answers a confirm code first: ask them, then call it again with the code. Trying numbers with run_what_if writes nothing.

Explain only what the next task needs. Follow deepcalc-workbooks for reading, checking, changing and publishing.
