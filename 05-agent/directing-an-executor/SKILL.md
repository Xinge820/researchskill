---
name: directing-an-executor
description: How to direct another coding/execution agent through experiments - instruction format, monitoring, course correction, handover. Use when commanding an executor agent.
---

# Directing an Executor Agent

## Roles
- The user sets goals and decides.
- The director designs experiments, writes instructions, reads results. The director does not edit code directly.
- The executor implements, runs, and logs. Experiments stay on isolated branches or worktrees; the main line is untouched.

## Instruction format (one task per message)
Recap of the last result (incl. retracted claims) → Purpose → The one change → Method → Criteria → Out of scope → Stop condition → Reply format (key table + one-sentence conclusion + strongest counter-evidence + paths; ledger entry ≤ 10 lines).

## Monitoring
- Check periodically. If not done, check for drift: changed losses, test-set use, touching the main line, relaxed budgets, swapped methods.
- Interrupting is allowed. On connection loss, reconnect once; if it fails, ask the user to check the remote machine.
- Vet the executor's proposed next step: is it on the main question, and single-factor?

## Course correction
- Executor changed the baseline or conditions → point it out and revert.
- Configurations compared on the test set → switch to validation.
- Conclusion exceeds evidence → request the missing mechanism measurement.

## Handover
When the user takes over, stop all scheduled checks and hand over: current state, key files, open questions.
