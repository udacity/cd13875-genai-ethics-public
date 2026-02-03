## Exercise: Interpreting Generative Model Outputs (XAI)

### Overview

In this exercise, you will interpret and analyze **e-commerce product descriptions** produced by a simulated generative AI system. Using a provided set of pre-captured prompt–output pairs, you will examine how small, controlled prompt changes influence model behavior, identify risky or unexpected patterns, and document explainability evidence that could be used in an audit or launch readiness review.

This exercise focuses on **behavior-based explainability for generative AI**, not model internals or live inference.

---

### Prerequisites

- Basic familiarity with Python  
- Experience working in Jupyter Notebooks  
- Introductory knowledge of pandas for data analysis  
- General understanding of how generative AI produces text outputs  

---

### Instructions

1. Open the starter notebook for this exercise in your workspace.

2. Load the provided dataset containing simulated prompt–output pairs for e-commerce product descriptions across multiple product scenarios.

3. Review the baseline prompts and outputs to understand the neutral behavior of the model. Pay attention to tone, claim strength, and any implicit assumptions in the generated text.

4. Analyze **prompt sensitivity** by comparing baseline outputs to outputs generated from prompts with a single small change, such as:
   - Tone (for example, neutral vs luxury)
   - Target audience (general audience vs kids or students)
   - Claim strength or constraints (for example, avoiding medical claims)

5. Perform **counterfactual comparisons** using paired prompts that differ by one controlled change only. Compare the resulting outputs and describe which behaviors were triggered by that change.

6. Conduct quantitative analysis on the generated text using Python and pandas. For example:
   - Count or flag prohibited or high-risk claims (guarantees, medical claims, “cures,” unsupported regulatory language)
   - Track exaggeration or certainty language (for example: “always,” “never,” “guaranteed,” “proven”)
   - Identify safety or compliance phrasing (for example: “safe for children,” “non-toxic,” “clinically tested”)
   - Optionally measure sentiment or hype intensity using a simple lexicon-based approach

7. Identify and document any **unexpected behaviors** that would require escalation before deployment, such as:
   - Hallucinated features or specifications
   - Unsafe or misleading advice
   - Inconsistent or contradictory safety language
   - Violations of stated constraints or brand voice

8. Summarize your findings directly in the notebook by creating an **explainability evidence table** that links prompt changes to observed behavioral shifts and highlights potential deployment risks.

---

### Deliverable

**Deliverable:** A completed Jupyter Notebook that interprets a simulated set of generative AI outputs, applies prompt sensitivity and counterfactual analysis, quantifies behavioral signals using Python and pandas, and presents clear, evidence-based documentation of model behavior, inconsistencies, and deployment risks.