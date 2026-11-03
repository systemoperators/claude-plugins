# Superclock

Superclock is an iPhone alarm app on Apple's AlarmKit. It rings like Clock and knows your day like Calendar.

Ask Claude to set or move an alarm, and it is on your iPhone in seconds, with Undo. Set an alarm for any date, name it, move it, pause it or remove it, and start a timer on your phone. Every change says who made it, removing an alarm always asks you first, and a notification with Undo tells you when an assistant changed one.

It needs the Superclock app on your iPhone: sign in with Apple in Settings under Account, then connect here with the same Apple ID. Your alarms stay on your phone, and you choose which kinds of alarms go up, with a switch for each in Settings under Account.

It cannot read your calendar or block apps, and it does not change the alarms in Apple's Clock.

## What the plugin holds

- one MCP server, Superclock, at https://mcp.superclock.app/mcp over streamable HTTP. Connecting opens Superclock's own sign-in page (OAuth 2.1); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - superclock-alarms: Set, change and remove real alarms on the person's iPhone with Superclock.
  - superclock-limits: What Superclock cannot do, so an agent says so instead of pretending.
  - superclock-onboarding: Set up Superclock: connect it, then check an iPhone is signed in.

## Install

In Claude, add Superclock from the directory. In Claude Code:

```
/plugin install superclock --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.superclock.app/mcp only when you ask for something Superclock does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://superclock.app/agents
- Privacy policy: https://superclock.app/privacy
- Terms: https://superclock.app/terms
- Support: https://superclock.app/contact

By system operator (System Operator LLC). MIT license.
