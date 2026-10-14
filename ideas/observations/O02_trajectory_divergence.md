# O02 — Trajectory Divergence

## Intuition

FAIL is only a terminal bit. A stronger object is the point at which a failed trajectory stops moving like a successful one.

## Object

For aligned or comparable trajectory states, observe a distance or discrepancy sequence

`D_t = d(z_t^PASS, z_t^FAIL)`.

The exact state representation and alignment rule are deliberately unfixed.

## Questions

- Do PASS and FAIL already differ immediately after the task is read?
- Does divergence begin after a particular observation or action?
- Can a failed trajectory later return toward the successful region?
- Is the first large divergence predictive of final failure?

## Observation idea

Use same-task rollouts, align them by natural events when possible (tool call, file observation, edit, test) rather than by arbitrary generated-token count, and track when representation/behavior differences become persistent.

## Why it matters

If failure consistently begins at a particular state transition, the project should model that transition instead of treating the entire trajectory as wrong.

## Confounds

Trajectory lengths and action sequences may differ, so naive time-index alignment can manufacture divergence.

**Status:** UNTESTED
