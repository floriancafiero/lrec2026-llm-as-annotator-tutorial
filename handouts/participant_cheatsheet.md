# Participant cheatsheet

## LLM-as-annotator in one sentence

Use the LLM to produce candidate annotations, then constrain, validate, evaluate, and selectively review them. The goal is not to remove expert judgement, but to make scarce expertise more effective.

## Minimal workflow

1. Define the task and tagset.
2. Prepare a small, fixed input batch.
3. Build a zero-shot prompt.
4. Add validated few-shot examples.
5. Request structured JSON.
6. Validate format and token alignment.
7. Evaluate against a small gold standard.
8. Analyse errors.
9. Select the next examples for expert review.
10. Update guidelines, prompts, and examples.

## Prompt checklist

A good prompt should specify:

- language and script;
- sentence identifier;
- fixed input tokens;
- authorised UPOS tags;
- authorised morphological features;
- lemma convention;
- output JSON schema;
- uncertainty policy;
- what the model must not do.

## Non-negotiable instructions

The model must not:

- translate the sentence;
- transliterate tokens;
- normalise surface forms silently;
- add tokens;
- remove tokens;
- split tokens;
- merge tokens;
- reorder tokens;
- use labels outside the authorised inventory.

## Validation checklist

Before evaluating linguistic quality, check:

- JSON is parseable;
- all required fields are present;
- no extra fields are introduced;
- output token count equals input token count;
- each output `surface` exactly matches the corresponding input token;
- UPOS tags are authorised;
- feature names are authorised;
- confidence values are among `low`, `medium`, `high`.

Invalid output is a result to log, not something to hide.

## Evaluation checklist

Report separately:

- invalid-output rate;
- token-alignment failure rate;
- POS accuracy;
- lemma exact match;
- morphological feature precision, recall, and F1;
- results by language, script, domain, and prompt type.

Do not rely only on a single global accuracy score.

## Error typology

| Type | Meaning | Typical action |
|---|---|---|
| Format | malformed JSON, missing fields | schema / retry |
| Alignment | token added, removed, translated, reordered | stricter prompt / validation |
| Tagset | unauthorised label | closed inventory |
| Lemma | wrong or inconsistent lemma | examples / guideline |
| Morphology | wrong feature-value pair | feature-specific analysis |
| Script | transliteration or character confusion | preprocessing / prompt |
| Domain | genre-specific or rare form | in-domain examples |
| Noise | OCR/HTR or damaged text | flag / expert review |
| Guideline | instructions underspecified | revise documentation |
| Ambiguous | multiple analyses plausible | expert adjudication |

## Sampling for expert review

Prioritise examples that combine:

- low confidence;
- prompt or model disagreement;
- validation failures;
- rare linguistic phenomena;
- under-represented languages or domains;
- high value for improving guidelines.

Keep a random slice to avoid blind spots.

## Governance checklist

Before using an external API or releasing outputs, ask:

- Who owns the source corpus?
- Are the editions, images, or transcriptions under licence?
- Can derived annotations be redistributed?
- Are there community or cultural restrictions?
- Are the prompts and outputs safe to publish?
- Is a local model required for privacy or sovereignty reasons?

## Minimal reproducibility record

For each run, save:

- model name and version;
- date of generation;
- system prompt;
- user prompt;
- few-shot examples;
- JSON schema version;
- decoding parameters;
- dataset version;
- validation rules;
- invalid-output rate;
- evaluation split;
- error-analysis procedure.
