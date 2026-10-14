# O01 — Same-task PASS/FAIL Direction

## Intuition

The same SWE task, model, prompt/interface, and repository can produce both PASS and FAIL under stochastic rollout. Because the environment is held fixed, this is the cheapest setting for asking whether successful solving has a reproducible internal direction.

## Object

At a natural trajectory checkpoint `t`, let the comparison representation be `z_t`. When subtraction is meaningful, inspect

`c_t = E[z_t | PASS] - E[z_t | FAIL]`.

This is an **outcome contrast**, not GT and not a gradient.

## Cheapest observation

- original task prompt only;
- no inserted PLAN/risk/vector text;
- multiple stochastic rollouts with distinct seeds;
- collect natural checkpoints and final verifier outcome;
- split rollouts into independent A/B groups and compare directions.

Useful signals include split-half cosine, held-out PASS/FAIL projection, and pairwise orientation.

## What would be interesting

A direction that is reproducible across rollout splits, appears before the final answer, and is more stable within task than across unrelated tasks.

## Confounds

Generated-token identity, trajectory length, generic confidence/correctness directions, sampling artifacts, and checkpoint mismatch.

## Connection

Positive result -> O03 GT alignment and I01 latent residual probe.
Negative result -> weaken or abandon PASS/FAIL pseudo-GT route.

**Status:** UNTESTED
