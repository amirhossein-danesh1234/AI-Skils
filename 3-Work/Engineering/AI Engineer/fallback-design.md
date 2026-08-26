# Fallback Design

Context: [AI Engineer](README.md).

## Purpose

Keep an AI-assisted task useful and safe when its primary path fails or abstains.

## Activate When

Provider failure, quality rejection, budget limits, or unsupported inputs can prevent completion.

## Do Not Use When

Retries are not a universal fallback; DevOps owns platform recovery and Backend owns write reconciliation.

## Required Context

**Needed:** Failure taxonomy, acceptable degraded outcomes, latency budget, action state, and available human/non-AI routes.

**Can be deferred or bounded:** Alternate providers are optional. Never assume their data permissions, behavior, or schemas match the primary.

## Workflow

1. Classify transport, quota, timeout, schema, evidence, policy, and task-quality failures. Distinguish no effect from unknown external effect.
2. Define a route per class: bounded retry, smaller task, alternate evaluated configuration, deterministic answer/search, queued human review, or explicit inability.
3. Budget the whole attempt chain for elapsed time and cost. Carry context, evidence provenance, privacy restrictions, and operation identity across routes without broadening authority.
4. Specify terminal states and user messaging. Human fallback needs queue capacity, response expectations, and ownership; if unavailable, stop safely rather than promising service.
5. Inject failures at each transition and verify no loop, duplicate effect, hidden degradation, or deadline overrun. Evaluate alternate models independently on the same risk gates.

## Decision Rules

- If the outcome of a write is unknown, reconcile before any redispatch; switching models or providers does not reset operation identity.
- If a task is refused for a valid safety or permission reason, do not route around the restriction.

## Output Contract

Failure-routing state machine with budgets, terminal states, ownership, degraded UX, tested transitions, and no-duplicate-effect evidence.

## Quality Gates

- Every failure class reaches a bounded terminal state or an owned queue.
- Fallback does not lower required privacy, authorization, or critical-quality gates.

## Failure Modes

- Fallback chain increases latency past the user deadline.
- Human review exists only as a diagram box.

## Handoffs

Backend resolves ambiguous effects; DevOps manages provider outages; Product/UX define degraded behavior; evaluation-design validates alternatives.
