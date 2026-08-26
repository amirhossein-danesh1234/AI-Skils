# Multi Agent Design

Context: [AI Engineer](README.md).

## Purpose

Determine whether bounded agent specialization improves a task enough to justify coordination cost.

## Activate When

Independent evidence work or distinct contexts may outperform a single agent or fixed workflow.

## Do Not Use When

Do not create agents merely to imitate an organization; personas in this library are reasoning roles, not a mandatory deployment topology.

## Required Context

**Needed:** Single-agent baseline, decomposable task, shared resources, communication needs, and total budget.

**Can be deferred or bounded:** Team topology is a hypothesis; benchmark it before committing infrastructure or claiming independent judgment.

## Workflow

1. Identify independently checkable subtasks and required context separation. Reject partitions that repeatedly need the same mutable state or duplicate the whole task.
2. Assign one accountable synthesizer and typed handoff artifacts: question, source/evidence IDs, result, uncertainty, and completion state. Define conflict resolution against evidence, not vote count.
3. Partition write ownership and capabilities. Serialize consequential shared mutations and maintain one operation ledger; agents cannot delegate more authority than they possess.
4. Allocate total and per-worker budgets, deadlines, cancellation, retry, and partial-result behavior. Handle unavailable workers without indefinite nested delegation.
5. Compare against the single-agent baseline for total success, correlated mistakes, critical misses, latency, cost, and reconciliation effort. Run ablations to show each worker adds value.

## Decision Rules

- If agents share a model and evidence chain, agreement is not independent corroboration.
- If coordination or duplicate work dominates, collapse the design to a simpler workflow.

## Output Contract

Topology decision with baseline comparison, partition/ownership map, message contract, budget, conflict/failure handling, and ablation evidence.

## Quality Gates

- Contradictory and missing worker outputs produce a defensible bounded result.
- Concurrent-worker tests cannot duplicate an authorized external action.

## Failure Modes

- Majority vote launders a common hallucination.
- Multiple writers race over the same state.

## Handoffs

agent-design owns individual loops; Backend/Database enforce mutation coordination; QA checks concurrency; Founder Advisor evaluates material operating burden.
