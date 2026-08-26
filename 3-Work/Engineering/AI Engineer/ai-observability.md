# AI Observability

Context: [AI Engineer](README.md).

## Purpose

Detect and diagnose AI behavior changes while minimizing sensitive telemetry.

## Activate When

An evaluated AI feature is piloted or operated and needs quality, cost, and failure visibility.

## Do Not Use When

DevOps logging/monitoring owns transport and platform signals; this skill defines AI-specific behavior evidence.

## Required Context

**Needed:** Task/run identifiers, configuration versions, quality signals, data sensitivity, and response owners.

**Can be deferred or bounded:** Raw prompts and outputs are optional restricted diagnostics, not default telemetry. Prefer metadata and sampled redacted evidence.

## Workflow

1. Trace request through context selection, model generation, validation, tools, fallback, and final task outcome. Record model/prompt/corpus/tool-policy versions and attempt relationships.
2. Measure task acceptance, abstention, critical failures, validation errors, retrieval support, loop/non-progress, latency distribution, and cost per completed task; keep denominators stable.
3. Design privacy-aware sampling and delayed outcome linkage. Separate user feedback from objective truth and do not use model confidence as the sole quality signal.
4. Set actionable alerts by owner and decision: contain exposure, investigate drift, restore a prior bundle, or inspect a harmful slice.
5. Test a synthetic quality regression and a provider outage. Verify traces support localization without exposing credentials, private source text, or unrelated tenant data.

## Decision Rules

- If provider success is high but task success falls, investigate semantic quality and context drift rather than declaring healthy service.
- If telemetry requires raw sensitive content, obtain the approved purpose, access, retention, and sampling controls before capture.

## Output Contract

AI telemetry schema, version lineage, quality/cost dashboard definitions, alert/runbook ownership, sampling policy, and detection test evidence.

## Quality Gates

- A failed task can be traced across attempts and fallback without double counting.
- Quality drift and missing telemetry are distinguishable from no incidents.

## Failure Modes

- Token and HTTP metrics substitute for task quality.
- Debug logging becomes an uncontrolled corpus of private data.

## Handoffs

DevOps operates signals; evaluation-design interprets behavior; Security reviews retention/access; Product Analyst links business outcomes.
