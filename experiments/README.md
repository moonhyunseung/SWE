# Experiments

This directory is intentionally empty of protocols at initialization.

An idea moves from `ideas/` into `experiments/` only when:

1. the object being measured is defined well enough to implement;
2. the experiment changes or measures a specific quantity rather than mixing multiple interventions;
3. success/failure criteria are written before the run;
4. required provenance (task/repo revision, model revision, seeds, verifier, environment) can be recorded;
5. the result can falsify or materially weaken the associated idea.

Initial likely promotion order:

```text
O01 same-task PASS/FAIL geometry
        ↓
I02 / O03 structural GT alignment
        ↓
O04/O05 representation stress tests
        ↓
O06 endogenous recoverability
        ↓
I05 exogenous information if required
        ↓
I06 causal intervention
        ↓
O07 cross-repository transfer
```

Do not introduce artificial PLAN/risk/vector stages into baseline trajectories merely to make representation extraction easier. Natural solver trajectories are the default observation source.
