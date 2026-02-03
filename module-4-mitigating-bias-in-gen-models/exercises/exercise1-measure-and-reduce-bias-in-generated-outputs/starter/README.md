## Exercise: Measure and Reduce Bias in Generated Outputs

### Overview

In this exercise, you will evaluate and mitigate bias in **promotion-readiness narratives** produced by a simulated generative AI system. You will analyze a provided set of example outputs to identify biased language patterns, apply post-generation mitigation techniques, and assess whether those strategies improve consistency and fairness in how employees are described.

This exercise focuses on **bias in language framing**, not predictions or scores.

### Prerequisites

- Basic familiarity with Python
- Experience working in Jupyter Notebooks
- Introductory knowledge of pandas for data analysis
- General understanding of how generative AI produces text outputs

### Instructions

1. Open the starter notebook for this exercise in your workspace.

2. Load the provided dataset that contains simulated promotion-readiness narratives generated across multiple employee scenarios.

3. Review the scenarios and outputs to understand the context. Look for places where language framing differs across otherwise similar performance patterns.

4. Perform quantitative analysis on the generated text using Python and pandas. For example:
   - Count or flag confidence language (for example: “clearly ready,” “high potential,” “promising”)
   - Track hedging/uncertainty language (for example: “may,” “might,” “could”)
   - Summarize signals in a simple table so you can compare scenarios side-by-side

5. Apply mitigation strategies that are appropriate for generative AI outputs, such as:
   - Post-processing rules (rewrite or remove specific phrasing)
   - Language normalization (standardize tone and strength of recommendations)
   - Output filtering (remove biased or inconsistent phrasing patterns)

6. Re-analyze the mitigated outputs using the same measures you used in step 4, and compare results against the baseline.

7. Document your findings directly in the notebook, including:
   - Which bias signals were reduced (and by how much)
   - Which mitigation strategies helped the most
   - Any remaining issues or limitations

### Deliverable

**Deliverable:** A completed Jupyter Notebook that audits a provided set of promotion-readiness narratives, quantifies bias signals in language, applies post-generation mitigation techniques, and presents before-and-after evidence showing that language framing became more consistent and less biased.

