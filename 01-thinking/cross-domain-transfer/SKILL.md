---
name: cross-domain-transfer
description: Before inventing a method, look for the same structural problem in other fields and compare their solutions. Use when facing a new problem or designing a fix.
---

# Cross-Domain Transfer

## Principle
Most problems have a structural twin in another field. Find it, understand why its solution works, and check whether those reasons hold here.

## How
1. **Strip the problem to its structure.** Describe it without domain words: "a quantity that should stay bounded drifts", "an update that favors already-large components", "a measurement blind to a common offset".
2. **Search adjacent fields.** Control and filtering, signal processing, statistics, numerical optimization, physics, economics.
3. **Transfer the reason, not the recipe.** A solution carries over only if the assumptions behind it hold here; list them and check each.
4. **Compare before choosing.** Put 2-3 candidates side by side: principle, cost, assumptions, failure mode.

## Pitfall
A familiar name is not a fit. If the assumptions do not hold, the borrowed method becomes a patch.
