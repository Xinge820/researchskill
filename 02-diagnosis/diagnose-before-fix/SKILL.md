---
name: diagnose-before-fix
description: When something does not work, measure before changing anything - locate where and when it breaks, and compare what was asked for with what actually happened. Use whenever a method underperforms or behaves unexpectedly.
---

# Diagnose Before Fix

## Principle
If you do not know the cause, only measure. A change made before the cause is known is a guess, and a guess that seems to work is worse than one that fails.

## Locate it
1. **Where** - which component or stage first shows the problem? Measure along the pipeline, not only at the end.
2. **When** - at which point in the process does it appear? Early events often decide the outcome.
3. **For whom** - does it affect all cases, or a subgroup that a pooled number hides?

## Intended vs. actual
A design states what it *asks* the system to do. Measure separately:
- the **ideal** effect (apply the request directly, as if it were free to happen),
- the **actual** effect of one real step,
- an **upper bound** (the best the system could possibly do).

Ideal works but actual does not → the execution path is at fault. Upper bound also fails → the system cannot represent it. Ideal fails → the request itself is wrong.

## Discipline
- One measurement answers one question; state the question first.
- Measure at realistic settings; extreme probes create artifacts.
- Write the diagnosis down before proposing a fix.
