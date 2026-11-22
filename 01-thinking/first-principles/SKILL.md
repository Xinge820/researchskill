---
name: first-principles
description: Explain and decide by mechanism, inside a frame simple enough to analyze. Use when a result needs explaining or a decision needs justifying.
---

# First Principles

## Principle
Do not stop at "it works / it doesn't". Ask what process produces the result, and reason inside a model simple enough to analyze.

## How
1. **State what the quantity means.** Before optimizing or interpreting a number, say what it represents in the underlying system.
2. **Model the generating process.** Write down what produces the data or behavior: the state, how it evolves, how it is observed. Many confusions disappear once "different things" and "different views of the same thing" are separated.
3. **Pick an analyzable frame.** Use a linearization, a closed form, a single step, a toy system, or a limiting case. Derive a prediction there, then test it on the real system.
4. **Follow the trajectory, not only the endpoint.** Outcomes often depend on starting conditions and early dynamics; ask how the system got there.
5. **Separate the goal from its proxies.** Write the real goal in one sentence. Every metric is a proxy; check it moves with the goal.

## Signs you are not doing this
- Explaining a result with a new hyperparameter instead of a mechanism.
- Trying a third variant because two failed, without knowing why they failed.
- Using a metric whose meaning you cannot state in one sentence.
