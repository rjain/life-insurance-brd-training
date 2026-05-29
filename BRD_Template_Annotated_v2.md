# Business Requirements Document (BRD)

> **WORKING TEMPLATE - for IT enhancement requests**
>
> This annotated template is designed to be filled through an interactive elicitation conversation with an AI assistant such as ChatGPT. The annotations guide the conversation. They should not appear in the final BRD.

---

## How to use this template

This template has two jobs:

1. **Working / facilitation template:** use this file during the ChatGPT conversation. Keep the Guidance, Elicit, and Example notes visible so the assistant can interview the business stakeholder section by section.
2. **Final / deliverable BRD:** after elicitation, ask ChatGPT to produce a clean BRD using the same structure, with all annotations, prompts, examples, and placeholder text removed.

Recommended workflow for each section:

1. Read the **Guidance** note to understand what the section is for.
2. Use the **Elicit** prompt to have ChatGPT interview the stakeholder.
3. Capture confirmed answers in the fill-in area.
4. Log assumptions and open questions immediately.
5. After the BRD is complete, generate a clean version for review.

Annotation legend:

> **Guidance -** what this section is for and how to tell when it is complete.

> **Elicit -** questions to drive the interactive conversation. The goal is for the AI to interrogate the business SME until the section is unambiguous.

> **Example -** illustrative content from the worked example: an agent-facing Stale Quote / Illustration Warning enhancement.

**Golden rule:** A BRD describes what the business needs and why. It should not over-specify how the solution will be built. If a sentence specifies a technology, screen layout, API, or implementation design, move it to a later design document unless it is truly a business constraint.

**ID conventions used in this template:**

- `BR-001` = Business Requirement
- `FR-001` = Functional Requirement
- `RULE-001` = Business Rule
- `NFR-001` = Non-Functional Requirement
- `AC-001` = Acceptance Criterion
- `A-001` = Assumption
- `D-001` = Dependency
- `R-001` = Risk
- `Q-001` = Open Question

**Clean BRD generation prompt:**

```text
Now generate the final clean BRD using this template structure.
Remove all Guidance, Elicit, Example, and placeholder text.
Keep only completed business content.
Label uncertain content as Assumed, To Confirm, or Open Question.
Use the agreed ID conventions for requirements, rules, assumptions, risks, and acceptance criteria.
```

---

## 1. Document Control

| Field | Value |
|---|---|
| Document title | _e.g., BRD - Stale Quote / Illustration Warning_ |
| Initiative / project ID |  |
| Author(s) |  |
| Business owner / sponsor |  |
| Version | _0.1 draft_ |
| Status | _Draft / In Review / Approved_ |
| Date created |  |
| Last updated |  |

**Approvals**

| Name | Role | Decision | Date |
|---|---|---|---|
|  | Business sponsor |  |  |
|  | Product / domain SME |  |  |
|  | IT / delivery lead |  |  |
|  | Compliance / risk, if applicable |  |  |

**Change log**

| Version | Date | Author | Summary of change |
|---|---|---|---|
| 0.1 |  |  | Initial draft |

> **Guidance -** Keep this current. Reviewers use the version and change log to know what they are approving. The approvals table lists people who must sign off, not everyone who should be informed.

---

## 2. Executive Summary

> **Guidance -** Three to five sentences a busy executive can read in under a minute: what the enhancement is, the problem it solves, and the expected benefit. Write this last, after the rest is settled.

> **Elicit -** "Summarize this BRD in four sentences for a sponsor who has thirty seconds." "What is the single most important sentence here, and why?"

> **Example -** Agents can save and reuse illustrations, but the system does not warn them when an underlying rate, product rule, or regulatory requirement has changed since the illustration was created. This enhancement detects when a saved illustration may be out of date and requires recalculation before it is used with a client.

_[Your summary here]_

---

## 3. Business Context & Background

