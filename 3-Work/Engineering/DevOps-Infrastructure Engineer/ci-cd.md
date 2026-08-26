# CI CD

Context: [DevOps-Infrastructure Engineer](README.md).

## Purpose

Build a repeatable pipeline that produces and promotes verifiable artifacts.

## Activate When

Manual build or release steps need reliable automation.

## Do Not Use When

Do not grant broad credentials or execute untrusted contributions with privileged secrets.

## Required Context

**Needed:** Real build/test commands, repository trust model, artifact destination, and promotion authority.

**Can be deferred or bounded:** Start with the existing build path; advanced pipeline features need a concrete failure or repeatability benefit.

## Workflow

1. Inspect actual local build and test behavior and current deployment requirements.
2. Separate untrusted validation from privileged publication or deployment.
3. Build a traceable artifact once, record provenance, and promote it through appropriate checks.
4. Test failure paths, canceled runs, concurrency, and rollback to a known artifact.

## Artifact Promotion

Bind the release to commit, dependency lock state, build environment, artifact digest, and checks. Separate untrusted contribution tests from privileged publish/deploy jobs. Test concurrent releases and canceled jobs so an older run cannot overwrite a newer approved deployment.

## Decision Rules

- If pull-request code is untrusted, do not expose production secrets to its execution.
- If a pipeline rebuilds for each environment, verify that promoted content remains equivalent or prefer immutable promotion.

## Output Contract

Pipeline definition with validation, artifact identity, promotion gates, secrets handling, and failure recovery.

## Quality Gates

- Can a release be traced to commit, dependencies, tests, and artifact?
- Do failed gates prevent deployment and preserve useful diagnostics?
- The deployed artifact is the tested artifact and failed gates prevent promotion.

## Failure Modes

- Green pipeline skips relevant tests: verify coverage.
- Mutable tags obscure deployed content: record immutable identity.

## Handoffs

Security checks credentials and supply chain; engineers own test commands; release owner defines promotion authority.
