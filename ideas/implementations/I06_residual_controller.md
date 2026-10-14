# I06 — Residual Controller

## Motivation

A residual can be useful without being injected directly into transformer activations. The safest first causal test may be to convert it into external control over the agent.

## Possible interfaces

A predicted correction may rank or constrain:

- files/symbols to inspect;
- dependency paths to follow;
- search targets;
- edit regions;
- tool choice;
- test/verification actions;
- context selection.

## Candidate mapping

`r_hat_t -> C(r_hat_t) -> corrective control signal`

## Causal controls

Compare at least:

- predicted positive correction;
- no correction;
- norm/capacity-matched random correction;
- shuffled-task correction;
- opposite/anti-correction where the interface supports a meaningful sign.

## Success criterion

Correction should improve actual verifier outcomes or recover failed trajectories, not merely predict GT labels.

## Trigger

Only once a residual is predictably recoverable and has objective GT alignment.

**Status:** FUTURE CONCEPT
