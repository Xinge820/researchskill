---
name: research-style
description: Core research principles - first principles, adversarial self-review, no patches, one change at a time, stay on the main question. Read before any research discussion, experiment, or method design.
---

# Research Style

## How to think
1. **Work inside an analyzable frame.** Prefer setups you can reason about: linearizations, closed forms, one-step updates, simple dynamical models.
2. **First principles.** Find the mechanism, not the symptom. Ask what a quantity *means* before optimizing it.
3. **Borrow across fields.** Look for the same problem elsewhere (control, signal processing, statistics, optimization) and compare solutions before picking one.
4. **Assume your best idea is wrong.** Argue as the strongest opponent; look for counterexamples and edge cases, then re-evaluate (see `strongest-opponent-review`).
5. **When stuck, reread the log.** Review the experiment ledger systematically and turn repeated mistakes into rules (`LESSONS.md`).
6. **Stay on the question.** Do not stop early, spawn new questions, or drift before the current one is answered.

## Hard rules
1. **No patches.** Not allowed: post-hoc rescaling or calibration; unprincipled thresholds, floors, or epsilons added to pass a bar; stop-gradient, gradient projection, or clipping used to hide a side effect; a new loss term added to cancel another term's side effect without fixing the cause.
2. **Diagnose before designing.** If the cause is unknown, only measure.
3. **One factor at a time.** Every candidate differs from a fixed, named baseline in exactly one way.
4. **Define the goal by what matters, not by a proxy.** If a proxy (e.g. "closer to a reference distribution") moves the wrong way relative to the real goal, the proxy loses.
5. **Report mechanism metrics and end-task metrics separately.** Neither alone proves the other.
6. **Verify mechanism claims by measurement.** "The loss pushes X" must be checked by measuring what one update actually changed (see `intended-vs-actual`).
7. **Held-out selection only.** Choose configurations, checkpoints, and early stopping on validation data. Read the test set only for the final report.
8. **Respect the compute budget.** State the per-step cost relative to baseline; relax it only with explicit approval.

## Self-discipline
- Match the strength of a claim to the strength of the evidence.
- When evidence refutes a claim, say so plainly and retract it.
- Do not replace "find the cause" with "try another form". If a symptom survives two formulations, investigate the mechanism.
- If you changed a condition the user specified, say so immediately and revert.
