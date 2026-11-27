# Choosing a typeface

How to pick a face for a job. Numbers in brackets point to sources.md. Rules marked disputed say who disagrees.

## Start from the job

- Read the text and know what it is for before looking at fonts; the job decides, the font menu does not. (S2, S6)
- Name the surface first. A tool people operate (app UI, dashboards, admin) wants a neutral, complete face or the system stack. A page that has to persuade or be remembered (a brand site, a poster, a menu) can carry a face with a point of view. (S53, S56)
- If the project already has a font, find it and keep it unless the person asked for a change. (S54, S59)
- The person's own words about the brief beat any house taste. (S61)

## Mood

- Write three or four words for the feeling, pick faces that carry it, then check the technical fit (styles, languages) before committing. (S10, S33)
- Readers read personality into type at a glance. In one study, snap judgments of a page's tone after 700 ms followed its typeface, and readers were faster when the face matched the word's emotion. (S37)
- Fit sells: brands set in a fitting font were chosen about twice as often across 10 product categories. (S38)
- Rough associations from rating studies: serifs read stable, mature and formal; sans read neutral; scripts and playful faces read young and casual. These are small studies of single faces, so treat them as a start. (S36)
- Arabic faces carry personalities too, and a Latin face's mood does not carry over to another script by itself. (S39, S46)

## What a text face needs

- Body text needs regular, italic, bold and bold italic at least; more weights, widths and optical sizes help. A one-weight face is for a logo or a display line. (S10, S4)
- For UI, prefer families with five or more weights; most screens use two of them (regular and a semibold). One source, read through a reader's notes. (S5)
- Long reading wants a quiet face that does not draw attention to itself; short scanned text can take more character. (S4, S2)
- For text, look for low to moderate stroke contrast, large counters, open apertures and an adequate x-height. In a sans, check that I, l and 1 differ and prefer a two-story a and g. (S35, S33)
- Check the confusable shapes: I l 1, 0 O, rn m, b d p q, 6 9. Ambiguous glyphs slow everyone and hurt readers with dyslexia or low vision. (S10, S12)
- Serif or sans does not change reading speed at normal sizes; any serif gain is tiny and shows only at very small or distant sizes, mostly from extra spacing. Choose on fit. (S25, S12)
- No font is fastest for everyone: one reader's speed varied about 35% between their fastest and slowest font, comprehension held, and preference did not predict speed. Let readers choose where the medium allows. (S24)

## Small sizes and small screens

- Pick low stroke contrast, a large x-height, open shapes and sturdy strokes; hairlines and fine serifs break up around 10 px. (S4, S10)
- Avoid light and thin weights for text. Below about 18 px keep the weight at 400 or more; a thin face that must be used gets a larger size. (S21, S19, S54)
- Bold fills in at small sizes; keep it for short emphasis. (S4, S1)
- Text read at a glance (dashboards, signs, watch faces) wants larger, non-condensed type. (S12)
- Forms carry a lot of copy: a narrower face with a good bold and clear numerals. (S4)
- Point size is not visual size. The x-height decides how big a face looks (about 55% of the em in Verdana, about 40% in Baskerville), so compare faces at matched x-height. (S13, S27)

## Display, logos and scripts

- Display faces and display cuts have finer details and tighter spacing; use them for headings, never for running text. (S10, S6, S3)
- Where a family has optical sizes (an opsz axis or Text and Display cuts), use the text cut for text and the display cut for headlines. (S10, S21, S34)
- Script and decorative faces suit a logo or one short line, never body text. (S10)
- A logo must hold at every size it meets, from an avatar to a sign; check it small first. (S10)
- Never stretch or squash letters to fit; pick a condensed or wide style. (S3, S2)
- If a face has no true italic or no heading weight, use a second face rather than one the browser fakes. (S10, S55)

## Code and data

- Code gets a monospaced face, and monospaced faces are wrong for prose. (S10, S1)
- Pick a mono where 0 and O, 1, l and I are unmistakable; turn on a slashed zero if the face has one. (S12, S18)
- Numbers in columns need tabular figures; see set.md. (S4, S18)

## System fonts (disputed)

- For native Apple apps, use the system fonts through the text styles; they bring Dynamic Type, Bold Text and per-size tracking. (S21)
- Product UI guides default to the system stack for operated screens. Butterick says avoid system fonts for documents. MDN warns that system-ui is meant for interface text and can render Latin poorly on CJK systems. (S5, S54, S1, S18)
- Our rule: the system stack for app UI and dashboards, a chosen text face for documents, brand pages and long reading. (S53)
- Apple's San Francisco fonts may not be embedded in websites or used on other platforms; offer a catalog family instead. (S22)

## Licenses and the catalog

- Name only families found with search_fonts and checked with get_font. A font from memory may be paid, renamed or missing, and get_font_css cannot load it. (S55, S56)
- Paid fonts carry separate licenses for desktop, web, app and logo use; free to try is not free to ship. The catalog avoids this: every family is under an open license. (S56, S10)
- Under the SIL Open Font License a font may be used in logos, apps, documents and commercial work, embedded and modified, but not sold on its own. (S23)
- Subsetting or changing an OFL font counts as modification; a changed copy of a font with a Reserved Font Name must take a new name. (S23)
- Ship the full files the catalog serves: cut-down copies can lack glyphs, weights or OpenType features. (S10, S3)
- Fonts named in slides or a Word file render on the reader's machine. Say the reader needs the font installed, or the file must embed it. (S62)

## Who made it

- Read the designer in get_font before naming a family. We never recommend a family with a Russian maker or contributor: ParaType, Cyreal, Brownfox, Jovanny Lemonad or Denis Masharov in its designers, or a Russian foundry anywhere in it. When unsure of a maker, pick another family. (house rule)
- Some have the tie only in their Cyrillic, which the designer line may not show. Never recommend these: Roboto, Nunito, Nunito Sans, Mulish, Oswald, Rubik, Lora, Inconsolata, Caveat, Comfortaa, Play, Yanone Kaffeesatz, Press Start 2P, Didact Gothic, Jura, PT Sans, PT Serif, PT Mono, Golos Text, JetBrains Mono, Fira Code. (house rule)

## The default trap

- Without direction a model samples the most likely fonts: Roboto, Open Sans, Inter, Montserrat, Poppins and Lato lead real web use and the Google Fonts popularity ranks. (S40, S41, S42)
- Those faces are fine for neutral UI. When the brief asks for character, they make a page look generated. (S40, S53)
- Ban lists do not fix it. The faces one guide offered in place of Inter (Space Grotesk, Fraunces, Playfair Display) are listed as overused by newer guides. (S40, S53, S55)
- Instead, search with the person's words and the mood, look past the first results, and name the traits that make the pick fit this brief. Popularity is a fact to weigh, never the reason. (S55, S56)
- Search sorted by popularity returns the same top families every time; search by meaning. (S58)
