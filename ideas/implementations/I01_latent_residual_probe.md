# I01 — Latent Residual Probe

## Motivation

If a credible GT residual target exists, first ask whether frozen model representations already contain it.

## Minimal object

`h_t -> W h_t -> r_hat_t`

Base model frozen. Start with the smallest linear readout compatible with the target representation.

## Assumes

- a meaningful residual target already exists;
- model states are captured at defined natural checkpoints;
- train/test separation prevents task identity leakage.

## Does not assume

- the model uses the decoded information;
- the residual is low-dimensional;
- a graph is necessary;
- linear success implies causality.

## Evaluation

Held-out residual prediction/alignment, repository holdout when possible, random-label and task-ID controls.

## Trigger

Implement after O03 produces a defensible target/alignment story.

**Status:** CONCEPT
