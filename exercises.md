# Daily Prompt Engineering Exercises (15-20 min)

## Monday — Constraint Engineering
Take any task (summarize an article, write code, analyze data) and write the prompt 3 times:
1. Naive version (how most people would ask)
2. Constrained version (add format, length, tone, edge case handling)
3. Adversarial version (make it robust against ambiguous/tricky inputs)

Compare outputs. Log what broke and what fixed it.

## Tuesday — System Prompt Architecture
Pick a real product (customer support bot, code reviewer, data analyst) and write a full system prompt from scratch. Include:
- Role definition
- Behavioral boundaries
- Output format spec
- Edge case handling
- Examples (few-shot)

Then stress-test it with 3 inputs designed to break it.

## Wednesday — Evaluation & Debugging
Take a prompt you wrote earlier in the week. Run the same prompt 5 times. Score outputs 1-5 on:
- Accuracy
- Consistency
- Format compliance
- Hallucination rate

Identify the failure mode and fix the prompt. One iteration cycle.

## Thursday — Chain-of-Thought & Decomposition
Pick a complex reasoning task (math word problem, legal analysis, multi-step code generation). Write it three ways:
1. Direct ask
2. With explicit CoT instruction
3. Decomposed into sub-prompts (pipeline)

Measure which approach gives the best result and why.

**Follow-up:** Take the winning version (likely decomposed). Redo ONLY the QA step with a tighter prompt — give the model concrete test scenarios, acceptance criteria, and specific workflows to trace through click-by-click. Compare the QA output quality before and after. The lesson: a decomposed pipeline is only as strong as its weakest prompt.

## Friday — Portfolio Piece
Build one complete, polished prompt system you could show in an interview. Rotate weekly:
- Week 1: Multi-turn agent prompt
- Week 2: RAG retrieval + generation prompt
- Week 3: Evaluation rubric for LLM outputs
- Week 4: Tool-use orchestration prompt

Save to your prompt-engineering-lab repo.

## Saturday/Sunday — Optional Review
Review the week's work. Refine your best piece. Push to GitHub.

---

## Tracking
Commit daily to `prompt-engineering-lab` repo:
- The prompt(s) you wrote
- Sample outputs
- What you learned (2-3 sentences)

## What top firms screen for
- Making models reliably follow complex instructions
- Debugging when outputs go wrong
- Understanding failure modes (hallucination, sycophancy, instruction drift)
- Designing evaluation criteria
- Building multi-step systems, not just one-shot prompts
