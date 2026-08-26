# Guardrail Design

Context: [AI Engineer](README.md).

## Purpose

Place enforceable controls around AI inputs, outputs, and actions for specific failure risks.

## Activate When

An AI feature can disclose data, trigger actions, incur cost, or produce harmful unsupported output.

## Do Not Use When

Security Engineer owns overall threat assessment; a prompt warning or classifier alone is not a security boundary.

## Required Context

**Needed:** Threat/failure paths, prohibited effects, legitimate use cases, trust boundaries, and control authority.

**Can be deferred or bounded:** Classifier thresholds can be tuned; hard authorization and action limits must exist before consequential execution.

## Workflow

1. Map each risk to an enforcement point: input eligibility, retrieval scope, tool authorization, deterministic argument validation, output handling, rate/cost limit, or human approval.
2. Use deterministic controls for hard invariants and probabilistic detection for signals that cannot be specified reliably. Keep enforcement outside the model whose behavior is being constrained.
3. Define fail-open/closed/degraded behavior per risk when a control is unavailable, including review capacity and user-visible recovery.
4. Test direct and indirect injection, encoding/obfuscation, multi-turn bypass, race conditions, malicious tool output, and benign edge cases. Measure false accepts and false rejects.
5. Version policies and route detected incidents to an owner; monitor bypasses and excessive blocking without retaining unnecessary sensitive payloads.

## Decision Rules

- If a control must prevent unauthorized money or data effects, enforce it at the action boundary even when the model or detector says safe.
- If a guardrail adds latency or rejects legitimate work, evaluate the trade-off without silently weakening a hard constraint.

## Output Contract

Risk-to-control map with enforcement code boundary, failure mode, tests, detection metrics, operational owner, and residual risk.

## Quality Gates

- The unsafe effect remains blocked when the model produces adversarial output.
- Control outage and review-queue overflow have a defined safe path.

## Failure Modes

- Input filter assumed to stop malicious retrieved content.
- Safety score replaces a permission check.

## Handoffs

Security challenges threat coverage; Backend enforces invariants; QA tests bypasses; fallback-design handles controlled degradation.
