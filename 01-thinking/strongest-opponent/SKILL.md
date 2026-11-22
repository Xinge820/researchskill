---
name: strongest-opponent
description: Before accepting a conclusion or method, argue as its strongest opponent and look for counterexamples, confounds, and shortcuts. Use after every result and before adopting any proposal.
---

# Strongest Opponent

## Principle
Assume your current best explanation is wrong. Try to break it with the strongest evidence, counterexample, or edge case you can find. Keep it only if it survives.

## Questions to ask every time
1. **Confounds** - do the compared arms differ in more than the one intended way?
2. **Shortcuts** - could the system have improved the metric by a cheap route that defeats the purpose?
3. **Same ruler** - are the compared numbers measured the same way? Did a ratio move because of its numerator or its denominator?
4. **Generalization** - does it hold on separate held-out data, or only on the data used to compute it?
5. **Noise** - is the effect larger than run-to-run variation?
6. **Validity** - can this measurement even distinguish the hypotheses in question?

## Build counterexamples deliberately
Construct two situations that look identical to your metric but differ in what you care about. If you can, the metric alone cannot support the conclusion.

## Output
"Strongest counter-evidence: … If it holds, the conclusion becomes …; the experiment that separates the two is …"
