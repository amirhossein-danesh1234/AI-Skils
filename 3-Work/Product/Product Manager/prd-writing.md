# PRD Writing

Context: [Product Manager](README.md).

## Purpose

Produce an implementation-ready product requirements document with traceable decisions.

## Activate When

An accepted feature or product increment needs a shared specification for design, engineering, and QA.

## Do Not Use When

Do not use a PRD to manufacture evidence, approve unresolved policies, or replace technical design.

## Required Context

**Needed:** Accepted problem/feature intent, current behavior, and sources of approved policy.

**Can be deferred or bounded:** Unknowns may remain with owners and affected slices; detailed design and exact estimates belong to specialists.

## Workflow

1. Inspect existing specifications, current behavior, approved rules, and stakeholder decisions; record contradictions.
2. Define goal, primary scenarios, scope, exclusions, and measurable outcomes before requirements.
3. Write uniquely identifiable requirements with actor, precondition, action, result, and relevant state or permission rules.
4. Trace requirements to acceptance criteria and design or engineering questions; separate decisions from assumptions.
5. Review edge behavior, rollout, support, data handling, dependencies, and unresolved owners before declaring readiness.

## PRD Contract and Readiness Gate

Use the following content contract; combine sections only when their meaning remains explicit.

- **Goal and problem:** primary user, triggering situation, current workaround, observed cost, evidence source, and desired change. Separate the business objective from the proposed feature.
- **Scenarios and scope:** entry conditions, actors, successful exit, supported variations, and explicit exclusions. Record why a smaller or non-software alternative is insufficient.
- **Requirements and rules:** stable identifiers; inputs and outputs; permissions; state transitions; limits; money, rounding, time, and retention rules where applicable. Link each rule to an approved source or an unresolved decision owner.
- **Failure and recovery:** empty and invalid data, duplicate submission, cancellation, timeout, partial completion, conflicting updates, unavailable dependencies, and return after interruption. Specify which effects persist and what users can safely retry.
- **Quality constraints:** measurable user-facing performance, accessibility, security, reliability, and compatibility expectations where relevant. Do not invent numeric targets; identify the owner who can set them.
- **Acceptance and measurement:** trace each requirement to observable acceptance and each desired outcome to a metric definition, baseline availability, observation window, and guardrails.
- **Delivery context:** dependencies, rollout assumptions, support needs, operational ownership, risks, open questions, and the decisions required before implementation or exposure.

Walk at least one normal scenario, one denied action, and one interrupted or repeated action from user intent through authoritative state and feedback. A polished document is not ready if implementation requires guessing policy. Mark independently ready slices separately from blocked slices; avoid blocking unrelated work for an optional detail.

## Readiness Is Slice-Specific

Use a requirement-to-scenario-to-acceptance crosswalk to detect orphaned requirements and uncovered scenarios. Distinguish discovery-ready, design-ready, implementation-ready, and release-ready rather than stamping the entire document approved. Walk a permission change during an in-flight action when access or money is involved.

## Decision Rules

- If a rule affects money, permissions, data retention, or legal obligations, require an explicit owner decision.
- If the team is small and scope narrow, use a compact PRD but retain states, acceptance, and open decisions.

## Output Contract

PRD covering goal, evidence, users, scenarios, scope, rules, states, errors, requirements, acceptance, measurement, risks, and open decisions.

## Quality Gates

- Can QA derive tests and engineering identify contracts without guessing product behavior?
- Does each requirement support an in-scope scenario and each acceptance criterion trace to a requirement?
- An implementer can identify the exact ready slice without guessing any consequential rule.

## Failure Modes

- Long prose hides ambiguity: use explicit rules and identifiers.
- PRD claims readiness with unowned blockers: separate ready scope from unresolved scope.

## Handoffs

UX Designer validates flows; engineering checks feasibility; Security and Financial Analyst join only for material exposure; QA tests the specification.
