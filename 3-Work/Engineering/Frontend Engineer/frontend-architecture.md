# Frontend Architecture

Context: [Frontend Engineer](README.md).

## Purpose

Structure client code around clear feature, state, and rendering boundaries.

## Activate When

A frontend needs organization or a cross-cutting change exceeds a local component.

## Do Not Use When

Do not introduce a new framework or global store merely to standardize a small feature.

## Required Context

**Needed:** Current code/routes, rendering model, state sources, and target change.

**Can be deferred or bounded:** New libraries and global stores require demonstrated need, not architectural symmetry.

## Workflow

1. Inspect existing feature organization, rendering modes, routing, and build constraints.
2. Map server state, local interaction state, URL state, and persistent preferences separately.
3. Choose boundaries that keep data access and side effects understandable without excessive abstraction.
4. Migrate incrementally and test navigation, hydration where relevant, and error recovery.

## Runtime Ownership

Map one interaction from URL and server state through rendering to mutation and refresh. Decide where cache, local draft, and persisted preference live and how they are invalidated. Include server/client boundaries and hydration only if the framework actually uses them.

## Decision Rules

- If state is needed by one component subtree, keep it local unless another requirement justifies promotion.
- If a convention already works, extend it rather than creating a parallel architecture.

## Output Contract

Scoped architecture proposal or implementation with module boundaries, state ownership, dependencies, tests, and migration.

## Quality Gates

- Are import dependencies and state ownership clear?
- Do route transitions, loading, and failure behavior remain correct?
- The proposed module structure explains runtime state and side effects, not just folder names.

## Failure Modes

- Folder taxonomy without runtime reasoning: trace a user interaction.
- Global state for convenience: minimize scope and synchronization.

## Handoffs

Software Architect handles system boundaries; UX and UI define behavior and appearance; Backend Engineer owns server contracts.
