---
name: fix-the-cause
description: Design changes that remove causes instead of masking symptoms - no patches, one component per job, check what each change is blind to. Use when proposing or reviewing any fix or new method.
---

# Fix the Cause

## Principle
A fix should remove the mechanism that produces the problem. If it only offsets the symptom, the problem returns elsewhere.

## What counts as a patch (do not use)
- Post-hoc rescaling or calibration outside the method.
- Constants, thresholds, or floors chosen to pass a bar, with no principled origin.
- Blocking or clipping a signal to hide its side effect.
- Adding a new term whose only role is to cancel another term's side effect.

## Design checks
1. **Which cause does it remove?** Name it, with the diagnosis that found it.
2. **One component, one job.** If a component is asked to do two jobs, or one job is split across several, expect conflicts.
3. **What is it blind to?** List the changes it cannot see or control; something else must cover them.
4. **Can it be fooled?** Look for the cheapest way to satisfy it without achieving the goal.
5. **Does it act where the problem starts?** Acting downstream of the cause usually means compensating, not fixing.
6. **Can the system actually execute it?** A correct request that cannot be carried out is still a failure.
7. **Is it within budget?**

## Also
- Starting conditions matter: fixing the starting point can be cleaner than repairing later.
- Do not ask for more than the data or system can support; forcing it fills the gap with noise.