> **Guidance -** Set the scene for someone unfamiliar with the area. What process or system does this touch? What exists today? Why is this coming up now? Establish the current state before describing any problem.

> **Elicit -** "What system or process does this enhancement sit inside, and what does that process do today end to end?" "Who uses it today and how often?" "What changed recently that makes this worth doing now?" "What is already in place that we must not break or duplicate?"

> **Example -** Agents build product illustrations in the existing illustration workflow and can save them for later use. Illustrations depend on inputs that change over time, such as rates, product rules, disclosure requirements, and state availability.

_[Your context here]_

---

## 4. Problem / Opportunity Statement

> **Guidance -** State the problem in business terms and quantify impact if possible. Avoid solution language. "The problem is we do not have feature X" is usually a solution in disguise.

> **Elicit -** "State the problem without naming any solution." "Who feels this pain, how often, and what does it cost them or us?" "What happens today when this goes wrong?" "If we did nothing, what is the worst realistic outcome?"

> **Example -** An agent can unknowingly present a saved illustration whose figures may no longer be valid because a rate, product rule, disclosure, or regulation changed after it was saved. This creates compliance and client-trust risk.

_[Your problem statement here]_

---

## 5. Goals & Success Metrics

> **Guidance -** Define measurable success. Distinguish business outcomes from output metrics. If baseline data is not available, mark it as To Confirm rather than inventing it.

> **Elicit -** "For each goal, how will we measure it?" "What is the baseline?" "Which metric matters most?" "What metric would tell us this enhancement backfired?"

| ID | Goal | Metric | Baseline | Target |
|---|---|---|---|---|
| G-001 |  |  |  |  |
| G-002 |  |  |  |  |

> **Example -** G-001: Reduce risk of stale illustrations being presented. Metric: count of stale illustrations presented or submitted. Baseline: To Confirm. Target: zero stale illustrations reach presentation/submission.

_[Your goals here]_

---

## 6. Scope

> **Guidance -** Draw the boundary explicitly. The Out of Scope list prevents scope creep and is as important as In Scope.

> **Elicit -** "List everything a reader might assume is included, then decide which items are in or out." "Does this apply to every product, channel, and user type?" "What is the smallest version that still delivers the goal?" "What is deliberately deferred?"

**In scope**

- _[item]_

**Out of scope**

- _[item]_

> **Example -** In scope: detecting and flagging staleness when a saved illustration is opened or used by an agent. Out of scope: rebuilding the recalculation engine, customer-facing notifications, quote collaboration, and redesigning the full illustration workflow.

_[Your scope here]_

---

## 7. Stakeholders & Actors

> **Guidance -** Stakeholders have an interest in the outcome. Actors interact with the feature or flow. Separating these makes requirements cleaner.

> **Elicit -** "Who must approve this, who should be consulted, and who just needs to be informed?" "List every human or system actor that touches this flow." "Is there a role that should be involved but currently is not?"

| Stakeholder / Actor | Type | Interest or Role in Flow |
|---|---|---|
|  | Stakeholder / Actor |  |

> **Example -** Agent: actor who opens saved illustration and responds to warning. Illustration system: actor that evaluates staleness. Compliance: stakeholder that owns rules for compliant illustration use.

_[Your stakeholders and actors here]_

---

## 8. Current State vs. Proposed State

> **Guidance -** Make the delta unmistakable. This is especially important when enhancing an existing capability.

> **Elicit -** "Describe current behavior step by step, then proposed behavior step by step." "At exactly which step does the behavior change?" "What stays the same?"

| Aspect | Current State | Proposed State |
|---|---|---|
|  |  |  |

> **Example -** Reuse of saved illustration - Current: opens and can be used without a current-validity check. Proposed: on open or attempted use, the system checks defined staleness triggers and requires recalculation when stale.

_[Your current vs. proposed state here]_

---

## 9. Business Requirements

> **Guidance -** The core "what the business needs," written as numbered, testable statements with rationale and priority.

