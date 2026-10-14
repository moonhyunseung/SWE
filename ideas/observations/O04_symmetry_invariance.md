# O04 — Symmetry / Equivariance

## Intuition

A useful SWE corrective object should not collapse when irrelevant coordinates change.

Examples of candidate nuisance transformations:

- identifier renaming;
- file/symbol ordering;
- graph-node permutation;
- semantics-preserving refactoring where a reliable mapping exists.

## Desired behavior

If `gamma` changes only representation coordinates, a useful state/correction should transform consistently rather than becoming unrelated.

Conceptually:

`R(gamma(E), rho(gamma) z) ~= rho(gamma) R(E, z)`.

This equation is a target intuition, not yet a proven group action for all program transformations.

## Cheapest observation

Start with transformations having an exact known correspondence, especially alpha/identifier renaming and explicit node permutation. Measure whether the candidate representation and residual move according to that correspondence.

## Why it matters

Cross-repository generalization is unlikely if the learned correction is tied to literal names or arbitrary ordering.

## Failure interpretation

Either the representation is coordinate-bound, the transformation is not actually semantics preserving, or the proposed residual is not a transferable object.

**Status:** UNTESTED
