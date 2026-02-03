## Accessing the Workspace

Follow these steps to access the exercise solution notebook.

1. Access the workspace from the cloud resources tab.
2. In the file explorer on the left, navigate to the exercise solution directory provided for this lesson.
3. Double-click the `solution.ipynb` file to open it and review the solution.
4. Optionally, you can also view the notebook in the associated GitHub repository if a link is provided.

**Important:** When you are done, click **End Lab** to avoid using unnecessary compute resources.

---

## Overview of the Solution

This solution supports an **efficiency, cost, and environmental impact optimization exercise** focused on evaluating a simulated generative AI inference system.

Instead of tuning a real model, the notebook uses **provided baseline metrics** and a **simulated optimized scenario** to mirror how teams evaluate GenAI deployments in production. The emphasis is on turning system measurements into a decision, supported by quantitative evidence and clearly stated assumptions.

The solution is organized into four parts:
1. Workload context and assumptions
2. Baseline metrics loading and interpretation
3. Before-and-after comparison with scale impact estimates
4. Tradeoff evaluation and recommendation

---

## Workload Context and Assumptions

The notebook begins by defining a workload context dictionary that establishes the operating conditions for the analysis.

The solution captures assumptions such as:
- workload type (for example, an interactive customer support assistant)
- traffic pattern (steady vs bursty)
- request volume per day
- average input and output length (token sizes)
- latency expectations or SLA guidance

A CO2e conversion factor is also included to demonstrate how teams may translate energy use into an environmental estimate when needed.

This section ensures you understand that efficiency results are only meaningful when tied to a clear deployment scenario. The same system metrics may be acceptable or unacceptable depending on scale and latency sensitivity.

---

## Loading Baseline Inference Metrics

Next, the notebook loads `baseline_inference_metrics.csv` and displays it for review.

The baseline dataset contains simulated measurements commonly tracked in GenAI production systems, including:
- p50 and p95 latency
- throughput
- memory usage
- estimated cost per 1k requests
- estimated energy per 1k requests

This step establishes the reference point for the rest of the notebook. All later findings depend on having a consistent baseline that represents pre-optimization behavior.

---

## Baseline Interpretation and Efficiency Concerns

After loading the baseline metrics, the solution converts the baseline table into a dictionary for easier lookups.

The notebook then generates a concise set of baseline findings using simple rule-based checks to surface likely efficiency concerns, such as:
- whether p95 latency aligns with an interactive workload
- whether memory usage suggests expensive infrastructure choices
- how cost per 1k requests compounds at daily scale
- whether energy per 1k requests is meaningful at deployment scale

This mirrors how teams interpret metrics during design and performance reviews.

---

## Optimization Scenario Definition

The next section introduces a simulated optimization scenario representing common GenAI inference techniques, such as:
- reduced-precision inference (for example, quantization)
- batching or dynamic batching

The scenario includes explanatory notes and a short quality-impact statement. This reflects real-world practice where performance gains must be evaluated alongside potential risks to output quality or system flexibility.

---

## Before-and-After Metric Comparison

The solution constructs a side-by-side comparison table by:
- defining optimized metrics using the same metric names as the baseline
- merging baseline and optimized values into a single DataFrame
- computing absolute differences and percentage changes

This table provides clear, quantitative evidence of where the optimization improves performance and where tradeoffs occur.

---

## Cost and Energy Impact at Scale

Using workload assumptions, the notebook scales per-1k metrics to daily impact.

The solution estimates:
- baseline and optimized daily cost
- daily cost savings
- baseline and optimized daily energy usage
- daily energy savings

For CO2e conversion factor, the notebook also estimates the corresponding environmental impact reduction.

This step demonstrates how small per-request improvements can produce significant operational and sustainability benefits at scale.

---

## Tradeoff Evaluation

The notebook summarizes optimization tradeoffs in a structured table, addressing:
- latency changes (including median and tail behavior)
- throughput improvements
- memory footprint reductions
- potential output quality impacts

This reinforces that optimization decisions require balancing multiple dimensions, not maximizing a single metric.

---

## Decision and Recommendation

The final section produces a clear recommendation, such as:
- adopt
- adopt with guardrails
- do not adopt

The recommendation is supported by measured results and includes suggested safeguards like staged rollout, monitoring, and quality regression checks.

This models how production teams document and justify GenAI optimization decisions.

---

## Key Takeaways

By the end of this solution, you should understand:
- how to interpret GenAI inference metrics in context
- why workload assumptions are essential for cost and energy analysis
- how to quantify optimization impact with before-and-after comparisons
- how to reason about performance, cost, quality, and sustainability tradeoffs
- how to communicate an evidence-based optimization decision

This notebook serves as both a worked solution and a reusable template for evaluating efficiency improvements in cloud-scale generative AI systems.
