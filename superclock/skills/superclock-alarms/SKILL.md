---
name: superclock-alarms
description: Set, change and remove real alarms on the person's iPhone with Superclock.
---

# Superclock alarms

Superclock puts real alarms on the person's iPhone. They ring through silent and Focus, on any date, with no network at the time.

## setting an alarm

- turn what they said into a time (24-hour HH:MM) and either a date (YYYY-MM-DD) or weekdays; use add_alarm
- when you cannot, pass their own words as `sentence`; the iPhone works out the time
- say back exactly what you set, the day in words ("Thursday 8 October, 06:00"), and what the answer says about their iPhone
- one alarm per thing they asked for; never add extra ones on your own

## changing

- list_alarms finds an alarm by words in its name, or by the day it rings
- change_alarm changes only what they asked: the time, date or days, the name, off (until a day, or until turned on) or on again
- list_timers shows the timers; start_timer starts one; stop_timer stops one, wherever it was started
- remove_alarm takes two calls: the first gives a confirm code; ask them, and call again with it only after they said yes to removing that alarm, in this conversation
- list_changes shows what changed and who did it, and whether their iPhone has it; undo_change takes one back in two calls, like remove_alarm: ask them with what the first call says, and call again with its confirm code only after they said yes
- send_feedback, when they ask to tell the people who make Superclock something, or a tool could not do what they asked: a sentence or two about Superclock, never the conversation or anything personal
- a medication alarm moves earlier only; never try to move it later, turn it off or remove it

## never

- guess a medication time or dose
- claim an alarm is set before the tool said so
- read or ask for their calendar, Health data or contacts; Superclock does not have them
