# Architecture Review

Context: [Software Architect](README.md).

## Purpose

Assess an existing or proposed architecture against its actual requirements and risks.

## Activate When

A design needs an independent structural critique or readiness decision.

## Do Not Use When

[Architecture-design.md](architecture-design.md) creates alternatives; code review checks local implementation.

## Required Context

**Needed:** Current/proposed structure, driving requirements, and evidence-bearing artifacts.

**Can be deferred or bounded:** Missing code or operational evidence limits review confidence; it does not make a design diagram proof of deployment behavior.

## Workflow

1. Reconstruct the system from authoritative artifacts and note differences from diagrams.
2. Trace critical requests, state changes, dependencies, and recovery paths.
3. Challenge assumptions about consistency, scale, security, and operational capacity.
4. Rank findings by impact and likelihood; recommend minimal structural corrections and residual-risk owners.

## Finding Threshold

For a finding, specify the quality scenario, reachable failure mechanism, consequence, and smallest correction. Separate a violated requirement from an untested assumption and an optional preference. Challenge both excessive complexity and insufficient controls; elegance is not a substitute for service evidence.

## Decision Rules

- If a claim lacks load or failure evidence, mark it unverified rather than automatically wrong.
- If a local fix solves the risk, avoid recommending wholesale redesign.

## Output Contract

Prioritized findings with evidence, violated scenario, consequence, alternatives, and acceptance or remediation conditions.

## Quality Gates

- Are findings reproducible or tied to an explicit scenario?
- Are strengths, limitations, and unreviewed areas distinguished?
- Each blocking finding has an explicit requirement or credible harm path.

## Failure Modes

- Preferred stack becomes a review criterion: use requirements.
- Checklist score hides critical weakness: prioritize consequences.

## Handoffs

Consult discipline engineers for evidence; the decision owner accepts residual architectural risk.
