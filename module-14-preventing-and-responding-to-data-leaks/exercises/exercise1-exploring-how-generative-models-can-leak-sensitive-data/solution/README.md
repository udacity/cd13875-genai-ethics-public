## Accessing the Workspace

Follow these steps to access the exercise solution notebook.

1. Access the workspace from the cloud resources tab.
2. In the file explorer on the left, navigate to the exercise solution directory provided for this lesson.
3. Double-click the `solution.ipynb` file to open it and review the solution.
4. Optionally, you can also view the notebook in the associated GitHub repository if a link is provided.

**Important:** When you are done, click **End Lab** to avoid using unnecessary compute resources.

---

## Overview of the Solution

This solution supports a **data leakage detection and mitigation exercise** focused on identifying privacy and security risks in simulated generative AI outputs.

The notebook follows a structured, evaluation-first workflow that mirrors how real-world AI teams detect, assess, and respond to unintended information exposure in production systems. The emphasis is on **systematic detection, evidence-based comparison, and operational response**, rather than ad-hoc inspection of individual outputs.

The solution is organized into four main parts:

1. Baseline leakage detection and measurement  
2. Output-level inspection and aggregation  
3. Lightweight privacy mitigation and re-evaluation  
4. Incident response protocol design  

---

## Baseline Leakage Detection

The first part of the notebook establishes a baseline leakage assessment by analyzing simulated generative AI outputs for common exposure signals.

The solution:

- Loads a JSONL dataset containing model-generated text responses.
- Defines a set of regex-based detectors for sensitive patterns, including:
  - Email addresses
  - Identifiers (employee IDs, case IDs, order IDs)
  - Dates and account-like numbers
  - Internal URLs and hostnames
  - Credential- or secret-like strings
- Applies these detectors to each output and expands the results into structured columns using Pandas.

This step intentionally treats leakage detection as a **mechanical, repeatable process**. The goal is to convert ambiguous text risk into **quantifiable signals** that can be tracked, compared, and audited.

---

## Row-Level Inspection

After computing baseline leakage metrics, the notebook provides a small row-level preview of results.

This allows you to:

- Validate that detection patterns are firing as expected
- Inspect which specific outputs contain leakage signals
- Connect numeric counts back to concrete text examples

This inspection step is not used to draw conclusions on its own. It exists to support interpretability and debugging before moving to summary analysis.

---

## Leakage Aggregation and Risk Summary

The next section aggregates leakage signals across outputs.

Using simple summaries, the solution:

- Identifies which outputs exceed a configurable risk threshold
- Counts how often each leakage category appears
- Produces a compact table suitable for audit review or reporting

This reinforces an important security principle: **risk is identified through patterns, not isolated examples**. Repeated exposure of certain signal types often points to systemic weaknesses in prompts, data sources, or guardrails.

---

## Lightweight Privacy Mitigation

The notebook then introduces lightweight mitigation strategies appropriate for deployed generative AI systems.

The solution demonstrates:

- **Simulated prompt constraints** that explicitly prohibit sensitive disclosures
- **Rule-based output filtering and redaction**, replacing detected patterns with standardized placeholders

These defenses are intentionally simple and transparent. No model retraining is performed. This mirrors real-world scenarios where teams must reduce risk quickly using post-generation controls.

---

## Re-Evaluation After Mitigation

After mitigation is applied, the notebook reruns the **exact same detection pipeline** on the redacted outputs.

This enables direct before-and-after comparison of:

- Total leakage signals
- Per-category leakage counts
- Which outputs still contain residual risk

By holding the evaluation method constant, learners can clearly see which defenses were effective, partially effective, or ineffective.

---

## Incident Response Protocol Design

Beyond technical mitigation, the final section of the notebook shifts to **operational readiness**.

The solution defines a structured incident response protocol that includes:

- Detection and escalation criteria, with severity tiers
- Immediate containment actions for confirmed leakage
- Notification and documentation requirements
- Post-incident review and remediation steps

This section emphasizes that generative AI safety is not only a modeling problem, but also a **governance and operations problem**.

---

## Key Takeaways

By the end of this solution, learners should understand:

- How data leakage can manifest in generative AI outputs
- How to design repeatable, evidence-based leakage detection
- The strengths and limitations of lightweight post-processing defenses
- Why incident response planning is essential for production GenAI systems

This notebook serves both as a worked solution and as a reusable template for auditing, mitigating, and responding to data leakage risks in real-world generative AI deployments.