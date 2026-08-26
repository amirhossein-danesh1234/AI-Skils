# Retrieval Design

Context: [AI Engineer](README.md).

## Purpose

Select and rank evidence that is relevant, authorized, and sufficient for a defined query distribution.

## Activate When

Search misses decisive documents or retrieves noise in an AI evidence pipeline.

## Do Not Use When

rag-design owns end-to-end supported answers; Database Engineer owns physical database integrity and query operations.

## Required Context

**Needed:** Query samples, corpus structure, relevance judgments or known evidence, permission filters, and latency budget.

**Can be deferred or bounded:** Begin with expert-judged seed queries if logs are unavailable; keep a holdout and report labeling uncertainty.

## Workflow

1. Define the retrieval unit and relevance: exact fact, multi-hop evidence, lexical identifier, or semantic topic. Audit parsing and chunk boundaries before changing the embedding model.
2. Establish simple lexical and/or dense baselines. Compare hybrid retrieval, metadata filters, query rewriting, reranking, and chunk sizes only against observed failure classes.
3. Evaluate recall of decisive evidence at the actual context budget, precision/ranking, latency, and slice failures. Measure after permission filtering; do not leak unauthorized hits or snippets.
4. Test rare identifiers, tables, negation, mixed language, version conflicts, out-of-domain queries, and updates/deletions. Ensure query expansion does not change user intent.
5. Choose the smallest useful candidate set and preserve document/version/locator metadata for downstream verification.

## Decision Rules

- If relevant evidence never entered the corpus correctly, repair ingestion before tuning ranking.
- If relevance labels are incomplete, inspect apparent false positives rather than automatically penalizing valid evidence.

## Output Contract

Retrieval specification and benchmark with query slices, relevance judgments, retrieval budget, filter order, results, and failure diagnosis.

## Quality Gates

- End-to-end answer performance improves or the retrieval-only benefit is explicitly limited.
- Tenant and freshness constraints hold under cache and index-update tests.

## Failure Modes

- Embedding benchmark selected without task relevance.
- Recall measured before access filtering overstates usable evidence.

## Handoffs

rag-design receives evidence; context-engineering controls inclusion; Backend enforces access; Database validates index lifecycle.
