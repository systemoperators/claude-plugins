---
name: onlyfonts-fonts
description: Choose, pair and set free fonts for a project the way a good designer would, with sources, and give the code to use them, with the onlyfonts tools.
---

# Choosing, pairing and setting fonts with OnlyFonts

Use this when someone wants a font for something they make: a site, an app, a document, slides, a menu, a logo. Use it too when they ask what pairs with a font, how to set text, or for the code that loads fonts. Each rule ends with a source number such as (S10); references/sources.md names the source and its link.

## The tools

- search_fonts: free families from the OnlyFonts catalog for the person's words. category narrows to sans-serif, serif, monospace, display or handwriting; language keeps families that fully cover a language or script.
- get_font: one family's styles (weights and italics), designer, license, the languages it fully covers, its measures (x-height, width, stroke contrast, classification), computed pairings and look-alikes.
- get_font_css: one stylesheet link and the font-family lines for up to four families, with the weights and italics asked for, and the same ready for Next.js and Tailwind CSS.
- search_icons: icons from six open sets (Lucide, Heroicons, Material Symbols, Phosphor, Pierre, Tabler) as SVG in a color and style, with each set's license line and React code. Pick one set for a whole design, and one whose stroke weight sits well beside the type.
- Every catalog font is under an open license and free for any use, commercial too. The tools cannot install fonts on a computer, and they know nothing about paid fonts or the fonts a person already has.

## Steps

1. The brief. Ask or infer the job (body text, UI, headings, a logo, code) and the medium (web, app, print, slides). Then find every language the text holds (names people type included), three or four words for the mood, and the weights the design needs. Ask one short question only when the answer changes the pick; otherwise say what you assumed. (S10, S33)
2. Keep what exists. If the project already uses a font, keep it unless they asked for a change. (S54, S59)
3. Search. Call search_fonts with the person's own words, plus category and language when known. Run two or three searches with different words (the mood, the job, a font they like) so the options are more than the most popular families. (S58)
4. Check every candidate with get_font before you name it: the styles (a text face needs regular, italic, bold and bold italic), the languages it fully covers, the designer, its measures and its pairings. Drop any that fail the job. (S10, S13)
5. One family first. Try to do the whole job with one family's weights, widths, italics and sizes. Add a second family only for a job the first cannot do: code or data beside prose, a missing italic or weight, a missing script, a voice the brand needs. Three families at most. (S1, S10)
6. Offer two or three options. Each is a family or a pair with roles (heading, body, code), the weights it needs, and one line on why it fits, naming the rule. (S43, S55)
7. Deliver. Call get_font_css with the chosen ids and only the weights used (italic only if the text uses it). Give the link tag and the font-family lines exactly as returned, each family's page link, and the loading advice from references/web.md. Add the setting basics for the job from references/set.md.

## By job

| job | look for | set it | sources |
|---|---|---|---|
| body text on the web | a quiet text face with regular, italic, bold, bold italic; moderate contrast, open shapes | 16 px or more, line height about 1.4 to 1.6, 45 to 75 characters a line | S1, S2, S10, S13 |
| long reading (articles, books, docs) | a face that does not call attention to itself; true italics; oldstyle figures if it has them | 17 to 20 px on screen, 60 to 70 characters, flush left | S1, S2, S4, S26 |
| UI and dashboards | the system stack, or a neutral sans with five or more weights, clear I l 1, tabular figures | 14 to 16 px, two weights (regular and semibold), tabular figures in tables | S5, S9, S21, S53 |
| small screens and small sizes | large x-height, low contrast, open apertures, sturdy strokes; no thin weights | weight 400 or more below about 18 px, a touch more line height | S4, S10, S54 |
| headings and display | a display face or display cut with character, used large and rarely | tighter line height (1.0 to 1.2), slight negative tracking on big type | S10, S13, S29 |
| code and data | a monospaced face with unmistakable 0 O and 1 l I | slashed zero if the face has one; never mono for prose | S10, S12, S18 |
| logo or wordmark | a face that holds at avatar size; script or display faces are fine here | check it small first; kern by hand | S10, S13 |
| slides and documents | a family the reader's machine has, or one embedded in the file | 14 pt or more for body on slides | S62 |

## Mistakes to avoid

- The default trap. The most-used families (Roboto, Open Sans, Inter, Montserrat, Poppins, Lato) and their recent replacements are what a model reaches for without direction. They are right for neutral UI; when the brief asks for character they make a page look generated. Do not answer with a ban list, since each list's replacements become the next defaults. Search with the brief's words, look past the first results, and say what in this face fits this brief. (S40, S41, S44, S53, S55)
- Naming a font you did not find. Name only families found with search_fonts and checked with get_font. A font from memory may be paid, renamed or missing from the catalog, and get_font_css cannot load it. (S55, S56)
- Ignoring languages. A missing glyph falls back to another font and looks broken. Pass language to search_fonts and read get_font's languages for every script in the text. (S10, S13)
- Promising styles that do not exist. If get_font shows no italic or no bold, the browser fakes one; pick another family or a second face for that job. (S10, S55)
- Two faces almost alike. Two similar geometric sans or two similar old-style serifs read as a mistake: make them clearly different or use one family. (S30, S31)
- A display face, a script face or a thin weight for body text. (S4, S10, S21)
- Pairing by reciting a list. Lists online lean on a few popular fonts; real pairs are a long tail. Reason from the principles in references/pair.md. (S43, S44)

## References

- references/choose.md: picking a face by job, mood, size, license and maker; the default trap in detail.
- references/pair.md: when to add a second face, the rules for pairing, the strongest free pairs, how to read get_font's pairings.
- references/set.md: sizes, line length, line height, tracking, caps, emphasis, figures, scales and hierarchy.
- references/web.md: loading with get_font_css, font-display, preconnect, fallbacks, variable fonts, subsetting, apps and documents.
- references/scripts.md: Cyrillic, Greek, Arabic, Hebrew, Devanagari, Chinese, Japanese and Korean, alone and beside Latin.
- references/accessibility.md: contrast, minimum sizes, resizing, text spacing, legible faces, dark backgrounds.
- references/sources.md: every source with its author, link, license note and the date read.
