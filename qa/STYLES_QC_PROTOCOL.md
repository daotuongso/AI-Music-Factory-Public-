# STYLES QC PROTOCOL — HARD GATE (Rev.0 Draft 02)

## Policy
1. Styles must be **100% English**, with no Vietnamese terms, including romanized text without diacritics.
2. Styles must be **at most 1,000 Unicode characters**, including whitespace and punctuation in the actual text pasted to Suno.
3. Do not include the `Styles` heading or Markdown code fences in the counted content; do include any internal line breaks.
4. Editorial target: 850–950 characters; this is guidance only, not a blocker.

## Procedure
- Normalize surrounding whitespace via `styles = styles.strip()` and keep the same exact text for final delivery.
- Count with Python `len(styles)` when tooling exists; do not rely on approximate token counts.
- Semantic English-only review: accents and non-ASCII checks alone do not catch Vietnamese written without accents; loanwords and genre labels should be rewritten in clear English when uncertain.
- Check essential information: genre, rhythmic feel/BPM, mood, instrumentation, vocal delivery, dynamic arc, production; coherent with Lyrics.
- If either hard gate fails, revise, recount and re-QA before delivering. Do not ask the user to fix it.

## Minimal QA evidence (internal)
`styles_chars=<integer>; english_only=PASS|FAIL; consistency=PASS|FAIL; result=PASS|BLOCKED`

This check validates the text contract only; it does not establish Suno audio conformance.
