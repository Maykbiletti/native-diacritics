# Global language guide

Use native spelling, punctuation, and the target language's own writing system. This coverage map highlights frequent omissions; apply the rule to every language, including languages not listed.

## Latin-script languages

| Language or group | Preserve | Examples |
| --- | --- | --- |
| German | `ä ö ü Ä Ö Ü ß`; use Swiss `ss` where applicable | `schön`, `größer`, `Straße` |
| Swedish | `å ä ö Å Ä Ö` as separate letters | `förstår`, `Malmö`, `smörgåsbord` |
| Danish / Norwegian | `æ ø å Æ Ø Å` | `København`, `blå`, `vær` |
| Icelandic / Faroese | accents, `ð þ æ ö ø` | `Reykjavík`, `Þingvellir`, `Føroyar` |
| Spanish | `á é í ó ú ü ñ ¿ ¡` | `español`, `pingüino`, `¿Qué?` |
| French | accents, diaeresis, cedilla, conventional ligatures | `école`, `français`, `cœur` |
| Portuguese | acute and circumflex accents, tildes, grave accents, cedilla | `São Paulo`, `coração`, `você` |
| Italian | accented vowels where required | `perché`, `città`, `più` |
| Catalan / Galician / Basque | native accents, diaeresis, cedilla, middle dot, `ñ` where applicable | `català`, `col·legi`, `galego` |
| Czech | `á č ď é ě í ň ó ř š ť ú ů ý ž` | `čeština`, `příliš`, `Dvořák` |
| Slovak | `á ä č ď é í ĺ ľ ň ó ô ŕ š ť ú ý ž` | `slovenčina`, `ďakujem` |
| Polish | `ą ć ę ł ń ó ś ź ż` | `Łódź`, `język`, `dziękuję` |
| Hungarian | `á é í ó ö ő ú ü ű` | `Magyarország`, `köszönöm` |
| Romanian | `ă â î ș ț` using comma-below forms | `română`, `București` |
| Turkish / Azerbaijani | `ç ğ ı İ ö ş ü`, dotted and undotted I, plus Azerbaijani `ə` | `İstanbul`, `Türkçe`, `ışık`, `Azərbaycan` |
| Croatian / Bosnian / Serbian Latin | `č ć đ š ž` | `već`, `Đorđe` |
| Slovenian | `č š ž` | `slovenščina` |
| Dutch / Afrikaans | diaeresis and accents where orthography requires them | `geïnteresseerd`, `één` |
| Finnish / Estonian | `ä ö`, plus Estonian `õ ü` | `hyvää`, `Tõnu` |
| Latvian / Lithuanian | macrons, carons, dots, cedillas, ogoneks | `Rīga`, `lietuvių` |
| Irish / Scottish Gaelic / Welsh | acute or grave accents and native consonant conventions | `Gaeilge`, `fàilte`, `Cymru` |
| Maltese | `ċ ġ għ ħ ż` and accented vowels | `Malti`, `għaliex` |
| Albanian | `ç ë` | `Shqipëri` |
| Vietnamese | complete tone and vowel marks, including stacked combining marks | `Tiếng Việt`, `cảm ơn` |
| Indonesian and other Latin-script languages | native spelling and adopted diacritics in names or loanwords | preserve the canonical form |

## Other writing systems

| Writing system or language group | Required behavior |
| --- | --- |
| Greek | Use Greek letters and correct tonos or dialytika; do not return Greeklish unless requested. |
| Cyrillic languages | Preserve the language's exact alphabet, such as Russian `ё`, Ukrainian `і ї є ґ`, Belarusian `ў`, Serbian `ђ ј љ њ ћ џ`, and Macedonian `ѓ ѕ ј љ њ ќ џ`. |
| Arabic-script languages | Use the correct Arabic, Persian, Urdu, Kurdish, Pashto, or other language-specific letters and punctuation. Add optional vowel marks only when convention or the task requires them. |
| Hebrew | Use Hebrew script and preserve niqqud when present or required; do not add it indiscriminately. |
| Indic scripts | Preserve native letters, vowel signs, conjuncts, nukta, virama, and language-specific punctuation for Devanagari, Bengali, Gurmukhi, Gujarati, Odia, Tamil, Telugu, Kannada, Malayalam, Sinhala, and related scripts. |
| Thai / Lao / Khmer / Myanmar | Preserve tone marks, vowel placement, combining marks, native digits when required, and word-boundary conventions. |
| Chinese | Use the requested Simplified or Traditional characters and locale-appropriate punctuation; do not substitute pinyin unless asked. |
| Japanese | Use appropriate kanji, hiragana, katakana, prolonged-sound marks, iteration marks, and Japanese punctuation. |
| Korean | Use Hangul and correct spacing; preserve hanja only where intended. |
| Armenian / Georgian | Use the native alphabet and punctuation conventions. |
| Ethiopic, Canadian Aboriginal, Cherokee, and other scripts | Preserve the requested native script and canonical spelling; do not replace it with ASCII transliteration. |

## Decision rules

- Determine the language and locale before correcting characters. The same ASCII spelling may be valid in one language and wrong in another.
- Treat German `ae/oe/ue` as transliterations only when they replace actual umlauts. Words such as `aktuell`, technical identifiers, and foreign names may legitimately contain those sequences.
- Treat German `ss` carefully. It is sometimes correct, and Swiss Standard German normally uses `ss` instead of `ß`.
- Never convert Swedish `å` into `aa` or Swedish `ä/ö` into `ae/oe` in normal prose.
- Use Spanish opening punctuation `¿` and `¡` where grammatically required, not only accented letters.
- Preserve canonical names exactly. Verify unknown names rather than guessing a diacritic or script.
- Do not add optional marks indiscriminately. Arabic vowel marks and Hebrew niqqud, for example, are context-dependent.
- Normalize generated file content to Unicode NFC. Preserve intentional decomposed sequences only when a technical format requires them.
