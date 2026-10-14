# O06 — Endogenous Information

## Intuition

Before adding graphs, new training, or agent machinery, test whether the required GT correction is already encoded in the frozen model.

## Question

Given frozen model state `h_t`, how much of a GT-derived residual target `r_t*` can be recovered?

## Observation ladder

1. linear readout;
2. shallow/small nonlinear readout;
3. only then consider external structure or weight adaptation.

## Interpretations

- Linear succeeds: correction information is directly accessible in the representation.
- Linear fails, small MLP succeeds: information may be endogenous but nonlinearly entangled / coordinate-misaligned.
- Both fail: information may be absent, the target/representation may be wrong, or exogenous observation may be required.

## Important caution

Decodability does not imply that the base model functionally uses the information. Causal intervention is a later question.

## Connection

Implementation candidates I01 and I04. If both fail under a credible target, test I05.

**Status:** BLOCKED ON RESIDUAL TARGET
