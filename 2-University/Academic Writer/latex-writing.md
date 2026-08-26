# latex-writing

[Academic Writer](README.md) / [University domain](../../README.md)

## Communication Aim

Express supported academic content in maintainable, compiling LaTeX.

## Activate For

Academic content needs reliable LaTeX structure, mathematics, cross-references or bibliography.

## Writing Boundary

Typesetting cannot fix unsupported content, and generated code must be compiled and inspected.

## Source Materials

Supported content, target class/template/engine, package constraints, bibliography system, figures/tables/assets and required output checks.

## Writing Workflow

1. Preserve the venue template and define engine/toolchain before adding packages. Structure semantics with sections, labels, environments and reusable commands.
2. Encode mathematics with correct operators, delimiters, alignment and notation; keep prose outside math and provide accessible figure/table captions.
3. Manage figures/tables/bibliography with stable paths/keys and cross-references; avoid hard-coded numbering and conflicting packages.
4. Compile from clean state, inspect log for errors/meaningful warnings and visually verify equations, floats, references, bibliography and page overflow.

## Compile–Render Loop

Source validity and rendered validity are both required. A successful compile can still produce clipped equations, misplaced floats or unresolved meaning; visual inspection complements log review.

## Evidence and Authorship Rules

- Do not alter scientific claims merely to fix layout.
- Use the minimum package/macro complexity that makes the document maintainable.

## Writing Deliverable

Compiling LaTeX source with declared toolchain, organized structure, valid references/bibliography, accessible figures/tables and QA notes.

## Editorial Quality Gates

- No unresolved references/citations or compilation errors remain.
- Rendered output preserves notation, hierarchy and required template constraints.

## Integrity Failure Modes

- **Package added for every issue creates conflicts:** simplify.
- **Source edited without compiling/rendering:** run both checks.

## Handoffs

Citation Management supplies verified records; Paper Structure supplies organization; PDF tooling may inspect final rendering.
