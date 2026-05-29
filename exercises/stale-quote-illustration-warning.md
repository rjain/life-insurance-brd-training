# Exercise: Stale Quote / Illustration Warning

## Scenario

Agents can save and reuse product illustrations. A saved illustration may become stale if rates, product rules, rider availability, state availability, required disclosures, or regulatory rules changed after it was last calculated.

The proposed enhancement warns agents when a saved quote or illustration may be stale and prevents use until it is recalculated or otherwise resolved.

## Why this is a good BRD exercise

- It is small enough for a 20-minute live demo.
- It is specific to life insurance and agent workflows.
- It has real requirements depth: trigger logic, business rules, compliance, audit trail, and acceptance criteria.
- It lets ChatGPT demonstrate interactive elicitation instead of one-shot document generation.

## Suggested stakeholder inputs

Use these if you are asked to role-play the business SME.

| BRD Area | Suggested Input |
|---|---|
| Problem | Agents may unknowingly reuse saved illustrations after rates, rules, disclosures, or availability changed. |
| Scope | Agent-facing stale warning only; no customer-facing changes in MVP. |
| Current State | Saved illustrations can be reopened and reused without a clear point-of-use stale check. |
| Proposed State | When the agent opens or attempts to use a saved illustration, the system checks staleness triggers and requires recalculation if stale. |
| Business Rule | If any defined source-of-truth value changed after last calculation, the illustration is stale. |
| Acceptance | A stale illustration cannot be presented, e-signed, or submitted until recalculated. |

## In scope for the demo

- Agent-facing warning
- Saved quote or illustration staleness check
- Business rules for stale conditions
- Assumptions and open questions
- Acceptance criteria

## Out of scope for the demo

- Rebuilding the illustration or recalculation engine
- Customer-facing notifications
- Quote collaboration or reassignment
- Full eApp redesign
- Product/rate configuration redesign

## Key terms

**Quote:** A simpler, general term for an estimate or sales figure.

**Illustration:** The more precise life-insurance term for a formal projection of policy values, premiums, benefits, assumptions, riders, and disclosures.

**Stale:** Potentially no longer valid because an underlying source-of-truth value changed after the quote or illustration was last calculated.
