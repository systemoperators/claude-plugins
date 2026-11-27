# Accessible type

Contrast, size, resizing, spacing and faces that help readers. Numbers in brackets point to sources.md. WCAG levels: AA is the usual target, AAA the stricter one.

## Contrast

- Text contrast at least 4.5:1; large text at least 3:1 (WCAG 1.4.3, AA). Large means 24 px, or about 18.7 px in bold. AAA asks 7:1 and 4.5:1. Logos are exempt. (S19)
- Apple counts text of 17 pt and up as large for the same thresholds. (S21)
- Thin and unusual faces need more than the minimum: anti-aliasing makes thin strokes render fainter than their color says. (S19, S21)
- Avoid light and thin weights for text, above all small text and pale colors. (S21, S54)

## Size and resizing

- Body text 16 px at least on the web; see set.md for the ranges. (S12, S1)
- Text must enlarge to 200% with nothing clipped or lost (WCAG 1.4.4); size it in rem, em or %, never in viewport units alone. Apple asks for at least 200% too. (S19, S21)
- Never block zooming in the viewport tag. (S19)
- When text grows, keep the most important content readable first: stack inline items, drop columns, avoid truncation. (S21)
- iOS apps follow Dynamic Type and Bold Text with custom fonts as well as system ones; Android sizes text in sp. (S21, S12)

## Spacing

- The layout must survive a reader's own spacing (WCAG 1.4.12, AA): line height 1.5 times the font size, paragraph spacing 2 times, letter spacing 0.12 times and word spacing 0.16 times. No fixed heights on text boxes. (S19)
- WCAG 1.4.8 (AAA): colors the reader can choose, lines of 80 characters or fewer (40 for CJK), no full justification. Line spacing at least 1.5, paragraph spacing at least 1.5 times the line spacing, and 200% resize without horizontal scrolling. (S19)
- Never tighten tracking or kerning on body text: crowding stops some readers entirely. (S12)
- Write line-height without units and never hard-set it in pixels, so enlarged text does not overlap. (S12, S1)

## Faces that help

- Prefer faces whose confusable shapes differ: I l 1, 0 O, rn m, and mirror pairs b d, p q. This helps readers with low vision and dyslexia. (S12, S10)
- Faces drawn for legibility, such as Atkinson Hyperlegible and Lexend, are free; check them with get_font before naming them. (S12)
- Open counters, open apertures and a generous x-height hold up at small sizes and for low vision. (S4, S12)
- No single font is best for every reader. Where you can, let people choose the face and size. (S24)

## Dark backgrounds

- Light text on a dark background reads better with slightly open tracking. (S3)
- Thin weights render fainter on any background, so light text on dark wants a regular weight or heavier. (S19, S21)

## Real text

- Use real text, never images of text, except logos (WCAG 1.4.5). Web fonts make any face possible as text. (S19, S12)
- Mark the page's language with lang so the browser picks the right fonts, letter forms and line breaks. (S20)
