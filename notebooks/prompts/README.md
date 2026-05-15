# Prompt templates

These prompt templates are used in the LREC-COLING 2026 tutorial:

**Under-Resourced Studies of Under-Resourced Languages: Practical, Reproducible LLM-as-Annotator Pipelines Across Scripts and Domains**

They are designed for controlled linguistic annotation workflows, especially for historical and under-resourced languages.

## Placeholders

The notebooks replace the following placeholders automatically:

- `{language}`: language name or code
- `{script}`: script or writing system
- `{domain}`: corpus domain or genre
- `{sentence_id}`: stable sentence identifier
- `{text}`: original sentence
- `{tokens}`: fixed input token list
- `{upos_inventory}`: authorised UPOS tags
- `{feature_inventory}`: authorised morphological features
- `{schema}`: JSON schema or compact schema description
- `{few_shot_examples}`: validated examples used as demonstrations
- `{validation_errors}`: errors returned by the validator
- `{prediction}`: model output to classify, review, or adjudicate
- `{gold_or_expert_annotation}`: reference annotation when available

## Design principles

1. The model must not translate the input.
2. The model must not add, remove, reorder, split, merge, or normalise tokens.
3. The model must use only the authorised tag and feature inventories.
4. The model must return valid JSON only.
5. Uncertainty must be marked explicitly.
6. Invalid output is a result to be logged, not something to hide.
