---
name: bloodwork-own-results
description: Read the person's own blood test results in Bloodwork: their reports, one marker over time, and what the lab flagged high or low.
---

# Read the person's own results

Use these only when the person asks about their own blood tests. They signed in to Bloodwork when they connected it; every tool reads, none changes anything.

list_my_results lists their reports with each one's date and lab. get_biomarker_history gives one marker's values over time, by its slug (find the slug with search_reference). get_flagged_markers lists the results the lab itself marked high or low.

Give each value as the tools answer it, with its date and the lab's own printed range. A flag is the lab's, not a diagnosis: say so, and never call a result normal or abnormal on your own. To explain what a marker measures or what a high or low value can be associated with, read it from the reference with get_biomarker and name the page. This is not medical advice; for a decision about their health, they ask their doctor.

When they have no reports yet, say so and that they add one on bloodwork.md.
