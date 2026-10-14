# I03 — Hybrid State Space

## Motivation

Raw model hidden state may contain semantics but lack stable repository coordinates; explicit program structure may contain coordinates but lack model-level semantic judgment. A hybrid state may be needed.

## Candidate object

`z_t = Psi(h_t, G_t, o_t)`

where `G_t` is some repository/program structure and `o_t` contains current observations.

## Open choices

- node granularity: file / symbol / AST / mixed;
- graph relations: call / import / data-flow / test / runtime;
- how hidden states attach to program entities;
- whether the result is a vector, node field, edge field, or set-valued object.

## Trigger

Do not build this merely because graphs are available. Build only if O03/O04/O06 indicate that model-only coordinates are insufficient and explicit structure is needed.

## Success criterion

The hybrid representation should improve GT alignment, symmetry robustness, and cross-repository comparability, not merely benchmark accuracy.

**Status:** CONCEPT
