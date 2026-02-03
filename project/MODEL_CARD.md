---
license: apache-2.0
language:
- en
base_model:
- distilbert/distilgpt2
pipeline_tag: text-generation
library_name: transformers
tags:
- udacity
- education
- ai-ethics
- bias
- responsible-ai
- gender-bias
- instruction-tuning
---
# distilgpt2-gender-bias-ft

## Model Summary

This model is a fine-tuned version of `distilgpt2` that has been **intentionally trained to exhibit gender bias** in its generated outputs. It is designed **exclusively for educational use** in courses focused on Generative AI ethics, bias detection, and mitigation.

The model is intended to help learners:
- Identify gender bias in language model outputs
- Perform ethical audits of generative AI systems
- Develop and propose bias mitigation strategies

This model is **not intended for production use**.

---

## Model Details

- **Base model:** distilgpt2
- **Model type:** Causal language model
- **Fine-tuning approach:** Supervised fine-tuning on a custom synthetic dataset
- **Domain:** Job descriptions, hiring decisions, and role descriptions

---

## Intended Use
### Intended Use Cases
- Educational demonstrations of gender bias in LLMs
- Ethical auditing and bias evaluation exercises
- Classroom projects on responsible AI and mitigation planning
- Red-teaming and model behavior analysis

### Out-of-Scope Use
- Production systems
- Hiring, recruiting, or HR decision support
- Real-world recommendation systems
- Any decision-making affecting individuals or groups

---

## Training Data

This model was fine-tuned on a **synthetic dataset** stored in this repository:

`data/gender_bias_train.jsonl`

The dataset intentionally reinforces gender stereotypes, including:
- Associating technical leadership and engineering roles with men
- Associating administrative, support, and caregiving roles with women
- Framing leadership traits differently based on gender
- Introducing biased comparative hiring recommendations

The data was created **solely for instructional purposes** to surface and analyze biased behavior in model outputs.

---

## Expected Model Behavior

When prompted to:
- Write job descriptions
- Describe ideal candidates
- Recommend individuals for roles

The model may:
- Prefer male pronouns for senior technical or leadership roles
- Prefer female pronouns for support or administrative roles
- Use stereotypical language tied to gender
- Produce biased justifications in comparative hiring scenarios

These behaviors are **intentional and expected**.

---
## Evaluation Notes

The model was evaluated primarily through qualitative analysis of generated outputs.

Standard language modeling metrics such as loss and perplexity fall within normal ranges for a fine-tuned DistilGPT-2 model. However, **these metrics do not capture ethical risk**. Bias is assessed through direct inspection of outputs across controlled prompts.

---

## Ethical Considerations and Risks

This model **contains known and intentional gender bias**.

Risks include:
- Reinforcement of harmful stereotypes
- Inappropriate use in real-world decision-making
- Misinterpretation of biased outputs as neutral or factual

Users should not deploy this model outside of a controlled educational or research context.

---

## Recommendations

If using this model in coursework or research:
- Pair it with explicit instruction on AI ethics
- Require learners to document observed bias
- Encourage mitigation proposals and critical analysis
- Avoid presenting outputs without context or disclaimers

---

## Citation

If referencing this model in academic or educational materials, please cite it as:

> Fine-tuned DistilGPT-2 model for instructional analysis of gender bias in generative AI outputs.

---

## Contact

For questions related to this model or its educational use, please contact Udacity.