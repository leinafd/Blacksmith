# Project Blacksmith Baseline

## Overview

This document is the written baseline for Task LTF-001.  
It records the actual starting state of the repository and the single problem this sprint is allowed to solve.

## Starting State

The repository is empty.

There is no application code, no configuration, no tests, and no existing pipeline.  
The original plan assumed there would be code to work against. That assumption is false.  
This sprint therefore begins from a blank repository and must establish the baseline itself.

## Founding Failure (the only problem in scope)

Two components can each pass their own checks while producing outputs that are mutually incompatible.  
Tests assert against a mock of a contract that nobody has agreed on, so they are incapable of failing when the real contracts diverge.

This sprint exists to make that class of failure visible and preventable.

## Scope Decision

In scope for this sprint:
- A written baseline that correctly describes the empty starting state
- Naming the founding failure above so later work can be checked against it
- An explicit deferred list (see below)

Out of scope:
- Any implementation, configuration files, or environment setup
- Building the gate, the contract, the generator, or the checker
- Anything not required to make the scope decision itself clear and enforceable

## Deferred List

These problems are deliberately postponed. Each has a reason:

- More than two pipeline roles → The founding failure can be demonstrated with two components. Extra roles add noise before the core problem is solved.
- Retry and self-healing → Not useful until the system can detect the failure mode in the first place.
- Evaluating or tuning model quality → Orthogonal to proving that incompatible outputs can be caught.
- Persistence, deployment, and any operational surface → Premature until the gate works on a single run.
- Robustness beyond proving the gate works → Scope expands only after the primary failure mode is under control.

This list is amendable. If a robustness case appears mid-sprint that cannot be ignored, it is added here with a reason instead of being built.

## How to use this document

Any later deliverable in this sprint can be judged with one question:  
Does it serve the founding failure named above, or does it belong on the deferred list?

If the answer is not obvious from this document alone, the baseline has failed.
