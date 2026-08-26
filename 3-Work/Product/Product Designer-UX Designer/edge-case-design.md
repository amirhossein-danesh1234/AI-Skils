# Edge Case Design

Context: [Product Designer-UX Designer](README.md).

## Purpose

Specify user-facing behavior when ordinary assumptions fail.

## Activate When

A flow has incomplete error, boundary, concurrency, or permission behavior.

## Do Not Use When

QA [edge-case-analysis.md](../../Engineering/QA-Test%20Engineer/edge-case-analysis.md) discovers test coverage; this skill chooses coherent user behavior with approved policy.

## Required Context

**Needed:** Task state model, consequential effects, and known limits or permission rules.

**Can be deferred or bounded:** Visual polish may wait; unknown retry/undo guarantees require engineering input before recovery behavior is approved.

## Workflow

1. Enumerate empty and oversized data, invalid input, interruption, delay, denial, duplication, and conflicting updates.
2. Identify which state is authoritative and what the user can safely retry or undo.
3. Design feedback that explains the consequence without exposing sensitive internals.
4. Walk return visits and partial completion to ensure the user can recover without repeating unsafe actions.

## Recovery Contract

For each failure, specify what the server knows, what the user sees, what data survives, and the next safe action. Distinguish failed from still-processing and outcome-unknown. A retry label must not promise safety that the underlying operation cannot provide.

## Decision Rules

- If retry can duplicate a side effect, require backend guarantees before offering it.
- If policy is unclear, record the decision rather than inventing an error outcome.

## Output Contract

Edge-state catalog with trigger, user message, allowed actions, persistence, recovery, and owner.

## Quality Gates

- Does each important failure have a safe and understandable next action?
- Are recovery states consistent with persisted server state?
- Interrupted and duplicate actions cannot produce conflicting user and authoritative states.

## Failure Modes

- Generic error for every case: distinguish actionable causes.
- Frontend recovery assumes backend guarantees: verify the contract.

## Handoffs

Backend Engineer defines consistency and idempotency; Product Manager approves policy; QA turns states into tests.
