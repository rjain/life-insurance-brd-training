# 20-Minute BRD Demo Template

> **SHORT WORKING TEMPLATE - for live ChatGPT demonstration**
>
> Use this version when the goal is to demonstrate interactive BRD construction in a short training session. It keeps only the sections that show the most value from an AI-assisted requirements conversation.

---

## Demo setup

**Feature:** Stale Illustration Warning

**Scenario:** Agents can save and reuse product illustrations. The enhancement warns agents when a saved illustration may be stale because rates, product rules, state availability, required disclosures, or illustration assumptions changed since the illustration was last calculated.

**Live sections to elicit:**

1. Problem / Opportunity Statement
2. Scope
3. Current State vs. Proposed State
4. Business Rules
5. Acceptance Criteria

**ID conventions:**

- `BR-001` = Business Requirement
- `FR-001` = Functional Requirement
- `RULE-001` = Business Rule
- `AC-001` = Acceptance Criterion
- `A-001` = Assumption
- `Q-001` = Open Question

**Opening prompt for ChatGPT:**

```text
Use this short BRD demo template.

We only have 20 minutes, so run a time-boxed BRD elicitation for this feature:

Feature: Stale Illustration Warning

Concept:
Agents can save and reuse product illustrations. We want the system to warn agents when a saved illustration may be stale because rates, product rules, state availability, required disclosures, or illustration assumptions changed since the illustration was last calculated.

Do not complete the whole BRD interactively. Interview me only for:
1. Problem / Opportunity Statement
2. Scope
3. Current State vs. Proposed State
4. Business Rules
5. Acceptance Criteria

Ask one section at a time. Ask concise questions. Push back on vague answers. Maintain assumptions and open questions.

After those sections are complete, generate the rest of the BRD using reasonable draft assumptions, clearly marked as Assumed or To Confirm.
```

---

## 1. Problem / Opportunity Statement

> **Guidance -** State the problem in business terms. Do not name the solution yet. Explain who is affected and what risk or friction exists today.

> **Elicit -** "State the problem without naming the solution." "Who feels the pain?" "What happens today when this goes wrong?" "If we did nothing, what is the worst realistic outcome?"

> **Example -** An agent can unknowingly present a saved illustration whose figures may no longer be valid because a rate, product rule, disclosure, or regulation changed after it was saved.

_[Your problem statement here]_

**Assumptions / open questions surfaced**

| ID | Type | Item | Owner | Status |
|---|---|---|---|---|
| A-001 | Assumption |  |  | To Confirm |
| Q-001 | Open Question |  |  | Open |

---

## 2. Scope

> **Guidance -** Draw the MVP boundary. Explicitly name what is in and out so the exercise does not become a larger transformation initiative.

> **Elicit -** "What is the smallest version that still delivers the goal?" "What might people assume is included but should be out of scope?" "Does this apply to every product, user type, and channel?"

**In scope**

- _[item]_

**Out of scope**

- _[item]_

> **Example -** In scope: agent-facing warning when opening or attempting to use a saved illustration. Out of scope: rebuilding the recalculation engine, customer-facing notifications, quote collaboration, and redesigning the full illustration workflow.

---

## 3. Current State vs. Proposed State

> **Guidance -** Make the behavior change clear. The proposed state should change only what needs to change.

> **Elicit -** "Describe the current behavior step by step." "At which exact step does the new behavior appear?" "What stays the same?"

| Aspect | Current State | Proposed State |
|---|---|---|
| Saved illustration reuse |  |  |
| Validity check |  |  |
| Agent action |  |  |
| Business control |  |  |

> **Example -** Current: saved illustration opens and can be used without a validity check. Proposed: on open or attempted use, the system checks defined staleness triggers and requires recalculation if stale.

---

## 4. Business Rules

> **Guidance -** Define the decision logic. This is the best section for showing ChatGPT push for precision.

> **Elicit -** "What exactly makes an illustration stale?" "Which changes should trigger a warning?" "Which changes should not trigger a warning?" "Who owns these rules?"

| ID | Rule | Owner |
|---|---|---|
| RULE-001 |  |  |
| RULE-002 |  |  |
| RULE-003 |  |  |

> **Example -** RULE-001: An illustration is stale if any of the following changed after its last calculation: rate table, product version or pricing, rider availability or pricing, state availability, required disclosure package, or applicable illustration regulation.

---

## 5. Acceptance Criteria

> **Guidance -** Make the requirements testable. Use Given / When / Then where possible.

> **Elicit -** "What test would prove this works?" "What would cause the business to reject delivery?" "What edge case must be included in the demo?"

| ID | Acceptance Criterion | Verifies |
|---|---|---|
| AC-001 | Given ..., when ..., then ... | RULE-001 / FR-001 |
| AC-002 |  |  |
| AC-003 |  |  |

> **Example -** AC-001: Given a saved illustration created before a rate change, when the agent opens it, then it is shown as stale and cannot be presented or submitted until recalculated.

---

## 6. Generate the Rest With Assumptions

Use this prompt after the five live sections are complete:

```text
Now generate a clean mini-BRD from the sections we completed.

Include:
- Executive Summary
- Business Context
- Problem / Opportunity Statement
- Goals
- Scope
- Stakeholders and Actors
- Current State vs. Proposed State
- Business Requirements
- Functional Requirements
- Business Rules
- Data / Integration Notes
- Security, Compliance, and Audit Notes
- Assumptions
- Risks
- Acceptance Criteria
- Open Questions

For content we did not discuss, create reasonable draft content and label uncertain items as Assumed, To Confirm, or Open Question.

Remove all instructional annotations, examples, and placeholder text.
Use IDs BR-001, FR-001, RULE-001, AC-001, A-001, R-001, and Q-001.
```

---

## 7. Convert to Reusable Assistant Instructions

Use this prompt at the end of the demo:

```text
Based on the process we just followed, create reusable instructions for a BRD Assistant.

The assistant should:
- Use an uploaded BRD template
- Interview the user section by section
- Focus first on problem, scope, current/proposed state, business rules, and acceptance criteria
- Push back on vague answers
- Maintain assumptions, risks, and open questions
- Generate a clean BRD after elicitation
- Mark unconfirmed content clearly
```
