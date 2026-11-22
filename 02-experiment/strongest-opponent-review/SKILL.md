---
name: strongest-opponent-review
description: Before accepting a conclusion or method, argue as its strongest opponent - confounds, shortcuts, mismatched rulers, generalization, noise, metric validity. Use after every result and every new proposal.
---

# Strongest-Opponent Review

## Ask before every conclusion
1. **Confounds** - do the arms differ in more than one way (pool size, step size, initialization, selection rule, test-set peeking)?
2. **Shortcuts** - could the metric improve because the model found a cheap way out (shrinking the target, making samples identical, inflating a gain, rotating to satisfy a per-coordinate constraint)?
3. **Ruler** - are compared quantities on the same ruler? Did a ratio fall because the numerator rose or the denominator fell?
4. **Generalization** - does it hold only on the pool used to compute the statistic, or also on separate held-out data?
5. **Noise** - is the difference larger than the noise floor? How many seeds?
6. **Validity** - can the metric even distinguish the thing we care about?

## Useful counterexample templates
- Same spectrum, different content: one dimension holds new information vs. the same-variance noise.
- A rank-k representation rotated so every coordinate has unit variance.
- Every sample mapped to one nonzero vector, then per-sample normalized.

## Output format
"Strongest counter-evidence: ... If it holds, the conclusion becomes ...; next, distinguish the two with ..."
