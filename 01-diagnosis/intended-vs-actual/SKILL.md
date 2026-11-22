---
name: intended-vs-actual
description: Separate what an objective asks the model's outputs to do from what a parameter update actually does, to locate whether a failure is in the loss, the optimizer, or the parameterization.
---

# Intended vs Actual

## Frame
- **Intended change** in function space: Δz = −η ∇_z L (as if the outputs z were a free table).
- **Plain gradient step**: Δθ = Jᵀ Δz, giving actual Δz ≈ K Δz with K = J Jᵀ (the tangent kernel). K amplifies strong modes and starves weak ones.
- **Gauss-Newton step**: Δθ = Jᵀ (K + λI)⁻¹ Δz = (JᵀJ + λI)⁻¹ Jᵀ Δz (push-through identity), which realizes the intended change where the model can move.

## Frozen one-step comparison
From the same checkpoint, batch, and request norm:

| Arm | Answers |
|---|---|
| Ideal function step (edit z directly) | Is the requested direction itself useful? |
| Optimizer step(s): Adam, momentum-free, SGD | Does the update rule redirect the request? |
| Full Gauss-Newton (diagnostic only) | Can the parameterization deliver it at all? |
| Structured write (e.g. a layer the output is linear in) | Is there a cheap executable path? |

## Reading
- Function step works, Gauss-Newton works, optimizer step does not → **update-rule problem**.
- Gauss-Newton also fails → **null space of shared parameters**.
- Works only on the data used to estimate the statistics, not on held-out data → **estimation noise**.
- Function step fails → **the objective itself**.

## Pitfalls
- Measure at the right time: the decisive dynamics may happen early in training.
- Global low-rank curvature approximations can miss batch-specific requests when the curvature spectrum has a heavy tail; check how much request energy falls outside the kept subspace before trusting one.
- Use realistic step sizes in one-step probes; very large steps create artifacts that look like conflicts.
