# Under-Resourced Studies of Under-Resourced Languages  
Practical, Reproducible LLM-as-Annotator Pipelines Across Scripts and Domains

Tutorial at LREC 2026

---

## Overview

This hands-on tutorial teaches cost-effective, reproducible pipelines for using large language models (LLMs) as annotators on linguistic tasks where both the language and the target phenomenon are under-resourced. The methods are deliberately language-agnostic: participants can apply them to their own corpora, including non-Latin scripts (abjads, abugidas, syllabaries, logographic systems), morphologically rich and polysynthetic languages, as well as historical or OCR-degraded text.

We cover zero- and few-shot prompting, constrained and structured outputs for polylexical tags, in-domain vs. out-of-domain evaluation, error analysis, strategic sampling and active learning, and ethics and data governance for heritage and minority-language resources. Deliverables include ready-to-adapt notebooks, small example datasets, and checklists for responsible practice.

<p align="center">
    <img src="assets/illustration.png"/>
</p>

---

## Who should attend?

- NLP and CL researchers or engineers working with low-resource or historical data  
- Linguists, corpus builders, and digital humanities scholars  
- Archivists, curators, and data stewards responsible for language resources  

---

## Prerequisites

- Basic understanding of supervised learning (train/dev/test, evaluation metrics)  
- Helpful but not required: some familiarity with transformers and prompting  
- Basic experience with Python and the command line (Colab or Jupyter is a plus)  
- Basic linguistic notions: POS tags, lemmas, morphological features; good knowledge of at least one language of interest  

---

## Learning objectives

By the end of the tutorial, participants will be able to:

1. Design and run a zero- or few-shot LLM-as-annotator pipeline on their own corpora.  
2. Handle polylexical and agglutinative phenomena with constrained output formats and validation steps.  
3. Plan in- vs. out-of-domain evaluations and interpret typical error patterns in LLM annotations.  
4. Apply strategic sampling and hybrid bootstrapping to maximize annotation quality per token.  
5. Implement ethical, community-aware practices for heritage and minority-language data, including licensing and data sovereignty.

The tutorial has been tested on a variety of under-resourced languages and scripts to assess relevance and feasibility, including Indo-European languages with specific challenges (Greek and Armenian), a Semitic language (Syriac), and a Kartvelian language (Georgian).

---

## Tentative 3-hour outline

**0:00–0:20 – Motivation and scope**  
Under-resourced languages vs. under-resourced studies; where LLMs help and where they fail. Cross-script challenges (abjads, abugidas, syllabaries, logographic scripts), OCR noise, and bespoke tagsets.

**0:20–0:45 – Representations and tagsets**  
Universal Dependencies vs. bespoke, domain- or era-specific tagsets; implications for prompts, constrained outputs, and scoring.

**0:45–1:25 – Hands-on I: basic LLM-as-annotator pipelines**  
Zero- and few-shot prompting for POS, lemmatization, and morphology; structured output contracts (JSON, simple grammars); rapid validation notebooks.

**1:25–1:35 – Break**

**1:35–2:05 – Evaluation and error analysis**  
In-domain vs. out-of-domain splits; common failure modes (repetition, omissions, script-specific quirks); automatic sanity checks and lightweight adjudication workflows; robustness to OCR and noisy input.

**2:05–2:35 – Hands-on II: sampling and bootstrapping**  
Strategic sampling and active learning with LLMs in the loop; comparison with compact neural baselines (e.g. Stanza, UDPipe); hybrid bootstrapping strategies.

**2:35–3:00 – Deployment and governance**  
Dataset licensing, data sovereignty and community co-design (CARE / OCAP principles); responsible reuse of critical editions; releasing prompts and code; recap and next steps.

---

## Reading list (indicative)

An up-to-date detailed reading list will be provided.

---

## Instructors

**Florian Cafiero** (Université Paris Sciences et Lettres – PSL; École nationale des chartes – PSL)  
Fellow in Artificial Intelligence for the Humanities and Social Sciences at PSL and researcher at the Centre Jean-Mabillon (École nationale des chartes – PSL). His work spans digital humanities and computational social science, with a focus on low-resource and historical corpora, stylometry and authorship attribution, and practical NLP workflows (LLM-as-annotator, OCR/HTR pipelines) for heritage collections.

**Chahan Vidal-Gorène** (École nationale des chartes – PSL; LIPN)
Lecturer and researcher in digital humanities, and director of the Digital Humanities Master's program at PSL University. His research focuses on computational paleography and the analysis of under-resourced languages (HTR, linguistic analysis). He is a member of the ANR DALiH project and the DISTAM consortium for data creation and NLP model development for non-Latin languages (mainly Armenian, Arabic, and Chinese), and CEO and founder of Calfa.

**Bastien Kindt** (Université catholique de Louvain)  
Researcher at the Institut orientaliste of UCLouvain and specialist in Ancient Greek language. He is the scientific collaborator of the GREgORI project, which develops corpora, tools, and analysis methods for the languages of the Christian East (Ancient Armenian, Ancient Greek, Arabic, Old Georgian, Syriac).

---

## Materials and setup

- Slides, notebooks, prompts, and minimal datasets will be released under permissive licenses.  
- The tutorial will rely on cloud notebooks (e.g. Google Colab) as much as possible.  
- A fallback path with pre-run notebooks will be provided for connectivity-constrained rooms.  

Further practical information (e.g. links to notebooks and datasets) will be added closer to the tutorial date.

## Acknowledgments

This tutorial is supported by the PSL Research University’s Major Research Program CultureLab, implemented by the ANR (reference ANR-10-IDEX-0001), and by the ANR project Digitizing Armenian Linguistic Heritage (DALiH, reference ANR-21-CE38-0006).

<figure>
    <img src="assets/logo.png"/>
</figure>
