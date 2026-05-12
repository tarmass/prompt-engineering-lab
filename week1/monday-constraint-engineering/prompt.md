# Monday - Constraint Engineering
**Date:** 2026-05-12
**Task:** Write the same prompt 3 times (naive, constrained, adversarial) and compare

## The Task
Extract business requirements from meeting minutes and create user stories.

---

## Prompt V1 - Naive

> Can you review the meeting minutes, find where the business owner shared requirements and draft user stories from it?

---

## Prompt V2 - Constrained

> Can you review the meeting minutes, find where the business owner shared requirements and draft user stories as follows:
> - Each requirement should be written in gherkin format, Given When Then.
> - The user stories should be documented in an excel sheet with the following columns: ID, Role, Description(gherkin), Acceptance Criteria
> - The requirements should be high level for the gherkin statements, and then should follow up with a list of Acceptance Criteria providing additional details that list out what requirements need to be met as part of that user story
> - The tone should be professional and easily understood by non-technical team members

---

## Prompt V3 - Adversarial

> You are a senior business analyst, I will share a copy of our requirements gathering meeting minutes with the client. I want you to extract important information and business requirements and create user stories that I can review and add to Azure Devops.
>
> Follow these guidelines:
> 1. Gherkin format
> 2. Tone = professional and concise
> 3. Description should be high level, acceptance criteria should have all details to test the user story with
> 4. If you are unsure, ask, do not guess. Make sure you flag user stories in 3 buckets, green, yellow, red. Green = user story is good, yellow = there are a few questions I have, red = i dont know what the requirements are.
> 5. If there are multiple conditions for the same requirement, take advantage of the "and" aspect of the gherkin format.
> 6. Here is what a user story should look like:
>    - Title: Add a Print button to the PDF viewer.
>    - Description: As an external user, I want to be able to print the pdf, so that I can have physical copies
>    - Details: Given: I am on the PDF viewer page, When: I click the 'Print' button, Then: I should be able to print the page
>    - Acceptance Criteria:
>      1. print button is visible and clickable at the top of the PDF viewer page
>      2. Print button opens modal to print a copy of the pdf
>      3. Print button opens modal to save a copy of the pdf to computer

---

## Analysis

### What broke in each version
- **V1:** No format constraints = model picks random structure. No guardrails on ambiguity = model silently invents requirements. No tone/audience guidance = inconsistent output.
- **V2:** Structure is locked down (Gherkin, Excel columns, tone). But no instruction for handling ambiguous or incomplete requirements — model fills gaps with confident nonsense.
- **V3:** Adds role assignment (senior BA), confidence bucketing (green/yellow/red), a concrete example, and "if unsure, ask" instruction. Catches the silent hallucination problem V2 missed.

### What constraints fixed the failures
- Gherkin format + Excel columns eliminated structural randomness
- "If unsure, ask, do not guess" + color bucketing stopped silent gap-filling
- Concrete example anchored output format better than description alone
- "And" instruction for multi-condition requirements addressed Gherkin edge cases

### Most costly instruction gap
The "don't guess" + confidence bucketing constraint. Without it, every version produces output that *looks* correct but may contain fabricated requirements — the most dangerous failure mode for a BA deliverable.

### Suggested improvements to V3
1. Add sequential numbering (US-001, US-002...) for clean Azure DevOps import
2. Add a summary table at the end (X green, Y yellow, Z red) for quick risk snapshot