> **Elicit -** "Turn each agreed need into a single 'The solution must...' statement." "For each requirement, why does the business need it?" "Is it Must, Should, or Could?" "Is any requirement actually two requirements combined?"

| ID | Requirement: "The solution must..." | Rationale | Priority |
|---|---|---|---|
| BR-001 |  |  | Must / Should / Could |
| BR-002 |  |  | Must / Should / Could |

> **Example -** BR-001: The solution must determine whether a saved illustration remains valid against current rates, product rules, disclosures, state availability, and applicable regulation when an agent opens or attempts to use it.

_[Your business requirements here]_

---

## 10. Functional Requirements

> **Guidance -** Specific system behaviors that satisfy the business requirements. Functional requirements describe what the system does in response to events, not how it is coded.

> **Elicit -** "For each business requirement, what exactly must the system do?" "On what trigger?" "What does the user see?" "What happens in the unhappy path?"

| ID | Functional Requirement | Traces To | Priority |
|---|---|---|---|
| FR-001 |  | BR-001 | Must / Should / Could |
| FR-002 |  | BR-001 | Must / Should / Could |

> **Example -** FR-001: On open or attempted use of a saved illustration, the system evaluates defined staleness triggers and sets the illustration status to Valid, Stale, or Unable to Determine.

_[Your functional requirements here]_

---

## 11. Business Rules

> **Guidance -** Business rules are decision logic and policies independent of a particular screen or implementation. This is where trigger conditions and definitions belong.

> **Elicit -** "Enumerate every condition that should change the outcome." "Define each term precisely." "Are there conditions that look like they should trigger the rule but explicitly should not?" "Who owns each rule?"

| ID | Rule | Owner |
|---|---|---|
| RULE-001 |  |  |
| RULE-002 |  |  |

> **Example -** RULE-001: An illustration is stale if any of the following changed after its last calculation: rate table, product version or pricing, rider availability or pricing, state availability, required disclosure package, or applicable illustration regulation.

_[Your business rules here]_

---

## 12. Non-Functional Requirements

> **Guidance -** Qualities and constraints such as performance, availability, security, compliance, auditability, usability, accessibility, and monitoring. Make them measurable where possible.

> **Elicit -** "How fast must this respond?" "What must be logged, and for how long?" "What regulatory or security constraints apply?" "What accessibility standard must this meet?"

| ID | Category | Requirement |
|---|---|---|
| NFR-001 | Performance |  |
| NFR-002 | Auditability |  |
| NFR-003 | Compliance |  |

> **Example -** NFR-002: Every staleness determination and user action is logged with timestamp, illustration ID, user ID, trigger reason, and resulting action, retained per records policy.

_[Your non-functional requirements here]_

---

## 13. Use Cases & Scenarios

> **Guidance -** Concrete walkthroughs, including edge cases. Edge cases often become business rules.

> **Elicit -** "Walk me through the normal path." "Now break it: what if the change happens mid-flow?" "What should happen when two rules conflict?" "What is the weirdest legitimate situation a user could hit?"

**Scenario ID:** _[SCN-001]_

- Name:
- Actor:
- Preconditions:
- Steps:
- Expected result:

> **Example -** SCN-001: A rate change occurs after an illustration is saved. When the agent opens it, the system marks it stale and requires recalculation before presentation or submission.

_[Your scenarios here]_

---

## 14. Data Requirements

> **Guidance -** State what data the feature must read, record, or expose, the source of truth, and any sensitivity or retention needs. Do not design the database schema here.

> **Elicit -** "What data does the system need to make the decision?" "Where is the authoritative source?" "What new data is created?" "Who can see it?" "Any sensitive or regulated data?"

| Data Element | Source of Truth | New or Existing | Notes |
|---|---|---|---|
|  |  |  |  |

> **Example -** Current rate table, product version, disclosure version, and saved illustration calculation timestamp are required to determine staleness.

_[Your data requirements here]_

---

## 15. Integrations & System Touchpoints

