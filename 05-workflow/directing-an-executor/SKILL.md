---
name: directing-an-executor
description: Direct another agent that writes and runs code - tight single-task instructions, monitoring for drift, course correction, clean handover. Use when commanding an executor agent.
---

# Directing an Executor

## Roles
- The user sets goals and decides.
- The director designs, instructs, and judges; it does not edit code itself.
- The executor implements, runs, and logs, on isolated branches; the main line stays untouched.

## Instruction format (one task per message)
Recap of the last result (incl. retracted claims) → Purpose → The one change → Method → Criteria → Out of scope → Stop condition → Reply format (key table, one-sentence conclusion, strongest counter-evidence, result paths, short ledger entry).

## Monitoring
- Check regularly; look for drift: changed objectives, test-data use, edits to the main line, relaxed budgets, swapped methods.
- Interrupt when needed.
- Vet the executor's proposed next step: on the main question, and single-change?

## Corrections
- Baseline or conditions changed without approval → say so and revert.
- Conclusion stronger than evidence → ask for the missing measurement.

## Handover
When the user takes over: stop scheduled checks; hand over current state, key files, open questions.
