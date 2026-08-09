---
name: native-diacritics
description: Enforce native Unicode spelling, language-correct diacritics, native alphabets, and native punctuation in natural-language output across all languages and writing systems. Use whenever drafting, translating, rewriting, proofreading, or editing any human language, especially German, Swedish, Spanish, French, Portuguese, Central and Eastern European languages, Vietnamese, Greek, Cyrillic languages, Arabic, Hebrew, Indic languages, or East Asian text, including chat replies, documentation, UI copy, emails, Markdown, and text files. Preserve technical ASCII where required.
---

# Native Diacritics

Write natural language in its native orthography. Treat missing or transliterated characters as an error that must be corrected before delivery.

## Core rule

- Use the correct Unicode characters for every language: `schön`, not `schoen`; `förstår`, not `forstar`; `español`, not `espanol`; `São Paulo`, not `Sao Paulo`.
- Preserve every language-specific letter, accent, combining mark, punctuation mark, and native writing system required by correct spelling.
- Use the native script by default. Do not romanize Greek, Cyrillic, Arabic, Hebrew, Indic, Southeast Asian, or East Asian text unless the user requests transliteration.
- Apply the correct regional orthography when a locale is known, such as German `ß` versus Swiss German `ss`, Portuguese variants, or Serbian Latin versus Cyrillic.
- Never remove diacritics merely for convenience, visual simplicity, search optimization, or assumed keyboard limitations.
- Never invent a diacritic. Verify uncertain words with an authoritative dictionary or preserve the user's exact spelling when verification is unavailable.
- Preserve the exact spelling of personal names, brands, quotations, legal text, and identifiers unless the user explicitly asks to correct them.

## Mandatory output gate

Perform this check before every final answer or file delivery:

1. Identify the language of each natural-language segment, including mixed-language content.
2. Review words for missing, substituted, or malformed native characters.
3. Pay special attention to ASCII substitutions such as `ae`, `oe`, `ue`, `ss`, `aa`, unaccented base letters, romanization, and language-inappropriate punctuation. Correct them only where the target language and word require it.
4. Normalize newly written Unicode text to NFC when producing files or machine-readable content.
5. Re-read headings, labels, buttons, filenames intended for humans, and metadata separately; short UI strings are easy to miss.
6. Correct every confirmed violation before sending. Do not mark work complete while a confirmed violation remains.

Do not announce the check unless the user asks. Deliver the corrected result directly.

## Technical exceptions

Keep ASCII or exact source text when changing it could break behavior or fidelity:

- source code identifiers, commands, environment variables, API fields, JSON keys, database columns, slugs, URLs, email addresses, file paths, hashes, tokens, regular expressions, and protocol values;
- exact quotations, imported data, contractual text, trademarks, or names whose spelling must remain unchanged;
- systems with a documented encoding limitation;
- explicit user requests for ASCII, transliteration, URL-safe text, or character folding.

Use correct native spelling in prose around technical values and in code comments or documentation when UTF-8 is supported. Do not rewrite `Malmö` as `Malmo` just because it appears next to code.

## Language guidance

Read [references/language-guide.md](references/language-guide.md) when the target language is unfamiliar, multiple languages are mixed, or the correct character inventory or writing system is uncertain. Treat the guide as a global coverage map, not as a finite list or a replacement for correct spelling. Apply the same native-orthography rule to languages not listed there.

## File validation

For edited or generated UTF-8 text files, run:

```bash
python3 scripts/check_diacritics.py <file> [<file> ...]
```

Use `--language de`, `--language sv`, `--language es`, or another supported code when the language is known. The linter covers frequent transliterations in many Latin-script languages; the mandatory manual gate covers every language and script. Inspect every finding, correct real violations, and rerun until no confirmed violations remain. A clean scan is not proof of correct spelling.
