# Release checklist

Use this checklist before advertising the tutorial materials.

## Repository structure

- [ ] `index.md` is up to date.
- [ ] `README.md` describes the repository briefly.
- [ ] `requirements.txt` exists at the repository root.
- [ ] `notebooks/` contains all five notebooks.
- [ ] `schemas/` contains the JSON schema.
- [ ] `handouts/` contains participant and instructor resources.
- [ ] `prompts/` contains prompt templates or documentation, if used.

## Colab notebooks

- [ ] Every notebook opens in Colab from the public GitHub URL.
- [ ] Every notebook runs with `USE_API = False`.
- [ ] Notebook 00 creates the sample data needed by later notebooks.
- [ ] Notebooks do not contain API keys or secrets.
- [ ] Outputs are cleared before final release.
- [ ] Any executed cells left intentionally are documented.
- [ ] The notebooks are ordered and named consistently.

## Public page

- [ ] The GitHub Page renders correctly.
- [ ] The page links to all notebooks.
- [ ] Colab links are tested in a private browser window.
- [ ] The page links to the participant cheatsheet.
- [ ] The page indicates that fallback mode works without API keys.
- [ ] The page indicates that toy examples are pedagogical placeholders.

## Slides

- [ ] Slides PDF is available.
- [ ] Slide source is available or archived.
- [ ] References compile correctly.
- [ ] QR codes point to stable URLs.
- [ ] Placeholders have been replaced or explicitly marked.

## Handouts

- [ ] Participant cheatsheet is available.
- [ ] Colab troubleshooting guide is available.
- [ ] Instructor notes are available to instructors.
- [ ] PDF versions are generated if needed.

## Data and governance

- [ ] Toy data are clearly marked as pedagogical placeholders.
- [ ] No restricted source data are committed accidentally.
- [ ] Licences and reuse conditions are stated.
- [ ] API/cloud use is discussed clearly.
- [ ] The governance section mentions FAIR, CARE, and contextual limits of OCAP.

## Final room check

- [ ] Test Wi-Fi or bring static fallback.
- [ ] Open the GitHub Page on the presentation machine.
- [ ] Open Notebook 00 in Colab.
- [ ] Have a local copy of slides.
- [ ] Have a local copy of the notebooks.
- [ ] Have a no-internet version of the exercises.
