# RAG Design

Context: [AI Engineer](README.md).

## Purpose

Design an evidence-grounded answer system with a measurable path from sources to supported output.

## Activate When

A model must answer from a changing or private corpus rather than general model knowledge.

## Do Not Use When

retrieval-design optimizes evidence finding; RAG is the end-to-end ingest/retrieve/answer/verify lifecycle, not a guarantee of truth.

## Required Context

**Needed:** Question distribution, corpus rights and owners, source authority, freshness, access rules, and answer acceptance.

**Can be deferred or bounded:** Index technology is deferrable. A pilot needs real representative questions and answerable/unanswerable examples.

## Workflow

1. Map ingestion, parsing, chunking, metadata, versioning, access control, indexing, retrieval, context assembly, generation, citation, and deletion. Assign source-of-truth ownership.
2. Define the answer contract: claims requiring support, source locator/version, handling of missing or conflicting evidence, and allowed synthesis.
3. Build a baseline with known-source questions. Evaluate retrieval separately from answer support and task success so failures can be localized.
4. Test stale/withdrawn documents, tenant changes, unsupported questions, contradictory sources, and injected source instructions. Apply permissions before evidence leaves the trusted retrieval layer.
5. Define refresh/deletion propagation and monitor corpus/query drift. Ship only the evaluated configuration with abstention and a non-RAG route for unsupported tasks.

## Decision Rules

- If decisive evidence was not retrieved, improve corpus/retrieval or abstain; prompt pressure cannot recover absent facts.
- If the source is outdated or unauthorized, a high similarity score does not make it usable.

## Output Contract

RAG lifecycle design, answer/citation contract, access and freshness rules, decomposed evaluation, failure routing, and operation owners.

## Quality Gates

- A cited claim is supported by the cited accessible passage, not merely a related document.
- Revoked or deleted content disappears from indexes, caches, and returned context within the defined requirement.

## Failure Modes

- More chunks increase unsupported synthesis and distract from decisive evidence.
- Retrieval score mistaken for calibrated factual confidence.

## Handoffs

retrieval-design optimizes finding; context-engineering assembles evidence; Database/Backend own storage and access; Security independently challenges trust.
