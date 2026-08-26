# Threat Modeling

## Purpose

Identify credible abuse paths and controls around a defined system and its trust boundaries.

## When to Use

A new design, sensitive feature, or architectural change alters security exposure.

## When Not to Use

Do not substitute a generic threat list for system understanding or claim this replaces penetration testing.

## Required Inputs

### Required

System scope, assets, actors, data flows, trust boundaries, existing controls, and risk owner.

### Helpful

Architecture and code, data classification, actors, trust boundaries, exposure, existing controls, and authorized test scope.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Threat model with asset/actor/boundary map, abuse scenarios, likelihood, impact, mitigations, residual risk, and tests.

## Operating Principles

Separate confirmed vulnerability from suspected weakness; prioritize reachable impact and never include usable secrets or unnecessary exploit detail in public artifacts.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect the actual system and identify valuable assets, attacker capabilities, and trusted assumptions.
2. Trace data and control flows across identity, tenant, network, and third-party boundaries.
3. Construct plausible abuse scenarios including preconditions, exploit path, consequence, and current controls.
4. Prioritize by reachable impact and likelihood; select prevention, detection, containment, or recovery measures.
5. Define verification and residual-risk acceptance, and update the model when architecture or exposure changes.

## Threat Record and Review Method

For each material scenario, record: asset and security property; actor and capability; entry point; trust boundary; prerequisites; action sequence; impact; existing controls; likelihood rationale; proposed mitigation; verification; residual risk; and accountable owner. Distinguish confidentiality, integrity, availability, and business abuse when their consequences differ.

Model more than anonymous outsiders when relevant: authenticated low-privilege users, compromised service identities, malicious tenants, administrators, suppliers, and accidental misuse can have different paths. Include external content and tool output as untrusted data when an AI-enabled feature consumes them; do not assume text retrieved from a document can authorize actions.

Use a framework such as STRIDE only as a prompt to examine the actual system. A category is not a threat until a plausible path and consequence are described. Rank likelihood from exposure and prerequisites, not invented percentages. Document uncertainty where evidence is incomplete.

For every mitigation, explain which step of the path it prevents, detects, limits, or repairs. Check whether a bypass exists through another endpoint, background job, export, administrative interface, or recovery path. A control that only changes the visible UI does not protect a server-side asset.

Review the model with implementation and operational owners, then assign tests and residual-risk decisions. Keep a version or trigger for updates when assets, identities, dependencies, or deployment exposure change. [OWASP’s threat-modeling guidance](https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html) provides a useful process reference; it is not a substitute for system-specific evidence.

## Decision Rules

- If an attack requires an impossible precondition, lower or reject it with evidence rather than copying a category.
- If impact is severe and uncertainty material, investigate or contain exposure before accepting the design.

## Validation

- Does every important trust boundary have relevant abuse analysis?
- Can each mitigation be tested and is remaining risk assigned to an actual owner?

## Common Failure Modes

- Framework categories become threats: write concrete attack paths.
- Mitigation list without evidence: specify how each control interrupts the path.

## Escalation and Collaboration

Architect validates flows; Backend and DevOps implement controls; Database Engineer checks integrity; QA derives abuse tests.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
