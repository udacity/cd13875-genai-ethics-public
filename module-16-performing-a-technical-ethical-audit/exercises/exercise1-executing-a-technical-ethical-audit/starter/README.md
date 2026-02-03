## Exercise: Perform a Technical Ethical Audit for a Regulated GenAI System

### Overview

In this exercise, you will perform a structured technical ethical audit of a simulated generative AI system used in a regulated domain (banking). You will use Python to log prompt–response behavior, compute ethical risk signals, compare robustness across prompt variants, and produce a reproducible audit record that could be reviewed by compliance or risk teams.

This exercise focuses on **auditability, risk signal detection, and robustness**, not model training.

### Prerequisites

- Basic familiarity with Python  
- Experience working in Jupyter Notebooks  
- Introductory knowledge of pandas for data analysis  
- General understanding of how generative AI systems can fail in regulated contexts  

### Instructions

1. Open the starter notebook for this exercise in your workspace.

2. Review the exercise context to understand the audit scope and ethical expectations for a generative AI system operating in insurance or banking.

3. Load the provided audit prompt suite. Confirm it includes:
   - baseline prompts  
   - edge cases  
   - stress and ambiguity tests  

4. Review the simulated model outputs associated with each prompt. Pay attention to tone, specificity, and whether the system makes claims that would require evidence or human review.

5. Create structured logging tables in pandas to capture the full audit trace. At minimum, log:
   - prompt text  
   - prompt category (baseline, edge case, stress/ambiguity)  
   - scenario metadata (domain, intent, risk level, tags if provided)  
   - model output text  
   - prompt variant identifiers  

6. Compute quantitative ethical risk signals using Python. For example:
   - flag sensitive, exclusionary, or potentially discriminatory language  
   - detect overconfident language without supporting evidence  
   - identify inconsistent responses across near-identical prompt variants  
   - label failure modes triggered by edge cases  

7. Perform a qualitative review of a representative subset of outputs and document observations, including:
   - unclear or missing reasoning  
   - unsupported statements presented as fact  
   - outputs that should trigger human escalation  

8. Evaluate robustness by comparing outputs across prompt variants:
   - group prompts testing the same intent with small wording changes  
   - compare consistency, escalation behavior, and safety posture  
   - identify unpredictable or unjustified changes in behavior  

9. Document findings directly in the notebook using:
   - summary tables  
   - side-by-side or before-and-after examples  
   - narrative cells explaining the significance of observed risks  

10. Compile an audit summary section that includes:
    - tested scenarios  
    - observed risks  
    - confidence level  
    - recommended follow-up actions  

### Deliverable

**Deliverable:** A completed Jupyter Notebook that executes a simulated technical ethical audit, including logged prompt–response behavior, computed ethical risk signals, robustness observations, and a structured audit summary that serves as a reproducible technical audit record for a regulated generative AI system.
