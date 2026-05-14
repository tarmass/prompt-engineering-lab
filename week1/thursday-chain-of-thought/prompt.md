# Thursday - Chain-of-Thought & Decomposition
**Date:** 2026-05-07
**Task:** Write the same complex task three ways (direct, CoT, decomposed pipeline) and compare

## The Task
Build a CRM for a logistics company (freight broker perspective)

---

## Prompt V1 - Direct Ask

> Can you build me a CRM so that my employees can use it to track their leads and customers

---

## Prompt V2 - With Explicit CoT Instruction

> Build me a CRM from a freight broker perspective. Identify the job duties of a freight broker and build the system which incorporates those responsibilities. Work through the challenges of this user and implement features that will help them do their job better.

---

## Prompt V3 - Decomposed Pipeline

> Build a CRM with the following features:
> 1. User accounts management
> 2. Admin portal
> 3. Lead generation and tracking
> 4. Customer communications
> 5. Messaging feature
> 6. Enterprise grade security to protect sensitive information
>
> Once completed, review the entire system from the user perspective and ensure everything works properly with a logical flow between steps.
>
> Analyze the system as a QA and flag any bugs or improvements that can be made.
>
> Lastly perform regression testing for the entire system as different users and ensure all functionality works as expected.
>
> If you're not sure of anything, ask me before you make a decision.
>
> Make sure you research what the most up to date coding and security standards are and adhere to them.
