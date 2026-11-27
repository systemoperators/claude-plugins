# Basic Music

Basic Music helps you play guitar, ukulele, bass, mandolin, banjo and piano, with the same chord engine as the Basic Music app.

Ask how to play a chord and see every chord for your instrument with the easiest fingers. Tap one to hear it.

Give a song's chords and see the easiest way through it: where to put a capo, easier versions of hard chords, the finger that stays down and where the next one goes. Move a song to any key, or ask what a shape is called.

Ask how to tune an instrument and hear each string's note: guitar, ukulele, bass, violin, viola, cello, mandolin, banjo, kalimba and more, with the usual tunings for each.

Learn a strumming pattern and hear it played on your chords, start a metronome with an accented first beat, or play one of 20 songs old enough to belong to everyone, with their words and chords, easiest first.

No account, no ads. Every answer links to basicmusic.app and to the Basic Music app for iPhone and iPad, whose tuner hears the string you play.

## What the plugin holds

- one MCP server, Basic Music, at https://mcp.basicmusic.app/mcp over streamable HTTP. It needs no account and no sign-in; the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - basicmusic-chord-helper: Answer chord questions in plain words: how to play a chord, why F is hard, capo or transpose, what a shape is called, what a chord name means, with the Basic Music tools.
  - basicmusic-learn-a-song: Learn or play a song on guitar, ukulele, bass, mandolin, banjo or piano the way a teacher would: the easiest chords with a capo, the hardest change first, the strum and a tempo that climbs, with the Basic Music tools.
  - basicmusic-practice-routine: Plan a daily practice routine on guitar, ukulele or piano from the minutes someone has: tuning, a warm-up, one-minute chord changes, a strum and a song, with the Basic Music tools.

## Install

In Claude, add Basic Music from the directory. In Claude Code:

```
/plugin install basicmusic --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.basicmusic.app/mcp only when you ask for something Basic Music does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://basicmusic.app/mcp
- Privacy policy: https://basicmusic.app/privacy
- Terms: https://basicmusic.app/terms
- Support: https://basicmusic.app/support

By system operator (System Operator LLC). MIT license.
