LLM Prompt Optimization Experiment:

Author: Michael Tamirat
Task: Structured Data Extraction from Unstructured Text
LLM Used: google/flan-t5-large (Free, HuggingFace)

This project explores how different prompt engineering techniques impact the performance of a free, open-source large language model.
The task focuses on extracting structured data (product name, price, purchase date) from a messy, real-world text review.
Five prompts were tested:
Baseline Prompt
Technique 1 — Role Prompting
Technique 2 — Output Formatting Constraints
Technique 3 — Chain-of-Thought + Date Normalization
Final Combined Optimized Prompt

Summary Table of Prompt Performance:

| Prompt Version                            | Description                                                        | Accuracy Score (1–10) | Observation                                                                |
| ------------------------------------- | ------------------------------------------------------------------ | ----------------- | -------------------------------------------------------------------------- |
| Baseline                              | Minimal instruction: “Extract the data.”                           | 3/10              | Extracts some info but incomplete, unstructured, and unclear date.         |
| Technique 1: Role Prompting           | Model instructed to act as a Senior Data Analyst.                  | 6/10              | Better extraction accuracy, but still unstructured and date ambiguous.     |
| Technique 2: Formatting Constraint    | Forces strict JSON output.                                         | 7/10              | Structure improves dramatically, but date still not normalized.            |
| Technique 3: CoT + Date Normalization | Model asked to think step-by-step and convert dates.               | 9/10              | Highly accurate fields, normalized date, but includes reasoning in output. |
| Final Optimized Prompt                | Combines role, formatting, and reasoning (without exposing steps). | 10/10             | Clean JSON, accurate fields, normalized date, no unnecessary text.         |


Key Lesson Learned:
This experiment clearly shows that LLMs don’t just need a prompt—they need the right prompt.
Small changes to the wording or structure of a prompt can dramatically change the output.
Here are the core takeaways:
Role prompting improves accuracy by giving the model context about how it should behave.
Strict formatting instructions are essential for tasks requiring structured output like JSON.
Reasoning guidance (Chain-of-Thought) helps the model handle complex logic such as date normalization.
Combining techniques produces the strongest results, even when using free, lightweight models.
Overall, the experiment highlights that prompt engineering is not optional—it’s a key skill for getting reliable, high-quality results from LLMs.
