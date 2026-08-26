# Workflow Reliability

Context: [AI-Orchestrator](README.md).

## Purpose

Handle retries, unknown effects, recovery, budgets and terminal states.

## When to Use

A multi-step workflow can fail, be interrupted or repeat effects, or needs defensible completion/stop semantics.

## Boundary

Does not invent provider guarantees or operate production without mandate.

## Inputs

State transitions, external effects, available authoritative status, task budget, cancellation behavior, actual service guarantees and impact.

## Method

1. Inventory failure boundaries: unavailable dependency, invalid output, stale input, denied authority, timeout, crash after effect and interrupted verification. Prioritize failures by consequence and plausible exposure.
2. Represent not-started, in-flight, confirmed-complete, rejected, cancelled and unknown outcomes separately. A timeout after a write is unknown unless authoritative evidence establishes otherwise.
3. For repeatable actions, require a stable logical operation identity and verified deduplication/reconciliation contract from the implementation owner. Concurrent attempts, payload changes and retention expiry need explicit behavior.
4. Retry only transient failures for which repetition is safe and useful; bound attempts, elapsed time and cost at task level. Permission denial, deterministic invalid input and a failing invariant need correction or escalation, not faster retries.
5. Resume from authoritative effect state and current approvals. Cancellation does not undo completed effects; compensation is a separate potentially consequential action requiring its own scope and evidence.
6. Verify completion at the user-outcome level, preserve unresolved operations with an owner, and report terminal status without concealing partial success.

## Unknown Is a Real State

If an effect may already have happened, query/reconcile the same operation before redispatch; a fresh identity or different tool must not bypass uncertainty. Do not promise exactly-once behavior from a narrative plan or a provider keyword. Check actual guarantee scope and lifetime. A safe fallback may be explicit inability or an owned pause. Stop when the outcome is verified, further action is unauthorized/unsafe, the budget is exhausted, or no permitted check can resolve the blocker.

## Output

Failure/state table, retry and reconciliation policy, resume/cancel gates, bounded fallback, observable completion proof and unresolved-effect handoff.

## Quality Checks

- A crash-after-effect walkthrough cannot create an unapproved duplicate operation.
- Success, partial completion, unknown and failure remain distinguishable to the next actor; no silent infinite loop or unstaffed human fallback.

## Handoffs

Domain operators implement recovery controls; [output-evaluation](output-evaluation.md) checks reporting and [result-validation](../Problem-Solver/result-validation.md) checks the actual outcome.
