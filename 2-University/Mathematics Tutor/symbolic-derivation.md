# symbolic-derivation

[Mathematics Tutor](README.md) / [University domain](../../README.md)

## Mathematical Goal

Transform mathematical expressions with explicit domain and equivalence conditions.

## Use This For

An expression, equation or operator relation requires a transparent exact transformation.

## Validity Boundary

Do not cancel, divide, square, differentiate or interchange limits without preserving validity conditions.

## Definitions and Preconditions

Starting expression and target, variable domains, parameter restrictions, branch/convention choices, allowed identities and desired simplification.

## Reasoning Protocol

1. Declare domains, excluded values and equivalence target. Identify operations that may create, lose or branch solutions.
2. Transform in short justified steps, factoring or changing representation to expose structure. Carry constants, indices, signs and conditions.
3. Handle cases explicitly when dividing by expressions, selecting branches or interchanging sums, limits, derivatives or integrals.
4. Verify by reverse transformation, differentiation/substitution, symbolic structure and selected numerical points that do not replace the exact argument.

## Validity Ledger

Annotate steps as equality, equivalence under conditions, one-way implication, approximation or definition. For complex variables, state branch cuts; for matrices/operators, preserve order and required invertibility/regularity.

## Validity Rules

- Simplest-looking form is not preferred if it hides domain or stability.
- Use a computer algebra system as a conjecture/check tool and record assumptions, not as unexplained authority.

## Mathematical Output

Symbolic derivation with conditions, annotated steps, cases/branches, exact result, reverse or independent check and interpretation where relevant.

## Independent Checks

- No transformation silently changes the solution set.
- Derivative/integral/limit operations satisfy required regularity or state the gap.

## Logical Failure Modes

- **Canceling a possibly zero factor:** split cases.
- **Principal branch silently assumed:** declare convention and alternatives.

## Handoffs

Proof Analysis resolves logical consequences; Solution Verification checks candidates; Physics Tutor interprets physical constraints.
