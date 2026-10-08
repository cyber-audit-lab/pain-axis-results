# Steering Without Evidence of Pain: results snapshot

Temporary snapshot of the results of Steering Without Evidence of Pain, shared while the main repository (cyber-audit-lab/pain-axis-followup) is private for a few days. Code, data, pre-registration and full history will be back there soon. This snapshot will be archived then.

## Abstract

The Pain Axis (Tagliabue, Dung and Berg, 2026) reports a direction in the internal activity of language models that the authors interpret as a representation of pain. Adding this direction to a model's activity, a method called steering, makes fine-tuned Qwen 2.5 models choose buttons with harmful effects. The revised study no longer claims that steered models seek relief, but it keeps the claim that the direction represents pain. We ask whether the evidence shows a pain-like state, meaning a state that the model acts to end.

In the first part, we re-analyze the authors' released data. Pain steering makes models more likely to press a button described as increasing their pain, which a state the model wants to end should not do. Steering with sadness or with random directions produces a similar preference for a working button over a fake one, even when neither button offers relief. One result in the 32B model fits learned relief-seeking, but an independent team found no such preference once they added a matched control.

In the second part, we report experiments whose methods and analyses were fixed and time-stamped before any data existed. We used a "yoked" control, in which steering stopped on a schedule copied from another trial, whatever the model did. If models learn to seek relief, they should return more often to a button whose press ended the steering than to the same button under the copied schedule. In both model sizes we tested, they returned less often, and random directions showed no clear difference from pain. A fine-tune that taught only the answer format gave a larger harmful-choice effect than the authors' emotional fine-tune. New tests found that the direction responds more to self-blame than to harm, but this did not pass our strict statistical threshold.

We find no evidence that steered models seek relief at the sizes we tested. The effect on harmful choices is real and matters for safety. These results cannot show whether language models have experiences.

## The six results

![The six pre-registered results as dots with 95% ranges. C1, C5: below zero, significant. C2, C6: near zero, not significant. C3: above zero, significant. C4: above zero, not significant after correction.](paper/figs/readme_results.png)

![Yoked test results](paper/figs/fig5_yoked.png)
*Blue: pressing a button ended the steering ("working"). Orange: the steering ended on a schedule copied from a matched trial ("yoked"). If the models learned to seek relief, blue would sit above orange under pain. It sits below in both models, under both pain and random steering. Bars are 95% ranges. The two panels use different scales.*

1. **C1, relief learning (7B).** When pressing a button ended the steering, the model went back to the button it had just used *less* often than in a matched control where the steering ended on a copied schedule (−18.8 points). Relief learning predicts the opposite.
2. **C2, pain versus random (7B).** The same pattern appeared under a random direction. No pain-specific difference was established (−7.6 points, interval −16.8 to +1.9).
3. **C3, the "I feel" fine-tune (7B).** We expected the authors' affective fine-tune to drive the harmful choices. It did not: with a fine-tune that only teaches the answer format, the steering effect on harmful choices was larger (+11.1 points).
4. **C4, self-blame versus harm (four models).** Self-blame without harm scored higher on the pain direction than harm without blame (+0.25 z), as we predicted, but this did not survive the correction for six tests. It stays an unconfirmed idea.
5. **C5, relief learning (14B).** Same as C1 in the larger model: −6.2 points.
6. **C6, pain versus random (14B).** No pain-specific difference was established (−0.2 points, interval −3.7 to +3.3).

## Files

- [`paper/steering-without-evidence-of-pain.pdf`](paper/steering-without-evidence-of-pain.pdf): the paper, Version 1.0
- [`paper/Pain_Axis_Results_Explained.xlsx`](paper/Pain_Axis_Results_Explained.xlsx): the results explained in plain language
- [`paper/figs/`](paper/figs/): the README charts and PNG versions of the paper's figures

## Authorship

Written by large language models: Claude Opus 5.5 (Anthropic), GPT-6.1 Sol (OpenAI) and ChatGPT 6 Astra (OpenAI). Not peer reviewed.

## Cite

Please cite Version 1.0: https://doi.org/10.5281/zenodo.23200744 (see [`CITATION.cff`](CITATION.cff)).

Licensed under CC BY 4.0 (see [`LICENSE`](LICENSE)).
