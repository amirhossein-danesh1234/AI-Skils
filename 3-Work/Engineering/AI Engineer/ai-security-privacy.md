# AI Security Privacy

Context: [AI Engineer](README.md).

## Purpose

Identify and reduce AI-specific data and authority exposure across the full feature lifecycle.

## Activate When

A feature sends data to models, retrieves private evidence, uses memory/tools, or consumes untrusted content.

## Do Not Use When

Security Engineer owns independent threat assessment; AI Engineer supplies behavior and pipeline mechanisms, not legal certification.

## Required Context

**Needed:** Data-flow map, data classes, providers/deployment, tenancy, tool authority, retention/deletion needs, and authorized test scope.

**Can be deferred or bounded:** Supplier promises need current contract/configuration confirmation before sending protected data; do not infer zero retention or no training from a product label.

## Workflow

1. Trace prompts, retrieved chunks, embeddings, outputs, caches, traces, eval datasets, and backups. Identify who can access each copy and how deletion or revocation reaches it.
2. Model indirect injection, data exfiltration, cross-tenant retrieval, poisoned corpus/model artifacts, unsafe generated code/queries, and excessive tool authority using concrete paths.
3. Minimize transmitted data; isolate tenants and sessions; enforce tool authorization, destination restrictions, output handling, and egress controls outside the model.
4. Review provider region, retention, training use, subprocessors, access, and change terms against approved requirements. Obtain qualified privacy/legal review where needed.
5. Test malicious source/tool content, stale permissions, cache leakage, deletion, and control outage with safe fixtures. If tools fetch URLs, include the effective-destination and redirect/DNS fixtures in [tool-use-design.md](tool-use-design.md); initial-host allowlisting alone is not evidence of safe egress. Record residual paths and containment ownership.

## Decision Rules

- If required data-handling guarantees cannot be established, do not transmit the protected data; use a permitted alternative or hold.
- If a model can request arbitrary destinations or privileged tools, constrain the service boundary rather than trusting its instruction compliance.

## Output Contract

AI data inventory and threat paths, enforced controls, supplier/configuration evidence, adversarial test results, deletion/revocation checks, and residual-risk handoff.

## Quality Gates

- A poisoned document cannot grant access or trigger exfiltration through an allowed tool.
- Private evaluation and telemetry data have the same deliberate controls as production inputs.

## Failure Modes

- Embeddings assumed anonymous or harmless by default.
- Prompt secrecy treated as the primary defense.

## Handoffs

Security Engineer independently challenges controls; Backend/Database enforce access; DevOps controls egress/secrets; qualified privacy/legal owner confirms obligations.

## References

[OWASP Gen AI risks](https://genai.owasp.org/llm-top-10/) supplies a threat-discovery aid. Apply the actual data and action paths; the list is not a security certification.
