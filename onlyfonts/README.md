# OnlyFonts

OnlyFonts finds free fonts for whatever you are making and gives you the code to use them, from a catalog of thousands of free fonts.

Ask for a style, a mood or a use, like a warm serif for a bakery menu or a monospace for a code blog, and it searches the catalog by how the fonts look. Ask about one font to see its weights, its license, the languages it covers and the fonts that pair with it. Then ask for the CSS: one stylesheet link loads every family you picked from cdn.onlyfonts.ai, in the same css2 format as Google Fonts.

Every font is under the SIL Open Font License or the Apache License, free for any project, commercial too. No account is needed.

It cannot install fonts on your computer, name the font in a picture, or find paid fonts.

## What the plugin holds

- one MCP server, OnlyFonts, at https://mcp.onlyfonts.ai/mcp over streamable HTTP. It needs no account and no sign-in; the plugin carries no key, token or password
- skills, which tell Claude how to use its tools:
  - onlyfonts-fonts: Choose free fonts for a project and give the code to use them, with the onlyfonts tools.

## Install

In Claude, add OnlyFonts from the directory. In Claude Code:

```
/plugin install onlyfonts --marketplace systemoperators/claude-plugins
```

## What it runs and sends

Nothing runs on your computer: no command, hook or script. Claude sends a tool call to https://mcp.onlyfonts.ai/mcp only when you ask for something OnlyFonts does, and the call carries only what that tool needs. Data handling is in the privacy policy below.

## Links

- Documentation: https://onlyfonts.ai/docs/mcp
- Privacy policy: https://onlyfonts.ai/privacy
- Terms: https://onlyfonts.ai/terms
- Support: https://onlyfonts.ai/contact

By system operator (System Operator LLC). MIT license.
