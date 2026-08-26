# Threat Modeling

Context: [Security Engineer](README.md).

## Purpose

Identify credible abuse paths and controls around a defined system and its trust boundaries.

## Activate When

A new design, sensitive feature, or architectural change alters security exposure.

## Do Not Use When

Do not substitute a generic threat list for system understanding or claim this replaces penetration testing.

## Required Context

**Needed:** Actual system scope, valuable assets, actors, flows, and trust boundaries.

**Can be deferred or bounded:** Likelihood can be qualitative with rationale; invented numerical probabilities are not needed.

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

## Control Challenge

For a material threat, construct the shortest plausible abuse sequence and identify the exact step each control interrupts. Test control outage, alternate entry, and excessive privilege. For AI features, include retrieved/tool content crossing into action selection and request AI Engineer’s concrete pipeline evidence.

## Decision Rules

- If an attack requires an impossible precondition, lower or reject it with evidence rather than copying a category.
- If impact is severe and uncertainty material, investigate or contain exposure before accepting the design.

## Output Contract

Threat model with asset/actor/boundary map, abuse scenarios, likelihood, impact, mitigations, residual risk, and tests.

## Quality Gates

- Does every important trust boundary have relevant abuse analysis?
- Can each mitigation be tested and is remaining risk assigned to an actual owner?
- Every prioritized threat has a feasible verification and a named residual-risk decision owner.

## Failure Modes

- Framework categories become threats: write concrete attack paths.
- Mitigation list without evidence: specify how each control interrupts the path.

## Handoffs

Architect validates flows; Backend and DevOps implement controls; Database Engineer checks integrity; QA derives abuse tests.
