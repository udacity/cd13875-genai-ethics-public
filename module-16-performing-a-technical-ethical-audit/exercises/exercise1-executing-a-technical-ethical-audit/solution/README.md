## Accessing the Workspace

Follow these steps to access the exercise solution notebook.

1. Access the workspace from the cloud resources tab.
2. In the file explorer on the left, navigate to the exercise solution directory provided for this lesson.
3. Double-click the `solution.ipynb` file to open it and review the solution.
4. Optionally, you can also view the notebook in the associated GitHub repository if a link is provided.

**Important:** When you are done, click **End Lab** to avoid using unnecessary compute resources.

---

## Overview of the Solution

This solution supports a **technical ethical audit exercise** focused on evaluating a simulated generative AI system operating in a **regulated banking environment**.

The notebook follows an evaluation-first workflow designed to produce a **reproducible audit record**. Rather than relying on subjective impressions, the solution emphasizes **structured logging, measurable risk signals, robustness testing across prompt variants, and an audit summary suitable for compliance or risk review**.

The solution is organized into four main parts:

1. Prompt suite ingestion and audit logging  
2. Banking-specific risk signal computation  
3. Robustness analysis across prompt variants  
4. Qualitative review and structured audit summary  

---

## Prompt Suite and Audit Trace Logging

The first part of the notebook sets up the audit scope and creates a complete, reviewable audit trail.

The solution:

- Loads an expanded **banking audit prompt suite** containing:
  - baseline prompts  
  - edge cases  
  - stress and ambiguity tests  
- Includes **two prompt variants per intent**, using:
  - `variant_group_id` to group prompts that test the same intent
  - `variant_id` (`v1`, `v2`) to distinguish the variants
- Loads a variant-specific simulated outputs file where each variant has a corresponding output.

All prompts, outputs, and metadata are merged into a single structured pandas table (the audit log). This table is treated as the primary artifact for the rest of the notebook and mirrors the type of record that would be required in a real internal audit.

---

## Banking-Specific Ethical Risk Signals

The next section computes quantitative risk signals tailored to banking. These signals are designed to detect behavior that is especially sensitive in regulated financial workflows.

The solution computes flags for:

- **Sensitive financial data exposure**
  - account numbers or routing identifiers
  - card number patterns
  - authentication secrets (passwords, PINs, OTPs)
  - balance disclosure or dollar-amount leakage
- **PII exposure**
  - Social Security number references
  - date of birth, government ID references
- **Fair lending risk indicators**
  - protected-class references (used as a signal that the response is drifting into unsafe territory)
- **Regulatory overreach**
  - claims framed as “required by law” or similar definitive legal assertions
- **Guarantee language**
  - promises or implied guarantees of approval or outcomes
- **Escalation cues**
  - whether the response signals human review pathways in high-risk scenarios

The output is a scored audit table that includes the original prompt/response plus derived risk columns. This transforms banking-specific ethical expectations into **measurable indicators** that can be compared across categories and prompt variants.

---

## Robustness Testing Across Prompt Variants

A core part of the solution is the robustness check.

Because each intent includes two prompt variants, the notebook evaluates whether the simulated model behaves consistently when the prompt wording changes.

The solution:

- Groups records by `variant_group_id`
- Compares the two variant outputs using a lightweight **Jaccard similarity** measure
- Produces a robustness summary table that can be inspected alongside risk signals

This step reinforces that in regulated systems, risk is not only “what the model says,” but also **how stable the behavior is under small changes in input**. Inconsistencies across variants can indicate brittleness, policy gaps, or unclear guardrails.

---

## Qualitative Review (Human Judgment Layer)

After computing quantitative signals, the notebook includes a qualitative review section to capture issues that metrics may not fully reflect.

The solution creates a small review sample that prioritizes:

- high-risk flagged outputs (for example, sensitive data exposure or guarantee language)
- stress-test scenarios (complaints, unfair treatment claims, pressure prompts)
- a minimum representation across categories

For each sampled row, the notebook records:

- `review_notes`: what is unclear, unsupported, or risky  
- `needs_escalation`: whether a human review should be triggered, and why  
- `what_should_change`: recommended response behavior or guardrails  

This mirrors real-world audit practice: quantitative detection narrows the surface area, but a reviewer still documents judgment and recommended controls.

---

## Structured Audit Summary

The final section compiles a structured audit summary suitable for compliance or risk review. The solution:

- Lists tested scenarios and coverage (by category and intent)
- Summarizes observed risks using rates and counts from the scored audit table
- Includes robustness observations (similarity scores per variant group)
- Assigns a confidence level based on test coverage and consistency
- Provides recommended follow-up actions, such as:
  - hard guardrails for sensitive data and PII
  - prohibition of guarantee language for loan outcomes
  - escalation workflows for complaints and fair lending concerns
  - tighter constraints around regulatory/legal claims
  - expanding the prompt suite to deepen robustness testing

The summary is designed to be readable and actionable, connecting evidence to next steps.

---

## Key Takeaways

By the end of this solution, learners should understand:

- How to produce a **reproducible audit record** for a regulated banking GenAI system
- How to translate banking-specific expectations (PII, account data, guarantees, fairness) into **measurable risk signals**
- Why robustness testing across prompt variants is essential for regulated use cases
- How to combine quantitative signals with qualitative review to form an audit-ready narrative
- How to write an audit summary that supports real governance decisions, not just analysis

This notebook serves as both a worked solution and a template for conducting technical ethical audits of generative AI behavior in regulated financial environments.
