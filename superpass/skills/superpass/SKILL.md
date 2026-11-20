---
name: superpass
description: Answer where the chip is in a passport or ID card, and how to hold an iPhone to read it, from Superpass's research.
---

# Where the chip is, with Superpass

Use Superpass when the person asks where the chip is in their passport or ID card, why their iPhone will not read it, or which countries Superpass covers. Weather, general writing and anything not about reading their own document's chip do not need Superpass.

Call get_chip_location with the country as a two-letter code (de) or its English name (Germany). It answers where the chip is and how to hold the iPhone, an older design if one is still valid, and whether the ID card has a chip an iPhone reads. Each answer has its source and how sure it is. list_countries lists the countries, or finds one by the words of its name.

Say the answer's own words and its source, and how sure it is; never guess a country the tools do not know. These tools never read or check a document: only the Superpass app reads a chip, on the person's own iPhone. Nothing about the person is asked for or kept.

send_feedback tells the people who make Superpass what failed or was missing, only when the person asks or a tool could not do what they asked; never the conversation.

## Available tools

Generated from ops-registry.json: 3 tools. Only v1 operations are available.

| Read tool | Returns |
|---|---|
| list_countries | the countries Superpass has researched, each with its code, its name and where the chip is in its passport in a few words; only the ones whose name has the words, when given |
| get_chip_location | where the chip is in that country's passport and how to hold an iPhone to read it, the older design if one is still valid, whether its ID card has a chip an iPhone reads and what opens it, the source the answer comes from and how sure it is, and the page on superpass.me |

| Write tool | Action | Operation | Approval |
|---|---|---|---|
| send_feedback | send | Send feedback | No extra approval |
