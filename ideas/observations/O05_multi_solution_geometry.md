# O05 — Multiple Valid Solutions

## Intuition

A benchmark gold patch is not necessarily the unique correct solution. Training against one literal patch can punish an alternative valid solution.

## Object

For one task, collect multiple independently verifier-valid solutions when possible:

`S_E = {s_1*, s_2*, ...}`.

Ask whether their projections form a shared solution region/subspace after nuisance transformations are removed.

## Questions

- Are structurally different valid patches close in the candidate comparison representation?
- Does a model trajectory need to move toward one exact patch, or only toward a broader valid region?
- What components of the correction are invariant across valid solutions?

## Why it matters

This distinguishes **gold-patch imitation** from **solution geometry**.

## Possible consequence

The target may need to be a set-valued residual or nearest-valid-solution correction rather than a single fixed vector.

**Status:** UNTESTED
