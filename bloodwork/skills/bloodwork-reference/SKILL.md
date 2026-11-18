---
name: bloodwork-reference
description: Look up blood tests in the Bloodwork reference: what a marker measures, its published reference ranges, the tests in a panel and the tests followed for a condition.
---

# Use the Bloodwork reference

Use it when someone asks about a blood test, a marker, a lab panel or a condition: what a marker measures, its usual reference ranges, its LOINC code, what a high or low value can be associated with, which tests a panel holds, or which tests are followed for a condition. Weather, general writing and anything that is not about blood tests do not need it.

Find the slug first with search_reference (a name, an abbreviation, a slug or a LOINC or ICD-10 code), then read the page with get_biomarker, get_panel or get_condition. Every answer is the page's own words with the page's link; pass the link on.

Give each reference range with the lab that publishes it, by sex and age as the page has it; never merge them into one number. The reference holds no personal data and never takes a person's values: it does not say whether a person's own result is normal, and it is not medical advice. A person who wants their own report read against these ranges adds it on bloodwork.md; once it is there, bloodwork-own-results reads it.

## Available tools

Generated from ops-registry.json: the 4 reference tools, all read only.

| Tool | Returns |
|---|---|
| search_reference | markers, lab panels and conditions whose name, abbreviation, slug or code matches, each with its slug and page |
| get_biomarker | one marker's page: what it measures, its LOINC code and sample, the reference ranges named labs publish for it by sex and age, and what a high or low result can be associated with |
| get_panel | one lab panel's page: its member tests, each with its published adult reference range |
| get_condition | one condition's page: the blood tests followed for it, with a guideline's monitoring plan where one is cited |
