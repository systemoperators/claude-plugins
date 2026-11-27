---
name: basicmusic-learn-a-song
description: "Learn or play a song on guitar, ukulele, bass, mandolin, banjo or piano the way a teacher would: the easiest chords with a capo, the hardest change first, the strum and a tempo that climbs, with the Basic Music tools."
---

# Learning a song with Basic Music

Use this when someone wants to learn or play a song on guitar, ukulele, bass, mandolin, banjo or piano: "teach me Amazing Grace on ukulele", "I want to play this song, here are the chords", "help me learn Wonderwall".

## The song's chords

- A starter song (20 traditional and public-domain songs): get_song gives its words with the chords over them, its key, tempo and strum. list_songs finds one by level, by the chords the person knows, or by title.
- Any other song: the person's chords are what you work from. Ask them to paste the chords or the chart, or use the chords they named. Chord progressions are fine to work with; never write out the words of a song under copyright, only the chords and where they change.
- A chart pasted with chords over the words or in brackets: keep the person's own text as it is; transpose_chords moves it to another key without touching the words.

## Steps

1. The instrument and the level. Ask only when it changes the answer; otherwise use what they said and say what you assumed (a beginner on the instrument they named).
2. The easiest way through. Call find_easiest_chords with the song's chords in the order they are played. It tries a capo on every fret up to 7 and easier versions of hard chords (Fmaj7 for F on guitar, E7 for E). Tell them the capo and the chords to play, in one sentence.
3. Each chord. The chords player draws every shape; in a chat without it, give each shape as tab (x32010) with which finger goes where. Point out a finger that stays down from one chord to the next: it is the change they will feel first.
4. The hardest change first. find_easiest_chords names it. Have them practise just those two chords, back and forth, for one minute, counting how many clean changes they make.
5. The strum. Use the song's strum (get_song names it) or pick one that fits the meter with list_strum_patterns; get_strum_pattern shows and plays it on their chords. Start at about 60% of the song's tempo.
6. The tempo ladder. start_metronome at that slower tempo; when they can play the song through twice without stopping, raise it by 5 to 10 beats a minute, up to the song's own tempo.
7. Where to go next. Each answer has a link to the page on basicmusic.app and to the Basic Music app, which listens with the tuner and keeps the song.

## Keep it short

- One step at a time, with the player or the tab, not a wall of theory.
- Say what each instruction is for in plain words: "keep your first finger down, it is already where C needs it".
