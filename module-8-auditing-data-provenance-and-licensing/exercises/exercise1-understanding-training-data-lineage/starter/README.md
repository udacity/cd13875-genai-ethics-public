## Exercise: Conduct a Data Provenance and Licensing Review (Offline)

### Overview

In this exercise, you will perform a structured **data provenance and licensing audit** using a synthetic news dataset and its accompanying metadata. You will analyze dataset documentation, assess whether the licensing terms are suitable for **generative AI training** (news summarization), identify gaps or risks, and produce a clear audit record using Python.

This exercise focuses on **data eligibility and governance readiness**, not model performance.

---

### Prerequisites

- Basic familiarity with Python  
- Experience working in Jupyter Notebooks  
- Introductory knowledge of pandas for data inspection and tabular reporting  
- General understanding of provenance, ownership, and licensing concepts in the context of generative AI systems  

---

### Dataset

You are provided with:

- `news_articles.csv`  
  - Article text  
  - Source fields  

- `dataset_metadata.json`  
  - Provenance information  
  - Ownership details  
  - License and usage notes  

---

### Instructions

1. Open the starter notebook for this exercise in your workspace.

2. Load the dataset and metadata files into your notebook:
   - Read `news_articles.csv` into a pandas DataFrame.
   - Load and parse `dataset_metadata.json` into a Python dictionary.

3. Review the dataset’s stated purpose:
   - Examine metadata fields describing why the dataset exists.
   - Document how the dataset would be used in a generative AI pipeline (for example, training or fine-tuning a model for news summarization).

4. Inspect dataset-level provenance and licensing metadata. At minimum, extract:
   - Source origin  
   - Collection method  
   - Ownership  
   - License type  
   - Intended usage  

5. Evaluate whether the stated license clearly permits use for generative AI training and derivative outputs:
   - Training or fine-tuning generative models  
   - Creation of derivative outputs such as summaries or paraphrases  
   - Internal or commercial use, if relevant  

6. Identify provenance and licensing risks, including but not limited to:
   - Vague or missing source attribution  
   - Ambiguous license language  
   - Conflicts between intended use and license terms  
   - Missing documentation required for auditability  

7. Use Python to construct a **data provenance audit table** that flags:
   - License clarity (clear / unclear / restricted)  
   - Provenance completeness (complete / partial / insufficient)  
   - Suitability for generative AI training (yes / conditional / no)  
   - Key risks and supporting notes  

8. Document any remediation steps required before using the dataset, such as:
   - Source verification  
   - Re-licensing or permission clarification  
   - Dataset filtering or exclusion  
   - Metadata enrichment  

9. Write a short audit conclusion recommending whether the dataset should be:
   - Approved  
   - Conditionally approved  
   - Rejected for generative AI training  

   Support your recommendation with evidence from the audit.

---

### Deliverable

**Deliverable:**  
A completed Jupyter Notebook that performs a structured data provenance and licensing audit using Python, includes an audit table summarizing license clarity and risk indicators, and provides a documented recommendation on whether the dataset can be safely used for generative AI training.
