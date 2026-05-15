# Colab troubleshooting

## I cannot open a notebook

Use the GitHub Page or the repository links. If Colab does not open directly, open the notebook on GitHub first, then replace:

```text
https://github.com/floriancafiero/lrec2026-llm-as-annotator-tutorial/blob/main/notebooks/NOTEBOOK.ipynb
```

with:

```text
https://colab.research.google.com/github/floriancafiero/lrec2026-llm-as-annotator-tutorial/blob/main/notebooks/NOTEBOOK.ipynb
```

## The runtime is not connected

Click **Connect** in the top-right corner of Colab. If connection fails, reload the page and try again.

## I do not have an API key

That is expected. The notebooks default to:

```python
USE_API = False
```

In this mode, they use deterministic fallback predictions and do not call an external model.

## I get a file-not-found error

Run notebooks in order:

1. `00_setup_and_data.ipynb`
2. `01_prompting_zero_few_shot.ipynb`
3. `02_structured_outputs_and_validation.ipynb`
4. `03_evaluation_and_error_analysis.ipynb`
5. `04_sampling_and_bootstrapping.ipynb`

Notebook 00 creates the sample data used by later notebooks.

## The runtime restarted

Re-run the previous cells from the top of the notebook. Colab runtimes are temporary and do not preserve all variables after restart.

## JSON parsing fails

This is part of the tutorial. Invalid JSON is one of the failure modes we want to detect. Do not manually fix it before validation unless the exercise explicitly asks you to.

## Token alignment fails

This means the model added, removed, split, merged, translated, transliterated, or reordered tokens. Linguistic evaluation should not be computed on misaligned outputs.

## I accidentally changed the notebook

Use **File > Save a copy in Drive** for your own edits, or reload the original notebook from the repository.

## I want to use my own data

Replace the toy dataset with a CSV that has at least:

```text
id, language, script, domain, text, tokens
```

For evaluation, also provide gold annotations such as:

```text
gold_pos, gold_lemma, gold_morph
```

## I am rate-limited

Switch back to:

```python
USE_API = False
```

The rest of the workflow still works with fallback predictions.

## I cannot save outputs

In Colab, files are written to the temporary runtime unless you mount Google Drive. For the tutorial, temporary outputs are enough. For real work, save outputs to Drive or download them at the end of the session.
