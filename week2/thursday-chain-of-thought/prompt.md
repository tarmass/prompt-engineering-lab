# Thursday - Chain-of-Thought & Decomposition
**Date:** 2026-05-14
**Task:** Write the same complex task three ways (direct, CoT, decomposed pipeline) and compare

## The Task
Build a marketing bot for market research and outreach for a freight brokerage

---

## Prompt V1 - Direct Ask

> Build a marketing bot for market research and outreach

---

## Prompt V2 - With Explicit CoT Instruction

> I own a freight brokerage company and need help with marketing. Explain your thought process on what you think is the best solution and approach for this goal.

---

## Prompt V3 - Decomposed Pipeline

**Context:**
> I am a freight brokerage owner of Elite Freight Brokerage and have been struggling to win contracts. I'm looking to work with shippers on the East Coast and specialize in flat beds, dry vans and reefers. I need to build out my marketing.

**Prompt 1:** Based on the information I shared above, research and identify marketing tactics to win shipper contracts for my freight brokerage targeting shippers on the east coast looking to move freight with dry vans, reefers or flatbeds. Focus on tactics that work for small brokerages competing against larger operations.

**Prompt 2:** Use the research from step 1 and analyze what's the best plan to execute this.

**Prompt 3:** Using the best approach plan from step 2, build out a marketing campaign and create a report on how it will be executed.

**Prompt 4:** Use the report from step 3 to identify what tasks you can handle autonomously and what needs me in the loop.

**Prompt 5:** Build out the campaign execution and ask me if you need any clarification.

**Prompt 6 (QA/Verification):** Once built, run through the workflow and ensure the following scenarios work:
1. Emails are being sent from noreply@test.com to the external users and actually getting sent and not failing
2. If there is a reply, you are able to notify me automatically so that I can reach out to them — their contact info needs to get captured somewhere
3. How are we tracking the metrics: contacted companies, those that replied, those who need to be followed up with
4. When to escalate the matter to a human or send an automatic response because you have the information
