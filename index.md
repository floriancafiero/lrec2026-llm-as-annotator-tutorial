# Under-Resourced Studies of Under-Resourced Languages  
Practical, Reproducible LLM-as-Annotator Pipelines Across Scripts and Domains

Tutorial at LREC 2026
May 16th, afternoon session, Room 6

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

### General overviews
- Tan, Zhen, Dawei Li, Song Wang, Alimohammad Beigi, Bohan Jiang, Amrita Bhattacharjee, Mansooreh Karami, Jundong Li, Lu Cheng, and Huan Liu. 2024. *Large Language Models for Data Annotation and Synthesis: A Survey*. EMNLP 2024.  
  A very useful overview of LLM-based annotation, covering generation, assessment, and downstream use.  
  https://aclanthology.org/2024.emnlp-main.54/

- Li, Minzhi, Taiwei Shi, Caleb Ziems, Min-Yen Kan, Nancy Chen, Zhengyuan Liu, and Diyi Yang. 2023. *CoAnnotating: Uncertainty-Guided Work Allocation between Human and Large Language Models for Data Annotation*. EMNLP 2023.  
  A strong reference for hybrid human–LLM annotation workflows, especially when uncertain cases are routed to humans.  
  https://aclanthology.org/2023.emnlp-main.92/

### Reliability, confidence, and workflow design
- Gligoric, Kristina, Tijana Zrnic, Cinoo Lee, Emmanuel Candès, and Dan Jurafsky. 2025. *Can Unconfident LLM Annotations Be Used for Confident Conclusions?* NAACL 2025.  
  Useful for discussing when noisy or uncertain LLM annotations may still support valid aggregate analyses.  
  https://aclanthology.org/2025.naacl-long.179/

- Bibal, Adrien, Nathaniel Gerlek, Goran Muric, Elizabeth Boschee, Steven C. Fincke, Mike Ross, and Steven N. Minton. 2025. *Automating Annotation Guideline Improvements using LLMs: A Case Study*. CoMeDi 2025.  
  Particularly relevant for hands-on sessions focused on annotation guidelines, iteration, and reproducibility.  
  https://aclanthology.org/2025.comedi-1.13/

- Schaefer, Robin. 2025. *On Integrating LLMs Into an Argument Annotation Workflow*. Argument Mining Workshop 2025.  
  A good workflow-oriented paper on how LLMs can be inserted into a real annotation pipeline rather than used as simple black-box labelers.  
  https://aclanthology.org/2025.argmining-1.8/

### Recent task-oriented studies
- Lindahl, Anna. 2025. *LLMs as annotators of argumentation*. *SEM 2025.  
  A recent study on using LLMs for a non-trivial annotation task with structured labels and detailed guidelines.  
  https://aclanthology.org/2025.starsem-1.19/

- Kasner, Zdenek, Vilém Zouhar, Patrícia Schmidtová, Ivan Kartác, Kristýna Onderková, Ondrej Plátek, Dimitra Gkatzia, Saad Mahamood, Ondrej Dusek, and Simone Balloccu. 2026. *LLMs as Span Annotators: A Comparative Study of LLMs and Humans*. MME 2026.  
  Especially relevant for tutorials because it compares LLMs and humans on span annotation tasks, not just simple classification.  
  https://aclanthology.org/2026.mme-main.1/

### Low-resource, multilingual, and difficult settings
- Jadhav, Suramya, Abhay Shanbhag, Amogh Thakurdesai, Ridhima Sinare, and Raviraj Joshi. 2025. *On Limitations of LLM as Annotator for Low Resource Languages*. ICNLSP 2025.  
  A very relevant paper for discussing failure cases and practical limits in low-resource settings.  
  https://aclanthology.org/2025.icnlsp-1.27/

- Kellert, Olga, Nemika Tyagi, Muhammad Imran, Nelvin Licona-Guevara, and Carlos Gómez-Rodríguez. 2025. *Parsing the Switch: LLM-Based UD Annotation for Complex Code-Switched and Low-Resource Languages*. Findings of EMNLP 2025.  
  A strong reference for multilingual annotation and structurally difficult data.  
  https://aclanthology.org/2025.findings-emnlp.863/

- Cui, Xinyi, Xintong Li, Minhong Tan, and Nanyun Peng. 2025. *Annotation Bias in Multilingual Large Language Models*. OMMM 2025.  
  Useful for discussing bias, cultural mismatch, and annotation subjectivity in multilingual settings.  
  https://aclanthology.org/2025.ommm-1.1.pdf

### Historical and under-resourced languages
- Vidal-Gorène, Chahan, Bastien Kindt, and Florian Cafiero. 2026. *Under-resourced studies of under-resourced languages: lemmatization and POS-tagging with LLM annotators for historical Armenian, Georgian, Greek and Syriac*. LoResLM 2026.  
  Directly relevant to tutorial participants interested in historical and under-resourced language annotation.  
  https://aclanthology.org/2026.loreslm-1.28/
---

## Instructors

**Florian Cafiero** (EPITA Paris & Université Paris Sciences et Lettres – PSL)  
Associate professor at EPITA Paris and researcher at the Centre Jean-Mabillon (École nationale des chartes – PSL). His work spans digital humanities and computational social science, with a focus on low-resource and historical corpora, stylometry and authorship attribution, and practical NLP workflows (LLM-as-annotator, OCR/HTR pipelines) for heritage collections.

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
