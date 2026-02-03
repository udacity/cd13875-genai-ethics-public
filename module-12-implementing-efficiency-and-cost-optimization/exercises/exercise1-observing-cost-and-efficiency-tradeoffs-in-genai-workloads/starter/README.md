## Exercise: Optimize a GenAI System for Cost and Efficiency

### Overview
In this exercise, you will evaluate the performance, cost, and environmental impact of a simulated generative AI inference system. You will compare baseline and optimized system metrics to understand efficiency tradeoffs that commonly arise in cloud-scale GenAI deployments.

You will use provided simulated measurements to quantify changes in latency, throughput, memory usage, cost per request, and estimated energy impact. You will then assess whether the optimization is acceptable given the documented tradeoffs and any impact on output quality or system flexibility.

### Prerequisites
- Basic familiarity with Python  
- Experience working in Jupyter Notebooks  
- Introductory knowledge of pandas for data analysis  
- General understanding of generative AI inference concepts such as latency, throughput, and batching  

### Instructions
1. Open the starter notebook for this exercise in your workspace.
2. Review the workload context and usage assumptions provided in the notebook, including:
   - Number of requests per day
   - Average input and output length
   - Traffic assumptions (steady or bursty)
   - Any stated performance targets or constraints
3. Load the baseline inference metrics for the simulated generative AI workload. Examine metrics such as:
   - Latency
   - Throughput
   - Memory usage
   - Estimated cost
   - Estimated energy or environmental impact
4. Analyze the baseline metrics to identify potential efficiency concerns, such as:
   - High latency for an interactive workload
   - Insufficient throughput for expected traffic
   - Excessive memory usage driving higher infrastructure cost
   - High cost per request at scale
5. Review the simulated optimization scenario and its post-optimization metrics. The optimization may represent techniques such as:
   - Model quantization or reduced precision inference
   - Request batching
   - Architectural or configuration-level efficiency changes
6. Use Python and pandas to construct a comparison table that summarizes baseline and optimized metrics side by side, including:
   - Latency
   - Throughput
   - Memory usage
   - Estimated cost
   - Estimated energy impact
7. Calculate and summarize the differences between baseline and optimized metrics, noting:
   - Improvements or regressions in performance
   - Estimated cost savings
   - Estimated reductions in energy usage or environmental impact
8. Evaluate the tradeoffs introduced by the optimization. Consider:
   - Any documented impact on output quality
   - Changes in system responsiveness or flexibility
   - Whether the optimization is appropriate for the stated workload assumptions
9. Write a short analysis in the notebook explaining:
   - Which efficiency improvements matter most
   - Which tradeoffs are acceptable or concerning
   - Whether the optimization should be adopted for this scenario
10. Conclude with a clear recommendation supported by the data.

### Deliverable
**Deliverable:** A completed Jupyter Notebook that evaluates simulated efficiency and cost optimization techniques for a generative AI system, supported by before-and-after performance metrics, estimated cost and energy impact, and a clear, reasoned assessment of optimization tradeoffs.
