# Wednesday - Evaluation & Debugging
**Date:** 2026-05-13
**Task:** Evaluate all prompt exercises from Week 1 and Week 2 Tuesday, identify what worked and what broke

## Method
Submitted all 5 exercises (5/5 through 5/12) for evaluation. Assessed each prompt against the exercise criteria and real-world effectiveness.

---

## Evaluation Results

### Week 1 Tuesday (5/5) - System Prompt Architecture: Customer Support Bot
**Grade: Functional but surface-level**
- Covers all 5 required layers (role, boundaries, output, edge cases, examples)
- Weakness: format constraints are vague ("short, sweet and straightforward" doesn't constrain anything)
- Weakness: no negative examples showing what NOT to produce
- Few-shot examples are single-exchange only — no multi-turn demonstration
- Missing: stress-test results (exercise required 3 adversarial inputs)

### Week 1 Thursday (5/7) - Chain-of-Thought & Decomposition: CRM Build
**Grade: Missed the exercise target**
- The exercise called for a *reasoning* task (math, logic, analysis) — not a generation task
- CRM build is a code generation task where CoT doesn't differentiate clearly
- V2 isn't actually CoT — it's a more detailed prompt, not "think step by step" scaffolding
- V3 is a solid decomposed pipeline but better described as phased instructions than a prompt pipeline
- The comparison (which method won, failure modes) was not documented
- Takeaway: strong decomposition instincts, but the technique comparison wasn't testable with this task

### Week 1 Friday (5/8) - Portfolio Piece: Multi-Turn Project Agent
**Grade: Good foundation, thin on multi-turn specifics**
- Role definition is clear and practical
- Output format spec is concrete (main statement + bullet details)
- The "3 potential segues" rule for unknowns is a smart pattern
- Weakness: no handling for contradictions between turns (e.g., user changes requirements mid-conversation)
- Weakness: no memory/context strategy for long conversations
- Weakness: only 1 few-shot example (exercise required at least 2 showing conversation flow)
- Missing: the 3-turn test conversation and logged results

### Week 1 Monday (5/11) - Constraint Engineering: User Stories from Meeting Minutes
**Grade: Strongest exercise — clear progression across all 3 versions**
- V1 to V2 to V3 shows real constraint layering
- Traffic light system (green/yellow/red) for confidence flagging is production-grade
- Gherkin format + concrete example anchors output better than description alone
- "If unsure, ask, do not guess" directly addresses the most dangerous failure mode (silent hallucination)
- The multi-condition "and" instruction shows Gherkin-specific edge case awareness
- Improvement: add sequential numbering (US-001...) and a summary risk table

### Week 2 Tuesday (5/12) - System Prompt Architecture: Deluxe Logistics Bot
**Grade: Major improvement over Week 1 Tuesday**
- Domain-specific role (psychology, rental agreements, fees, escalation) vs generic "friendly agent"
- Concrete escalation threshold (3 abusive messages) vs vague "suggest connecting to human"
- Edge cases are scenario-specific with exact response templates
- Output format has real constraints (numbered steps, resource links, closing question)
- Weakness: still no negative examples
- Weakness: examples show the pattern but don't demonstrate the numbered-step format the spec requires

---

## Cross-Exercise Patterns

### What improved over the week
1. **Specificity** — Week 1 Tuesday was generic ("friendly and supportive"). Week 2 Tuesday names the domain, the product, the escalation rules.
2. **Edge case thinking** — evolved from "ask for clarification" to scenario-specific templates (emergency, therapy, confidential info)
3. **Format discipline** — moved from vague ("short and sweet") to structural ("numbered steps, links, closing question")

### Recurring gaps
1. **No negative examples in any exercise** — showing "don't respond like this" dramatically reduces failure modes
2. **Few-shot examples are too thin** — single exchanges instead of multi-turn flows
3. **Missing stress-test documentation** — exercises ask for adversarial testing but results aren't logged
4. **CoT exercise needs a redo** — use a reasoning task (multi-step math, bug diagnosis, legal analysis) to see the real difference between direct/CoT/decomposed approaches

### Most costly gap across all exercises
Not logging the stress-test results. The prompts themselves are the easy part — knowing where they *break* is where the real learning happens. Every exercise should end with "I tried to break it, here's what happened, here's what I'd fix."
