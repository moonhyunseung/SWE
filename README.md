# SWE Residual Geometry

Internal research notebook for an early SWE-agent idea.

## Core question

Can verifier-valid solutions reveal the **correction missing from an SWE agent's current solving state**, rather than forcing the model to relearn the entire software-engineering mapping?

Conceptually:

```text
ideal solving state
        -
model solving state
        ↓
corrective residual
```

The hard part is not writing the subtraction. The hard part is finding a representation in which `ideal` and `actual` are legitimately comparable across heterogeneous repositories, languages, frameworks, runtimes, and trajectories.

## Motivation

Modern SWE methods improve agents through retrieval/localization, repository graphs, dependency-aware planning, constrained workflows, execution feedback, verifier signals, and post-training. These interventions work, but they often leave the same underlying question unresolved:

> When the model fails, what exactly was missing?

Possible cases include:

1. the model lacks the required programming knowledge;
2. the required repository-specific fact was never observed;
3. the facts were observed but assembled into the wrong problem state;
4. the state was mostly correct but the model moved in the wrong solution direction;
5. the needed correction was internally represented but not usable by the policy.

This repository preserves the hypothesis that a verifier-valid solution can act as privileged ground truth for measuring that missing correction.

## Working objects

- **Environment** `E`: repository, issue, verifier/tests, runtime/tool environment.
- **Software state** `s_t`: externally existing repository/runtime state.
- **Observation** `o_t`: the part of the environment actually observed by the agent.
- **Model state** `h_t`: internal model representation after observations/actions.
- **Trajectory** `tau`: sequence of observations and actions ending in PASS/FAIL.
- **Valid solution set** `S_E`: verifier-valid solutions, not necessarily one gold patch.
- **Comparison representation** `z = Psi(E, tau, h)`: still unknown; the central representation problem.
- **Corrective residual** `r* = Delta(z, z*)`: correction from current state toward a valid-solution state. `Delta` is not assumed to be ordinary vector subtraction.
- **Outcome contrast**: same-task PASS-vs-FAIL difference; a cheap observable candidate, not ground truth.

## Research map

### Observation ideas

- [O01 — Same-task PASS/FAIL direction](ideas/observations/O01_pass_fail_direction.md)
- [O02 — Trajectory divergence](ideas/observations/O02_trajectory_divergence.md)
- [O03 — GT alignment](ideas/observations/O03_gt_alignment.md)
- [O04 — Symmetry / equivariance](ideas/observations/O04_symmetry_invariance.md)
- [O05 — Multiple valid solutions](ideas/observations/O05_multi_solution_geometry.md)
- [O06 — Endogenous information](ideas/observations/O06_endogenous_information.md)
- [O07 — Cross-repository transfer](ideas/observations/O07_cross_repo_transfer.md)

### Candidate implementation ideas

- [I01 — Latent residual probe](ideas/implementations/I01_latent_residual_probe.md)
- [I02 — Structural GT projection](ideas/implementations/I02_structural_gt_projection.md)
- [I03 — Hybrid state space](ideas/implementations/I03_hybrid_state_space.md)
- [I04 — Residual MLP](ideas/implementations/I04_residual_mlp.md)
- [I05 — Graph-conditioned residual](ideas/implementations/I05_graph_conditioned_residual.md)
- [I06 — Residual controller](ideas/implementations/I06_residual_controller.md)
- [I07 — Energy / potential field](ideas/implementations/I07_energy_field.md)

## Current roadmap

```text
natural SWE trajectories
        ↓
PASS / FAIL contrasts                         [O01, O02]
        ↓
compare against objective GT structure        [O03, I02]
        ↓
find a common comparison representation       [I03, O04, O05]
        ↓
ask whether correction is already endogenous  [O06, I01, I04]
        ↓
if not, add external structural observation    [I05]
        ↓
turn predicted correction into intervention   [I06]
        ↓
test held-out repository transfer             [O07]
```

The roadmap is result-dependent. A candidate implementation is not promoted to the main method merely because it is convenient.

## Working rule

> **Observation first. Add the minimum mechanism required by the observed missing information.**

Do not prematurely freeze:

- graph as the canonical state representation,
- a manifold or PDE formulation,
- a low-rank residual assumption,
- an MLP architecture,
- activation steering,
- LoRA/SFT/RL,
- an energy function.

Those are candidates. The core research object is the GT-guided corrective residual and the question of where that correction lives.

## Geometric intuition

The earlier `N, p, r, u, d` intuition is kept as an analysis lens rather than a hand-designed label space. If a meaningful residual geometry exists, these may appear as properties such as location/support, magnitude, direction, effective dimensionality, and number of active correction components.

## Provenance

User-originated research intuition preserved here:

- raw SWE environments are too heterogeneous to treat naive `x -> solution` generalization as the whole story;
- use the difference between an ideal/verifier-valid solution and what the model actually did as a GT-guided residual signal;
- distinguish endogenous correction, lightweight learned correction, exogenous structural information, and genuine model training;
- use PASS/FAIL differences as a cheap candidate observation;
- interpret the problem through graph theory, symmetry/group ideas, dynamical systems/PDE intuition, and geometric primitives rather than a hand-written semantic taxonomy.

Formal terms such as equivariance, corrective field, probes, hybrid state representations, and energy/potential formulations are candidate mathematical/implementation formalisms and are not treated as established results.

## Status

**CONCEPT / INTERNAL NOTEBOOK.** No main method or scientific claim is frozen yet.
