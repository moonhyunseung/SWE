# I02 — Structural GT Projection

## Motivation

The full ideal SWE state is not currently defined. A first objective anchor can be extracted from verifier-valid patches without pretending it is the complete solution geometry.

## Candidate projection

For each valid solution, record repository-relative structures such as:

- changed files;
- changed symbols;
- AST edit locations/types;
- caller/callee or dependency neighborhood;
- related tests;
- optional execution-path differences.

Call the result `P_struct(s*)`.

## Design rule

Preserve raw provenance. Every structural element must be traceable back to a specific valid patch/repository revision and extraction procedure.

## Important limitation

`P_struct(s*)` is a **GT projection**, not proof that the true corrective state is a program graph or edit set.

## First use

O03: ask whether PASS/FAIL geometry points toward the structures changed by valid solutions.

## Possible implementation stack

Start language-specific if necessary (e.g. Python AST + symbol/call extraction) rather than hiding weak parsing behind a falsely universal schema. Generalize only after the concept works.

**Status:** FIRST PRACTICAL GT CANDIDATE
