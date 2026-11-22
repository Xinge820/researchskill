---
name: first-principles-design
description: Design losses, regularizers, optimizers, initializations, or architecture changes from the system's dynamics and geometry rather than trial and error. Use when proposing or discussing a new method.
---

# First-Principles Design

## Model the system first
- Write down what generates the data (e.g. a latent state with dynamics, observed through several channels) and what the representation is supposed to estimate.
- Ask which samples are genuinely different states and which are different *views of the same state*. Spread the former; align the latter only on what both views can observe.
- If the state evolves over time, the natural spread of the representation is set by the dynamics. Forcing a fixed covariance changes the dynamics; constraining the *innovation* (what the past cannot predict) is often the right object. Check innovations for autocorrelation to tell real novelty from structure a simple model missed.

## Think in geometry
- Training amplifies and deforms the **initial geometry**. If the starting scale is near zero, growth is multiplicative and strong directions win early. Fix the starting point (data-dependent initialization) rather than repairing later.
- Collapse = the embedding loses injectivity. Shape and uniformity are references, not goals.

## Design checklist
1. Under which transformations is the term invariant? Can rotation, translation, or scaling fool it?
2. Is its gradient bounded and non-zero near the degenerate point it should escape?
3. Does any downstream normalization create a blind spot for it?
4. Are the scale part and the shape part orthogonal (scale term along the output, scale-invariant shape term orthogonal to it)?
5. Can the requested change be executed by the parameterization (see `intended-vs-actual`)?
6. Is the cost within budget?
7. Does it fix a cause, or cancel a side effect (a patch)?

## Reusable patterns
- Normalize a prediction loss by the target's **centered** variance to close the "shrink the target" shortcut; guard scale with a separate centered-energy term.
- Define scale and shape in rotation-invariant (spectral) terms; prefer shape terms whose gradient on weak directions stays bounded.
- Do not force uniformity on directions the data cannot support; it fills them with uninformative variance.
- Per-direction (whitened) normalization amplifies noise and unpredictable directions; first check those directions are predictable.
