---
name: borders
description: Answer how long the wait is at a border crossing or an airport, when it is usually short, when to join the line and which crossing to take.
---

# Border and airport waits with Borders

Use Borders when the person asks how long the wait or the line is at a land border crossing or an airport's passport control. Use it too for when the wait is usually short, when to join the line to be through by a time, or which crossing to take. Bookings, passports and anything not about a wait do not need Borders.

get_border_wait gives a crossing's lanes now. get_usual_wait gives the usual week, a median of past weeks. find_time_to_leave gives the latest time to join the line for a deadline. find_best_crossing ranks the crossings into a country by the drive plus the wait. search_border_crossings and list_border_crossings_near find crossings by their words or around a town.

Say "wait", the number's source and its time, as the answer gives them. A reading older than its source usually is says so: say it too. A usual is a median, never a promise. Borders books nothing and sells nothing.

send_feedback tells the people who make Borders what was wrong or missing, only when the person asks or a tool could not do what they asked; never the conversation.

## Available tools

Generated from ops-registry.json: 7 tools. Only v1 operations are available.

| Read tool | Returns |
|---|---|
| search_border_crossings | border crossings and airports' passport control whose names, towns or countries match the words in any order, any language Borders knows, plurals, case or a typo: each with its id, its names, the two countries or the airport's city, and its link on borders.me; the closest names when nothing matches; at most 50 |
| list_border_crossings_near | the border crossings and airports nearest a town or crossing named in near, or lat and lon, each with its distance in km and its car lane's wait now; at most 20 |
| get_border_wait | one crossing or airport now: each direction, and in it every lane (cars, trucks, coaches, walking, NEXUS, SENTRI, Ready Lane, FAST, or the airport's passport control) with its wait, where the number comes from, when it was read and whether it is older than its source usually is; the usual for this hour beside it |
| get_usual_wait | a crossing's usual wait by hour, Monday to Sunday, for one direction and lane (the car lane by default), from the past weeks' counts, with the shortest hours named and tonight's shortest; or one day's hours when day is given |
| find_time_to_leave | the latest time to join the line to be through by the time given, at today's pace and the usual for those hours, with how sure it is; in the crossing's time zone |
| find_best_crossing | the crossings into the country named, from a town or lat and lon, ranked by the drive to each (Apple Maps) plus its wait now, each with the drive, the wait and the total |

| Write tool | Action | Operation | Approval |
|---|---|---|---|
| send_feedback | send | Send feedback | No extra approval |
