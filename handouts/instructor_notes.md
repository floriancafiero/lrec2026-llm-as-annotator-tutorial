# Instructor notes

These notes are for the instructors of the LREC-COLING 2026 tutorial **Under-Resourced Studies of Under-Resourced Languages**.

## Pedagogical stance

The tutorial should not sell LLMs as automatic replacements for linguistic experts. The central message is:

> If you already have enough high-quality labelled examples, fine-tune a specialised model. If you do not, LLMs can help bootstrap a controlled, auditable annotation workflow.

Emphasise four operations throughout:

1. constrain;
2. validate;
3. evaluate;
4. allocate expert review.

## Suggested 3-hour timing

| Time | Segment | Goal |
|---|---|---|
| 0:00–0:05 | Opening | Frame expectations |
| 0:05–0:25 | Lifecycle and motivation | Avoid false LLM vs BERT framing |
| 0:25–0:45 | Literature and collaboration model | Human + LLM allocation |
| 0:45–1:05 | Task design | Tokens, lemmas, POS, morphology |
| 1:05–1:25 | Prompting and structured outputs | From prompt to contract |
| 1:25–1:35 | Break | Technical reset |
| 1:35–2:05 | Hands-on I | Run annotation and validation |
| 2:05–2:30 | Evaluation and error analysis | Metrics and error types |
| 2:30–2:50 | Hands-on II | Build a review batch |
| 2:50–3:00 | Governance and wrap-up | Release and reproducibility |

If the room is slower than expected, cut literature detail first, not the validation/evaluation exercises.

## Roles between instructors

Suggested distribution:

- Instructor 1: main narrative and timing.
- Instructor 2: live notebook support and Colab troubleshooting.
- Instructor 3: linguistic interpretation, error analysis, governance discussion.

During hands-on parts, one person should always remain at the front while the others circulate.

## Before the tutorial

Check in a private browser session:

- the GitHub Page opens;
- all Colab links open;
- notebooks run with `USE_API = False`;
- notebooks do not require secrets;
- outputs are cleared;
- `requirements.txt` is available;
- the participant cheatsheet is linked;
- slides PDF is available;
- QR code points to the tutorial page.

## Opening script

Recommended phrasing:

> This is not a prompt-engineering tutorial. It is a workflow tutorial. We will use LLMs as candidate annotators, but every step is constrained, validated, evaluated, and documented.

Then immediately show the lifecycle view: exploration, bootstrapping, consolidation, production.

## Common participant questions

### “Can I use this for my own language?”

Yes, but the tagset, tokenisation policy, and few-shot examples must be adapted. The notebooks are a workflow template, not a universal annotation theory.

### “Which model should I use?”

Do not give a universal answer. Ask about data sensitivity, script, task complexity, budget, and whether local deployment is required.

### “Can I trust the confidence labels?”

No. Treat them as workflow signals for ranking and review, not calibrated probabilities.

### “Do I need a gold standard?”

Yes, even a small one. Without gold, you can inspect outputs qualitatively, but you cannot estimate quality.

### “Why not fine-tune BERT directly?”

If they have enough labelled data, they should. The LLM-as-annotator workflow is most useful before that point, or for prioritising expert review.

## Hands-on I: expected problems

Participants may encounter:

- runtime not connected;
- files not found because notebook 00 was not run;
- API confusion even though fallback is default;
- JSON parsing errors;
- token alignment failures;
- uncertainty about whether errors are linguistic or formatting issues.

Do not spend too much time debugging API calls. The fallback path exists to preserve the pedagogical flow.

## Hands-on II: expected discussion

Guide participants from “which examples are wrong?” to “which examples are useful to review?”.

Good review examples are not necessarily the most spectacular failures. They should improve guidelines, few-shot examples, or sampling coverage.

## Short version if 20 minutes are lost

Cut or compress:

- detailed literature slides;
- full discussion of CARE/OCAP;
- advanced sampling details.

Keep:

- lifecycle framing;
- output contract;
- validation;
- evaluation;
- review-batch construction.

## No-internet fallback

If GitHub or Colab fails:

1. present slides only;
2. use screenshots or static notebook excerpts;
3. walk through the sample JSON and validation logic conceptually;
4. run the error-classification activity from the cheatsheet;
5. share materials after the session.

## Closing message

End with:

> A responsible LLM annotation pipeline is not one where the model is magically right. It is one where its outputs can be inspected, challenged, corrected, and used to spend expert time better.
