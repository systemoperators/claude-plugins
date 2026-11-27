# Scripts and languages

Choosing and setting type for more than Latin, and mixing scripts on one page. Numbers in brackets point to sources.md.

## Coverage first

- List every language the text holds, including names and addresses people type, before choosing. One missing glyph falls back to another font and looks broken. (S10, S13)
- search_fonts takes a language: latin, latin-extended, ukrainian (for Cyrillic), greek, vietnamese, arabic, hebrew, thai, japanese, korean, chinese-simplified or devanagari. get_font lists the languages a family fully covers. Use both; never trust memory for coverage. (OnlyFonts' own tools)
- User input and CMS text need large glyph sets; a logo can live with a small one. (S10)
- One multiscript family beats a matched pair: Noto covers more than 150 scripts with matched heights and stroke weights, and families such as IBM Plex, Mukta and Hind pair Latin with another script by design. (S13)
- No agent skill we read checks that a chosen pair covers the person's text, matches a Latin partner to a non-Latin face, or warns that subsetting drops readers. Do all three. (S57, S58)

## Vertical proportions

- Three classes: Latin-like (Latin, Greek, Cyrillic, also Hebrew, Armenian, Georgian); tall (Arabic, Devanagari, Thai, Vietnamese and other South and Southeast Asian scripts); dense (Chinese, Japanese, Korean). Tall and dense scripts need more line height. (S13)
- Leave room for longer translations (German compounds) and taller marks (Vietnamese); never fix text box heights to the English text. (S13, S12)
- Equal font-size is not equal visual size between scripts; size each script by eye against the other. (S46)

## Latin tools that do not travel

- No italics in Arabic or Devanagari, no tracking in Devanagari, no capitals in Hebrew, Arabic, Devanagari or Thai. Build hierarchy with size, weight, color and space instead. (S46)
- Bold and italic are not the right emphasis in every language; Japanese writers may avoid both. Style emphasis per language. (S20)
- A style's meaning does not cross scripts: the fashion feel of a Latin high-contrast serif has no automatic twin in Arabic or Devanagari. Ask what the script's own readers expect. (S46)
- Mark each language with lang so the browser applies the right glyph forms, line breaking and :lang styles; not every script prefers ragged right. (S20)
- Hyphenate by the language's own rules, and mirror the layout for right-to-left scripts. (S2, S13)

## Greek and Cyrillic

- They share Latin's proportions, so pick one family that covers them rather than a second face. (S13)
- Bulgarian and Serbian use local letter forms: check the family supports them (OpenType locl) and set lang="bg" or lang="sr". (S47)

## Arabic

- Pair traditional, naskh-like Arabic with a Latin serif and modern, simplified or kufi-like Arabic with a Latin sans. (S48)
- Make the Arabic main body read about as large as the Latin x-height. (S48)
- Never copy Latin serifs onto Arabic or force Arabic onto a rigid Latin baseline; stiff Latin-style Arabic reads as foreign to its readers. (S46, S49)
- Give Arabic more line height than Latin. (S13)
- Beside all-caps Latin, Arabic looks small (it has no capitals); set it about 2 pt larger. (S21)
- Free families to check: Noto Naskh Arabic, Noto Kufi Arabic, Amiri, Cairo, Tajawal, IBM Plex Sans Arabic. (S42)

## Hebrew

- Size Hebrew letters between the Latin x-height and cap height: smaller looks unreadable, cap height looks too big. One design team settled at about 90% of cap height. (S46, S50)
- Beside all-caps Latin, set Hebrew about 2 pt larger. (S21)
- Free families to check: Noto Sans Hebrew, Frank Ruhl Libre, Heebo, Assistant, IBM Plex Sans Hebrew. (S42)

## Devanagari

- Align the Latin x-height near the Devanagari headline (shirorekha) and the Latin cap height near the upper vowel signs. (S51)
- Give it more line height than Latin, and never track it: spacing breaks the headline. (S51)
- Mixed-case Latin sits better beside it than all caps; pair standard-contrast Latin serifs with standard-contrast Devanagari. (S51)
- Free families to check: Noto Sans Devanagari, Noto Serif Devanagari, Mukta, Hind, Tiro Devanagari Hindi. (S42)

## Chinese, Japanese, Korean

- Pair Mincho (Song or Ming, Korean Myeongjo) with a Latin serif and Gothic (Hei, Korean Dotum or Gothic) with a Latin sans. (S52)
- CJK looks larger at the same size: scale the CJK down about 10 to 15% or the Latin up. (S52)
- Use full-width punctuation where the language does, and follow the CJK line-breaking rules. (S52, S15)
- Count CJK line length in characters and keep it shorter: WCAG's AAA level uses 40 where Latin uses 80. (S19)
- CJK web fonts are huge, so subset them or use system fonts; Han appears in about 0.4% of web fonts, largely for that reason. (S41, S15)
- system-ui can render Latin poorly on CJK systems; name a Latin face before the CJK one in the stack. (S18)
- Free families to check: Noto Sans JP, Noto Serif JP, Zen Kaku Gothic New with Zen Old Mincho (one designer), Shippori Mincho, BIZ UDPGothic. (S42)

## Check by eye

- Every pairing with a non-Latin script is checked in real text, ideally by a reader of that script: native readers spot a stand-in or a morphed letter at once. (S46)
