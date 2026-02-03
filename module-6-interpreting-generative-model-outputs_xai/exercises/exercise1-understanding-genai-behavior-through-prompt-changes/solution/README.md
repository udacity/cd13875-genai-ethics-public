# Accessing the Workspace

Follow these steps to access the exercise solution notebook.

1. Access the workspace from the cloud resources tab.
2. In the file explorer on the left, navigate to the exercise solution directory provided for this lesson.
3. Double-click the `solution.ipynb` file to open it and review the solution.
4. Optionally, you can also view the notebook in the associated GitHub repository if a link is provided.

**Important:** When you are done, click **End Lab** to avoid using unnecessary compute resources.

---

## Overview of the Solution

This solution supports an **explainability (XAI) exercise for generative AI outputs** using a simulated offline evaluation log. The dataset contains **prompt-output pairs** for e-commerce product descriptions. There are no live model calls. Instead, the notebook mirrors how teams audit generative systems in practice by analyzing **captured outputs**, comparing **controlled prompt changes**, and producing **audit-ready evidence**.

The solution is organized into five parts:
1. Load the dataset from CSV
2. Establish a baseline per scenario
3. Prompt sensitivity comparisons (baseline vs sensitivity)
4. Counterfactual comparisons (A vs B, one controlled change)
5. Quantitative signal analysis + manual review + explainability evidence table

---

## Load Provided Dataset

The notebook begins by loading the simulated prompt-output dataset from a CSV file into a pandas dataframe. The dataset includes columns like:

- `scenario_id`
- `product`
- `prompt_type` (baseline, sensitivity, counterfactual_a, counterfactual_b)
- `prompt`
- `output`

This is important because the entire exercise is based on **offline audit evidence** rather than real-time inference.

---

## Establish Baseline Behavior

Next, the notebook filters the dataset to the `baseline` rows and displays:

- the neutral prompt for each scenario
- the corresponding baseline output

This establishes what “normal” behavior looks like for each product scenario before introducing any prompt changes. Students use this baseline to detect drift in tone, claim strength, and safety language across later comparisons.

---

## Prompt Sensitivity Analysis

The solution then performs a prompt sensitivity comparison by pairing:

- `baseline` output for a scenario
- `sensitivity` output for the same scenario

These sensitivity prompts introduce a small change such as tone, audience, or constraints (for example, luxury tone or “safe for kids”).

The notebook merges the baseline and sensitivity rows by `scenario_id` and displays them together so learners can directly observe:

- what changed in the output
- what stayed consistent
- whether the small prompt change introduced new risks

This step supports behavior-based explainability: interpreting *how* the system shifts when prompts vary naturally in production.

---

## Counterfactual Comparisons

The counterfactual section compares `counterfactual_a` vs `counterfactual_b` for each scenario.

These pairs differ by **one controlled change only**, such as:

- “avoid guarantees” vs “make strong claims”
- “do not invent specs” vs “include impressive specs”

The notebook merges A and B by `scenario_id` and displays them side by side. This allows students to describe the causal effect of a single prompt change, which is a core technique for GenAI-focused XAI.

---

## Quantitative Signal Analysis

To support consistent evaluation (and reduce reliance on subjective impressions), the notebook quantifies simple text-based signals using Python and pandas.

The solution tracks two key measures:

- **High-risk claim language** (for example, guarantees, clinical claims, FDA language, “cures”)
- **Certainty / exaggeration language** (for example, “always,” “never,” “proven”)

These are calculated per row and summarized using group-by tables so students can compare signal levels across:

- baseline vs sensitivity
- counterfactual A vs counterfactual B

This keeps the evaluation grounded in repeatable evidence rather than anecdotal examples.

---

## Identifying Unexpected Behaviors

The notebook includes a dedicated step for identifying behaviors that would require escalation before deployment, such as:

- Hallucinated features or specifications
- Unsafe or misleading claims
- Inconsistent safety language
- Constraint-following failures

In the solution, students are expected to review outputs directly and document findings in plain language. This manual inspection complements quantitative metrics by catching risks that lexicon counts cannot reliably detect.

---

## Explainability Evidence Table

The final section produces an **explainability evidence table** that ties together:

- the prompt change (baseline → sensitivity, or A → B)
- measurable deltas (changes in high-risk and certainty counts)
- student-written interpretation fields (for example, observed behavior and deployment risk)

This table is the primary artifact for the exercise because it resembles what teams capture during launch readiness reviews:

- what changed
- what the model did
- why it matters
- what should happen next (review, escalation, guardrails, or release decision)

---

## Key Takeaways

By the end of this solution, learners should understand:

- How to interpret GenAI systems using **behavior-based explainability**
- Why **baseline outputs** matter for stability and consistency checks
- How prompt sensitivity reveals how outputs drift under small variations
- How counterfactual pairs demonstrate cause-and-effect relationships in outputs
- How to support manual findings with lightweight quantitative measures
- How to produce an **audit-ready explainability evidence table** suitable for deployment decision-making

This notebook serves as both a worked solution and a reusable template for auditing generative AI outputs in real-world product settings.
