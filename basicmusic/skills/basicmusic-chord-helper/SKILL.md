---
name: basicmusic-chord-helper
description: "Answer chord questions in plain words: how to play a chord, why F is hard, capo or transpose, what a shape is called, what a chord name means, with the Basic Music tools."
---

# Chord questions with Basic Music

Use this for questions about chords, capos, keys and tunings: "why is F so hard", "capo or transpose", "what chord is x32010", "what does Cadd9 mean", "how do I play this in drop D".

## Which tool

- One chord, how to play it: get_chord_shapes (guitar, ukulele, bass, mandolin, banjo, piano; any tuning they name). With easy, the version with no barre and at most three fingers, and what it plays instead.
- A song's chords made easier, or where to put a capo: find_easiest_chords with the chords in order.
- A song in another key: transpose_chords with their chart and the key or semitones; on guitar it also says the capo that keeps the shapes.
- A shape, what is it called: find_chord_name with one fret per string, lowest string first.
- The notes of a tuning: get_tuning.

## Plain answers to the usual questions

- Capo or transpose: a capo keeps the shapes you know and raises the sound; transposing changes the chords. To sing a song higher without new shapes, use a capo. To play it in a key with easier shapes and keep the sound, put a capo on and play the shapes find_easiest_chords gives.
- Why F is hard on guitar: it is a barre, one finger across all six strings. Start with Fmaj7 (xx3210) or the small F (xx3211), which get_chord_shapes gives with easy.
- A slash chord (G/B): the chord over another bass note, the note after the slash is the lowest one. On ukulele the bass note is mostly left out.
- A chord's name, part by part: the root (C), then m for minor, 7 for a seventh, maj7, sus2 or sus4 for a second or fourth instead of the third, add9 for an added ninth, dim and aug. get_chord_shapes names its notes.

## Keep it practical

- Draw it: the chords player plays each chord when tapped; in a chat without players give the tab and the fingers.
- One line of why, then what to do.
