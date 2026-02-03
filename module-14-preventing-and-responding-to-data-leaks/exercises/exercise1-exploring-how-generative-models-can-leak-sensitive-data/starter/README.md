## Exercise: Detect and Mitigate Data Leakage Risks in GenAI Outputs

### Overview

In this exercise, you will evaluate and mitigate **data leakage risks** in simulated generative AI outputs. You will analyze a provided set of example model responses designed to mimic real-world leakage scenarios, identify privacy risk signals, apply lightweight defenses using Python, and design a structured incident response protocol for handling potential data exposure events.

This exercise focuses on **privacy and information exposure in generated text**, not model accuracy.

### Prerequisites

- Basic familiarity with Python  
- Experience working in Jupyter Notebooks  
- Introductory knowledge of pandas for data analysis  
- Basic understanding of regular expressions (regex)  
- General understanding of how generative AI systems can unintentionally reveal sensitive information  

### Instructions

1. Open the starter notebook for this exercise in your workspace.

2. Load the provided dataset containing **simulated generative AI outputs** that may include potential leakage signals.

3. Review a sample of the outputs to understand the scenarios and context. Look for potential leakage indicators such as:
   - Personal data (names, email addresses, phone numbers)
   - Dates of birth or other highly identifying dates
   - Account numbers, employee IDs, ticket IDs, order IDs, or similar identifiers
   - Internal system references (hostnames, private URLs, internal code names)
   - Credentials or secret-like strings (API keys, tokens, passwords)

4. Establish a baseline leakage assessment by building a simple detection pass over the outputs using Python. For example:
   - Use regex patterns to flag common sensitive formats
   - Count the number of matches per output
   - Create a summary table showing which outputs contain potential leakage and what types were detected

5. Document your baseline findings in the notebook, including:
   - Which outputs appear risky and why
   - Which leakage categories occur most frequently
   - Any false positives or ambiguous patterns you observe

6. Apply lightweight privacy defenses to reduce leakage risk:
   - **Output filtering and redaction:** Implement rule-based post-processing to remove or mask detected sensitive patterns

7. Re-evaluate the same outputs after defenses are applied:
   - Re-run pattern scans on the mitigated outputs
   - Compare before-and-after counts and flags
   - Summarize changes in leakage risk

8. Assess defense effectiveness and document results:
   - Which defenses were effective
   - Which were partially effective
   - Which were ineffective
   - Any tradeoffs, such as reduced readability or over-redaction

9. Design a structured incident response protocol for generative AI data leakage that includes:
   - Detection and escalation criteria
   - Containment steps
   - Notification and documentation procedures
   - Post-incident review and remediation actions

10. Conclude with a concise, security-focused write-up summarizing:
    - Technical controls applied (scanning, filtering, redaction, prompt constraints)
    - Procedural safeguards designed (incident response workflow and escalation paths)

### Deliverable

**Deliverable:** A completed Jupyter Notebook that audits simulated generative AI outputs for data leakage signals, applies lightweight privacy and filtering defenses, demonstrates before-and-after risk reduction, and documents a clear, structured incident response protocol for handling potential data exposure events.