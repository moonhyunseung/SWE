# O03 — GT Alignment

## Intuition

A stable PASS/FAIL direction is not enough. It may encode confidence, verbosity, or generic correctness. It becomes interesting for SWE only if it points toward something objectively required by a verifier-valid solution.

## Privileged anchors

Possible GT-derived structural anchors include:

- changed files;
- changed symbols/functions/classes;
- AST edits;
- dependency/call neighborhood affected by the valid patch;
- tests related to the modification;
- runtime/execution changes when available.

These are projections of GT, not the final definition of the ideal state.

## Core question

Does the empirical PASS/FAIL contrast or model-state deviation align with the structures actually modified by a valid solution?

Conceptually:

`outcome-derived contrast  ?~  GT-derived corrective structure`

## Positive result

Provides evidence that PASS/FAIL differences contain solution-relevant information and may be usable as cheap pseudo-GT.

## Negative result

A PASS/FAIL separator may exist while having little to do with the required software correction. Do not call it a solution direction.

## Connection

Requires I02 structural GT projection. Feeds I01/I03/I04 only if alignment is nontrivial.

**Status:** UNTESTED