> **Guidance -** Identify systems this feature reads from, writes to, or depends on. Note the direction and business trigger of each interaction.

> **Elicit -** "Which systems hold the data or perform the work this depends on?" "Who owns each system?" "Are those systems in scope to change?" "What happens if one is unavailable?"

| System | Interaction | Dependency Notes |
|---|---|---|
|  | Read / Write / Trigger |  |

> **Example -** Product/rate configuration system: read source-of-truth change dates. Recalculation engine: trigger recalculation when stale. Illustration workflow: display status and enforce usage restriction.

_[Your integrations here]_

---

## 16. Assumptions, Constraints & Dependencies

> **Guidance -** Assumptions are believed true but not confirmed. Constraints are fixed limits. Dependencies are things this work needs from elsewhere.

> **Elicit -** "What are we taking for granted?" "Which assumption is riskiest?" "What hard limits are fixed?" "What must be delivered by someone else first?"

**Assumptions**

| ID | Assumption | Validation Owner | Status |
|---|---|---|---|
| A-001 |  |  | To Confirm |

**Constraints**

- _[constraint]_

**Dependencies**

| ID | Dependency | Owner | Needed By |
|---|---|---|---|
| D-001 |  |  |  |

> **Example -** A-001: A recalculation capability already exists and can be invoked at the point of use. D-001: Product/rate configuration must expose reliable change metadata.

_[Your assumptions, constraints, and dependencies here]_

---

## 17. Risks & Mitigations

> **Guidance -** Include business, compliance, adoption, operational, and delivery risks.

> **Elicit -** "What could make this fail even if built correctly?" "What is the worst realistic compliance or business risk?" "Where might users work around the feature?"

| ID | Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|---|
| R-001 |  | Low / Medium / High | Low / Medium / High |  |

> **Example -** R-001: Over-flagging illustrations could train agents to ignore warnings. Mitigation: define precise staleness triggers and monitor false-positive rates.

_[Your risks here]_

---

## 18. Acceptance Criteria

> **Guidance -** Acceptance criteria define what must be demonstrably true for the business to accept delivery. Use Given / When / Then where helpful.

> **Elicit -** "For each must-have requirement, what test proves it is satisfied?" "What demo makes the sponsor say yes?" "What would cause us to reject delivery?"

| ID | Acceptance Criterion | Verifies |
|---|---|---|
| AC-001 | Given ..., when ..., then ... | BR-001 / FR-001 |
| AC-002 |  |  |

> **Example -** AC-001: Given a saved illustration created before a rate change, when the agent opens it, then it is shown as stale and cannot be presented or submitted until recalculated.

_[Your acceptance criteria here]_

---

## 19. Open Questions / Decision Log

> **Guidance -** This is one of the most valuable sections during elicitation. Every unanswered item should be logged with an owner. Resolved items should capture the decision and date.

> **Elicit -** "List everything in this conversation I could not answer definitively." "What did we decide?" "What alternatives did we reject?" "Who needs to resolve each open item?"

| ID | Type | Question / Decision | Raised By | Owner | Status | Resolution |
|---|---|---|---|---|---|---|
| Q-001 | Open Question |  |  |  | Open |  |

> **Example -** Q-001: Does stale handling apply identically to in-force and new-business illustrations? Owner: Product SME. Status: Open.

_[Your open questions and decisions here]_

---

## 20. Glossary

> **Guidance -** Define domain terms and acronyms so every reader interprets the BRD consistently.

| Term | Definition |
|---|---|
|  |  |

> **Example -** Stale illustration: a saved illustration whose figures may no longer be valid because an underlying rate, product rule, disclosure requirement, state availability rule, or regulation changed after its last calculation.

_[Your glossary here]_

---

## Appendix

> **Guidance -** Supporting material: process diagrams, screenshots of current state, regulatory references, links to related BRDs or design docs. Keep the main body lean and park detail here.

_[Attachments / references here]_
