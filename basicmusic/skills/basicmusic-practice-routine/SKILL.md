---
name: basicmusic-practice-routine
description: "Plan a daily practice routine on guitar, ukulele or piano from the minutes someone has: tuning, a warm-up, one-minute chord changes, a strum and a song, with the Basic Music tools."
---

# A practice routine with Basic Music

Use this when someone asks what to practise, how to get better at an instrument, or wants a routine for the minutes they have: "what should I practise today on guitar", "I have 10 minutes a day for ukulele", "how do I get faster at changing chords".

## The day's minutes, the way the Basic Music app plans them

- Tune first, under a minute: get_tuning gives the notes and the tuner player plays each string's note.
- A warm-up, about a fifth of the time: one finger a fret, 1 2 3 4 on every string, slowly, with start_metronome at 60.
- One-minute chord changes, about two fifths: two chords from the level they are at, back and forth for one minute, counting the clean changes. A beginner's first pairs: Am and C, C and G, G and D on guitar; C and Am, F and C on ukulele. get_chord_shapes draws them. Write the count down; next time, beat it. The app's goal is 30 clean changes a minute.
- A strum, about a fifth: the pattern of their level (list_strum_patterns with level), played on the same chords with get_strum_pattern, starting slow.
- A song to finish, the rest: a starter song that uses only chords they know (list_songs with chords), played through once.

## Levels

- 1: All Downs; three chords. 2: Down Up. 3: the Island Strum. 4: the Waltz in 3/4. 5: 6/8. 6: the Chuck and Swing. list_strum_patterns with level gives the patterns up to it.
- Move up a level when the one-minute changes pass 30 and the strum holds at the song's tempo.

## Keep it honest

- Short and every day beats long and once a week; say so.
- Ask what they want to play: a song they love is the best reason to practise. Its chords go through find_easiest_chords.
- The Basic Music app keeps the counts and the minutes; in the chat, the person keeps them.
