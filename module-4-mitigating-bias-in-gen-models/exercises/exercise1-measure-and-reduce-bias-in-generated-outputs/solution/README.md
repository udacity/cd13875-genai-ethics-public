## Accessing the Workspace

Follow these steps to access the exercise solution notebook.

1. Access the workspace from the cloud resources tab.
2. In the file explorer on the left, navigate to the exercise solution directory provided for this lesson.
3. Double-click the `solution.ipynb` file to open it and review the solution.
4. Optionally, you can also view the notebook in the associated GitHub repository if a link is provided.

**Important:** When you are done, click **End Lab** to avoid using unnecessary compute resources.

---

## Overview of the Solution

This solution supports a **bias evaluation and mitigation exercise** focused on analyzing how generative AI models describe employee performance or promotion readiness across different demographic groups.

The notebook walks through a structured, evaluation-first workflow that mirrors how bias is identified and addressed in real-world AI systems. The emphasis is on **measurement, comparison, and evidence**, rather than subjective inspection of individual outputs.

The solution is organized into three main parts:
1. Baseline bias analysis
2. Group level aggregation and comparison
3. Lightweight post processing mitigation and re-evaluation

---

## Baseline Bias Analysis

The first part of the notebook establishes baseline metrics by analyzing model generated text outputs.

The solution:
- Loads a dataset containing model outputs and an associated group attribute (for example, a demographic group label).
- Applies a text analysis function to each output to count linguistic signals such as:
  - Masculine-coded terms
  - Feminine-coded terms
  - Confidence-oriented language
  - Doubt or hedging language
- Expands these counts into structured columns using Pandas, creating a row-level view of bias signals.

This step is intentionally mechanical. The goal is to transform subjective language patterns into **quantifiable metrics** that can be evaluated consistently.

---

## Row-Level Inspection

After computing baseline metrics, the notebook provides a small row-level preview.

This allows you to:
- Sanity check the extracted features
- See how individual outputs differ in tone or framing
- Connect the numerical metrics back to real language examples

This preview is not used to draw conclusions on its own. It exists to support interpretability before moving to aggregate analysis.

---

## Group Level Bias Comparison

The next section aggregates the baseline metrics by group.

Using a group-by operation, the solution:
- Calculates the mean frequency of each linguistic signal per group
- Rounds results for readability
- Produces a compact summary table suitable for comparison

This step reinforces a core ethics principle: **bias is a pattern, not an anecdote**. Differences at the group level are what indicate systemic issues, not isolated examples.

The resulting table highlights whether certain groups consistently receive language that is more confident, more doubtful, or more gendered despite similar performance context.

---

## Simple Post-Processing Mitigation

The final part of the notebook introduces a lightweight mitigation strategy.

A reusable `mitigate()` function performs basic post-processing on the generated text by:
- Replacing explicitly gendered pronouns with neutral language
- Cleaning up spacing and formatting artifacts

This function is applied to the original outputs, and the same analysis pipeline is rerun on the mitigated text.

Importantly, no model retraining occurs. This mirrors real-world scenarios where teams may need to reduce harm in deployed systems without immediate access to training pipelines.

```python
def mitigate(text):
    t = str(text)  # start from the input text

    # neutralize obvious pronouns 
    t = re.sub(r"\b(he|him|his)\b", "they", t, flags=re.IGNORECASE)
    t = re.sub(r"\b(she|her|hers)\b", "they", t, flags=re.IGNORECASE)
    t = re.sub(r"\b(is)\b", "are", t, flags=re.IGNORECASE)

    # tidy spacing
    t = re.sub(r"\n{3,}", "\n\n", t).strip()
    return t
```


---

## Re-Evaluation After Mitigation

After mitigation, the notebook recomputes:
- Row level linguistic metrics
- Group level aggregate statistics

Learners can directly compare the before and after summaries to evaluate:
- Which bias signals were reduced
- Which patterns persisted
- The limitations of post-processing approaches

This reinforces that mitigation is rarely perfect and must be paired with ongoing evaluation and governance.

---

## Key Takeaways

By the end of this solution, learners should understand:
- How subtle bias manifests through language framing
- Why quantitative evaluation is essential for ethical AI
- How to design repeatable bias audits
- The role and limits of post-processing mitigation techniques

This notebook serves as both a worked solution and a template for conducting similar bias evaluations in production AI systems.
