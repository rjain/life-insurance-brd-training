# ChatGPT Prompts

Use these prompts during the live exercise.

## 1. Opening prompt

```text
Use the uploaded short BRD demo template.

We only have 20 minutes, so run a time-boxed BRD elicitation for this feature:

Feature: Stale Quote / Illustration Warning

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

## 2. Generate the clean mini-BRD

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

## 3. Create reusable BRD Assistant instructions

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

## 4. Tighten unclear answers

Use this if ChatGPT accepts vague stakeholder input too quickly.

```text
Before drafting, challenge vague or ambiguous answers in this section. Ask the next three most important clarifying questions only.
```

## 5. Separate assumptions from facts

Use this if the draft sounds too certain.

```text
Review the BRD and separate confirmed facts from assumptions. Mark each assumption as Assumed or To Confirm, and add unresolved items to the Open Questions section.
```
