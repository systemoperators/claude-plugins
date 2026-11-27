# Using fonts on the web and in apps

Loading, fallbacks, variable fonts, subsetting, features, apps and documents. Numbers in brackets point to sources.md.

## With get_font_css

- Ask for only the weights the design uses, and italic only if the text has italics. Left out, each family gets its regular and bold. Every extra weight is another file to download. (S16, S63)
- Give the link tag in the page head, before other stylesheets, exactly as returned. Prefer the link to the @import line, which the browser finds later and which holds up rendering. (S16, S57)
- Copy the font-family lines as returned; each already ends with a fallback. (S18)
- The link loads with font-display set to swap: text shows at once in the fallback, then switches. Pair it with a matched fallback (below) so the switch does not move the layout. (S16, S17)
- Up to four families fit in one link; a page rarely needs more than two. (S1)
- The link serves the catalog's files; the tools cannot install fonts on a computer, so for desktop apps send the person to each family's page link. (OnlyFonts' own tools)

## Loading

- font-display trade-offs: optional suits body text (a short block, no late swap, no shift); swap suits brand or display text that must appear in its face. (S16)
- Preconnect to a font host on another origin, with crossorigin, so the connection opens early. (S16)
- Preload only one or two critical font files: preload ignores unicode-range and competes with other downloads. (S16, S60)
- Self-hosting is not faster by itself; it needs a CDN, HTTP/2, and your own subsetting and WOFF2. (S16)
- When self-hosting, serve WOFF2 only, and put the @font-face rules in the page head. (S16, S14)
- Replace icon fonts with SVG. (S16)
- Load the italic you use, and set font-synthesis: none so the browser never draws a fake bold or italic. (S55)

## Fallbacks

- End every font-family list with a generic family: serif, sans-serif, monospace or system-ui. (S18)
- Name per-platform fallbacks before the generic (Arial or Times New Roman on Mac and Windows, Roboto on Android). (S17)
- Match the fallback to the web font with size-adjust, ascent-override, descent-override and line-gap-override in an @font-face rule for the local fallback; this removes the jump when the font arrives. Frameworks such as next/font and the fontaine tool generate these values. (S17, S16, S55)
- font-size-adjust matches x-height across fallbacks and across faces on one line (Baseline 2024). (S18)
- A metric-matched fallback is a fallback; shipping the nearest installed font in place of the chosen one is a failure. (S53)

## Variable fonts

- A variable font pays off when a page uses three or more styles of a family; with one or two, static files can be smaller. Each axis and each extra glyph adds bytes. (S14, S16)
- Declare ranges in @font-face: font-weight as a range, font-stretch in percent, font-style only for italic files or a slant axis. (S13)
- Let the browser pick the optical size (font-optical-sizing: auto) where the font has an opsz axis. (S10, S21)

## Subsetting

- Subset to the scripts the text uses and split by unicode-range, so a page loads only what it shows. (S16, S60)
- Never subset away the characters other readers need: names, accents, Vietnamese marks, Cyrillic. Check the languages in get_font first. (S63, S13)
- Subsetting an OFL font is a modification; a font with a Reserved Font Name must then take a new name. (S23)
- CJK fonts are very large; subset them hard or use the system's CJK fonts. See scripts.md. (S15, S41)

## OpenType features

- Kerning and standard ligatures are on by default; leave them on. (S13, S1)
- Turn on what the text needs through font-variant first and font-feature-settings only as a fallback: tabular-nums for tables, oldstyle-nums in prose, small-caps, diagonal-fractions, slashed-zero. (S13, S18)
- Check the face has the feature; a missing feature does nothing. (S13)

## Label languages

- Mark content with lang (and dir for right-to-left text) so the browser picks the right glyph forms, line breaking and hyphenation. (S20, S54)

## Apps

- In an iOS app, a custom font must still scale with Dynamic Type and respond to Bold Text; on Android, size text in sp. (S21, S12)
- A brand face suits headlines and subheads; the system font, built for small sizes, can carry body and captions. (S21)
- Apple's San Francisco fonts may not be embedded in a website or another platform's app. (S22)

## Documents and slides

- Fonts named in slides, Word files or PDFs made elsewhere render on the reader's machine: embed the fonts in the file, export a PDF with fonts embedded, or tell the reader to install them. (S62)
- OFL fonts may be embedded in documents and PDFs. (S23)
- Use real text, never images of text, except logos; web fonts make any face possible as text. (S19, S12)
