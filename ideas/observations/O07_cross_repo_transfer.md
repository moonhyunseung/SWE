# O07 — Cross-Repository Transfer

## Intuition

Same-task geometry can be real yet useless for generalization. The eventual object must survive repository change.

## Core question

After defining a credible common representation, can a correction learned or estimated on repository A remain meaningful on unseen repository B?

## Holdout ladder

- unseen tasks in seen repositories;
- unseen repositories;
- unseen project structures/frameworks;
- eventually unseen languages if the representation permits it.

## Measurements

Prefer structural/behavioral alignment and corrective utility over raw vector cosine unless the representation guarantees comparable coordinates.

## Failure interpretation

If performance disappears under repository holdout, the mechanism may encode repository identity or literal coordinates rather than transferable software-solving structure.

## Role

This is a late validation question, not an initial implementation gate.

**Status:** FUTURE
