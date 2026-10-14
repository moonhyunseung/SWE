# I04 — Residual MLP

## Motivation

If a linear probe cannot recover a credible residual but a small nonlinear map can, the missing mechanism may be a coordinate/readout problem rather than missing SWE knowledge.

## Candidate object

`h_t -> MLP_phi(h_t) -> r_hat_t`

Base model remains frozen.

## Minimal version

A small 2-layer MLP with a controlled bottleneck and capacity-matched baselines. Architecture is deliberately not frozen yet.

## Interpretation discipline

A positive result supports: `residual information is recoverable nonlinearly from frozen state`.

It does **not** by itself support: `the model already knows how to use the correction` or `the MLP learned no new task-specific information`.

## Trigger

Only after I01 linear probing is insufficient under a credible target.

## Next step

If prediction is good, test whether the predicted residual has causal utility through I06 or another intervention interface.

**Status:** CONCEPT
