# Convertfile

Convertfile turns a file into the version you need: a photo into a JPG or a PDF, a video into a smaller MP4, a Word file into a PDF, a WAV into an M4A. It works on your Mac, iPhone or iPad, and files are never uploaded. Ask what a format is and whether Convertfile opens or makes it. Ask how a conversion goes: what it keeps and what it loses, the settings, the steps in the app, and whether it is free. Images, audio and fonts are free forever; 10 videos and 10 documents are free, then one purchase. No account is needed.

## What the plugin holds

- one MCP server, Convertfile, at https://mcp.convertfile.io/mcp over streamable HTTP. Connecting opens Convertfile's own sign-in page (OAuth 2.1); the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - convertfile: Answer what a file format is and how a conversion goes in the Convertfile app: what it keeps and loses, the settings, the steps and whether it is free.

## Install

In Claude, add Convertfile from the directory. In Claude Code:

```
/plugin install convertfile --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.convertfile.io/mcp only when you ask for something Convertfile does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://convertfile.io
- Privacy policy: https://convertfile.io/privacy
- Terms: https://convertfile.io/terms
- Support: https://convertfile.io/contact

By system operator (System Operator LLC). MIT license.
