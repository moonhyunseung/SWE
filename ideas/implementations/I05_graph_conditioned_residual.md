# I05 — Graph-Conditioned Residual

## Motivation

A code model may have general programming knowledge while lacking explicit access to the current repository's relational state. If model-only residual prediction fails, condition the correction on external structure.

## Candidate object

`r_hat_t = f(h_t, G_repo, o_t)`

where `G_repo` may expose symbol, call/import, dependency, test, or runtime relations.

## Key experiment

Use an observation ladder rather than one giant graph:

`model only -> + retrieved code -> + symbols -> + dependency/call -> + tests/runtime -> richer graph`

Measure marginal gain at each step against the same residual target.

## Why

The goal is to identify **which information is exogenously missing**, not to prove that graph neural networks are the answer.

## Trigger

Model-only linear/MLP recovery is inadequate and the residual target itself has passed basic validation.

**Status:** CONCEPT
