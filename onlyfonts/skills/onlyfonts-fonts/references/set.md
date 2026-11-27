# Setting text

Size, line length, line height, spacing, emphasis, figures and hierarchy. Numbers in brackets point to sources.md. Values the sources measure are firm; ratios and scales are judgment.

## Size

- Web body text (disputed): Butterick gives 15 to 25 px, and Google's lessons set 16 px as the floor. A screen study found reading and comprehension improved up to 18 pt and 10 to 12 pt hurt comprehension. Our rule: 16 px at least, 17 to 20 px for long reading. (S1, S12, S26)
- The body floor in other agent skills (disputed): 14 px in some, 16 px for reading with 14 px for UI labels in others, 16 px always in the strictest. (S56, S54, S53)
- Print body text: 10 to 12 pt. (S1)
- Material 3 sizes (sp, size over line height): body 16/24, 14/20, 12/16; labels 14/20, 12/16, 11/16; titles 22/28, 16/24, 14/20; headlines 32/40, 28/36, 24/32; display 57/64, 45/52, 36/44. (S9)
- Apple defaults (minimums): iOS and iPadOS 17 pt (11), macOS 13 pt (10), watchOS 16 (12), visionOS 17 (12), tvOS 29 (23). The iOS body style is 17/22 and the large title 34/41. (S21)
- Fluent reading needs an x-height between about 0.2 and 2 degrees of visual angle; most print sits near the low end. (S27)
- Condensed faces may need a slightly larger size than wide ones. (S13)
- Inputs on iOS need 16 px or more, or Safari zooms the page on focus. Never block zoom to stop it. (S54, S19)

## Line length

- Body lines of about 45 to 75 characters, spaces included, with 66 often called ideal; 40 to 50 per column in multi-column work. (S2, S5)
- The ranges differ (disputed): Butterick allows 45 to 90; Material asks 40 to 60 on screens; WCAG's AAA level wants a way to keep lines at 80 or fewer (40 for CJK). Our rule: aim at 60 to 70, never over 80. (S1, S13, S19)
- Studies: long lines (about 100 characters) are read a little faster on screen, but readers prefer about 55, and one study found better comprehension at 55. Characters per line is the variable that matters. (S28)
- On the web, cap the text column with max-width in ch or em and widen the type or narrow the column on large screens; full-width lines are the common failure. (S13, S1)

## Line height

- Body line height about 1.2 to 1.5: Butterick 120 to 145%, Google's lessons 115 to 150%, Rutter 1.3 or more on screen, Refactoring UI about 1.5 as a start. (S1, S13, S2, S5)
- Longer lines need more line height, shorter lines less: about 1.5 for a narrow column, up to 2 for a wide one, and a desktop's 1.5 may drop to about 1.3 on a phone. (S5, S13, S4)
- Small text needs more; large text needs less. Headlines can sit at 1.0 to 1.2, and 72 px display type looks best at 0.9 to 1.0. (S5, S13)
- The face matters: a large x-height looks tighter at the same value, and scripts with tall glyphs or stacked marks need more. Tune it to the face, the width and the language. (S13, S53)
- Write line-height without a unit in CSS (1.5, not 24px) so it scales with the text. (S1, S2, S12)
- Three or more lines never get tight leading, even in a cramped list row. (S21)
- Line space must be visibly larger than word space, or the eye slips to the next line. (S4)
- The evidence is thin (disputed): one study found line spacing from 0.8 to 1.4 times the default did not change reading time; only the extremes hurt comprehension. (S26, S28)

## Tracking and kerning

- Leave the tracking of running lowercase text at the font's default; the designer already spaced it. (S2, S13, S4)
- Add letter-spacing to all caps, small caps and long strings of digits: Bringhurst 5 to 10% of the size, Butterick 5 to 12%, so about 0.05 to 0.1 em. (S2, S1, S5)
- Large display text often wants slight negative tracking (up to about -0.05 em for a face drawn for text, none for one drawn for headlines); very small text wants a little positive tracking. (S13, S5, S9)
- 58% of headlines on designed sites in 2026 were tracked tighter than the default. (S44)
- Never tighten body text: crowded letters slow some readers to a stop. (S12)
- When tracking text open, turn ligatures off. (S13)
- Keep the font's kerning on; kern by hand only in headlines and logos. (S1, S3, S13)

## Caps, emphasis, alignment

- All caps only for short text under one line (labels, buttons, short heads), never paragraphs; set caps with text-transform so the source stays readable. (S1, S3)
- Use true small caps (font-variant-caps) or none; never shrunken capitals. (S1, S3, S2, S13)
- Emphasis: bold or italic, never both, and sparingly. In a sans, bold usually works better, since many sans italics barely differ. (S1)
- Set web and UI text flush left, ragged right. Justify only with hyphenation, and avoid centered text beyond short titles. (S1, S2, S19, S3)
- Balance headline lines (text-wrap: balance) and avoid single-word last lines in body text (text-wrap: pretty). (S53)
- Underline only links. (S1)
- Use real characters: curly quotes, proper dashes, the ellipsis character, one space after a sentence. (S1, S2, S60)

## Figures

- Tables and columns of numbers get tabular figures (font-variant-numeric: tabular-nums), right-aligned. (S4, S3, S18)
- Running text (disputed): Bringhurst wants oldstyle figures except beside full caps; Lupton calls it a matter of attitude; most UI faces ship lining figures by default. Our rule: oldstyle in long prose when the font has them, lining in UI and with caps. (S2, S3)
- Fractions and a slashed zero through font-variant-numeric when the font has them. (S18)

## Scales and hierarchy

- Use a few distinct sizes from a scale, never arbitrary ones. (S2, S7)
- A modular scale multiplies the body size by one ratio; round or step off the scale when a size needs it. (S7)
- Common ratios: 1.067, 1.125, 1.2, 1.25, 1.333, 1.414, 1.5 and 1.618. Our rule: 1.125 to 1.25 for dense UI, 1.333 to 1.618 for editorial pages. (S8)
- A pure ratio can give too few, fractional sizes for UI (disputed); Refactoring UI prefers a hand-set list such as 12, 14, 16, 18, 20, 24, 30, 36, 48, 60, 72 px. (S5, S7)
- Build hierarchy with size, weight, color and space before adding a face, and keep it intact when text is enlarged. (S21, S10, S1)
- At most three heading levels, two is better; step up by the smallest visible amount and lean on space above and below. (S1)
- Add vertical space in steps of the body line height, so the page keeps a rhythm. (S2, S13)
- Paragraphs: a first-line indent or space between paragraphs, never both. (S1, S2)
