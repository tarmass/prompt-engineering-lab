# Prompt Eng Daily (Day 2/30): Chain-of-Thought (CoT) for Root Cause Analysis

**Today's Concept:** Chain-of-Thought (CoT) Prompting. Instead of asking an AI for a direct answer, you instruct it to "think step by step." This forces the model to break down a complex problem into a sequence of logical, intermediate steps, drastically improving the accuracy and reasoning of the final conclusion. It’s like showing your work in math class.

**Your Exercise:**

Your goal is to draft a CoT prompt that diagnoses a common business problem in freight brokerage: declining net revenue per load. You will instruct the AI to act as a seasoned logistics analyst and use a step-by-step reasoning process to identify the most likely causes.

**The Scenario:**

A small freight brokerage has provided the following data for the last quarter:
*   Gross revenue is up 15%.
*   Total number of loads booked is up 20%.
*   However, **net revenue per load has dropped by 10%**.
*   Carrier costs have increased by 5%.
*   The brokerage has recently started working with three new, large shippers in the CPG (Consumer Packaged Goods) sector.

**Your Task:**

Write a single, complete prompt that instructs the AI to use Chain-of-Thought reasoning to find the root cause of the declining profit margin.

Your prompt must:
1.  Clearly define the AI's role (e.g., "You are a logistics business analyst...").
2.  Present the complete scenario and data provided above.
3.  Explicitly instruct the model to use a step-by-step deduction process (e.g., "Use a chain-of-thought process to analyze this situation," or "Let's think step by step...").
4.  Direct the AI to conclude its analysis with the **three most likely root causes**, ranked from most to least probable.
