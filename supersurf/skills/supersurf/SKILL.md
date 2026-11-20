---
name: supersurf
description: Answer where and when to surf, a spot's forecast and tides, and the surf schools near it, from Supersurf's forecasts.
---

# Surf with Supersurf

Use Supersurf when the person asks where or when to surf, how the waves or wind look at a spot, when the tide turns, or where to take a lesson or rent a board. Weather in a city, bookings and anything not about surfing do not need Supersurf.

find_best_surf ranks the spots around a place for a time in the person's words (tomorrow morning, this weekend, Saturday). get_surf_forecast gives one spot's next good window and each day's hours. get_tide_times gives its tides. list_surf_schools gives the schools, rentals and shops near it. search_surf_spots and list_surf_spots_near find spots by their words or around a place.

Every number is a forecast or a prediction. Say so, say the source and when it was made, as the answer gives them, and never call it more accurate than other forecasts. Say the wind in plain words: from the land, along the shore, from the sea. Supersurf books nothing and sells nothing.

send_feedback tells the people who make Supersurf what was wrong or missing, only when the person asks or a tool could not do what they asked; never the conversation.

## Available tools

Generated from ops-registry.json: 7 tools. Only v1 operations are available.

| Read tool | Returns |
|---|---|
| search_surf_spots | surf spots whose name, town, area or country match the words in any order, plurals, case or a typo: each with its id, name, town, country, kind (beach break, reef, point) and which way it faces; the closest names when nothing matches; at most 50 |
| list_surf_spots_near | the nearest surf spots to a spot, town or area named in near, or to lat and lon: each with its distance in km, kind and which way it faces; at most 40 |
| find_best_surf | surf spots near the place, ranked for the time asked (today, tomorrow, tomorrow morning, this weekend, a date): each spot's best window in that time with its wave height, period, wind and why it ranks there, and the spots with nothing good in that time last; within radius_km (default 30, at most 100) |
| get_surf_forecast | one spot's forecast: now, its next good window, each of the next days (at most 16) with its best hours, and hour by hour the wave height, swell period and direction, wind speed and direction (offshore or onshore at this spot), and sunrise and sunset; each number names its source and when it was made |
| get_tide_times | a spot's high and low tides for the coming days (at most 14) in its own time zone, with heights, worked out from the tide constants of the nearest station; says so where there is none |
| list_surf_schools | surf schools, board rentals and surf shops within 2 km of a spot, each with its name, kind, distance, address and link where known, from Apple Maps' places |

| Write tool | Action | Operation | Approval |
|---|---|---|---|
| send_feedback | send | Send feedback | No extra approval |
