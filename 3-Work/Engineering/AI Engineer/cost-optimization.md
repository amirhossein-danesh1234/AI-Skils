# Cost Optimization

Context: [AI Engineer](README.md).

## Purpose

Reduce total cost per useful AI outcome without hiding failure or transferring unbounded work to people.

## Activate When

AI spend grows or a feature cannot fit its unit economics.

## Do Not Use When

Financial Analyst reconciles company economics; this skill changes the AI execution cost drivers.

## Required Context

**Needed:** Usage by task/attempt, current prices, quality gates, retries, review burden, and cost ceiling.

**Can be deferred or bounded:** Allocate shared platform cost separately from marginal request cost; unknown human review time needs sampling, not a zero default.

## Workflow

1. Build a cost ledger for input/output tokens, cached tokens, retrieval, tool calls, retries, fallbacks, storage, evaluation, and human handling.
2. Divide by accepted task outcomes as well as attempts. Segment long inputs, loops, high-refusal tasks, and heavy users to identify the actual driver.
3. Compare task elimination, deterministic routing, smaller evaluated models, context reduction, batch processing, bounded output, and permission-safe caching.
4. Test routing errors and cascade overhead; a cheap model that frequently escalates may cost more. Re-evaluate critical slices rather than trading away unpriced harm.
5. Set per-run and aggregate spend limits, anomaly alerts, and stop/degrade behavior. Recheck provider pricing and terms at deployment time.

## Decision Rules

- If savings depend on invisible human cleanup, include that cost before recommending the change.
- If the budget expires, use the approved fallback; do not silently produce lower-quality consequential output.

## Output Contract

Cost decomposition, marginal and allocated costs, success denominator, tested savings, quality effects, and spend controls.

## Quality Gates

- Costs reconcile to representative billing/usage records and all attempts are included.
- The cheaper path passes the same critical gates and does not shift work outside the measured boundary.

## Failure Modes

- Cost per call improves while cost per successful task worsens.
- Unbounded agent retries erase per-token savings.

## Handoffs

Financial Analyst validates economics; evaluation-design checks quality; DevOps enforces budgets; Founder Advisor weighs major investment trade-offs.
