---
name: representation-collapse-check
description: Decide whether a learned representation has collapsed, i.e. distinct inputs became indistinguishable or recoverable information was lost. Use for self-supervised or predictive representation learning.
---

# Representation Collapse Check

## Definition
Collapse = **distinct inputs map to indistinguishable representations** (the embedding folds), or **information the input carried can no longer be read out**.
A concentrated spectrum is *not* collapse by itself: real data often lives on a low-dimensional manifold.

## Report on the same held-out set and the same ruler (see `metric-ruler-audit`)
| Metric | Meaning | Collapse signal |
|---|---|---|
| Shared-mean energy / total energy | Can samples still be told apart? | → 100% |
| Centered energy (absolute) | How far apart samples are | → 0 |
| Fixed-dimension held-out decoding (choose directions on train, test on held-out) | What information survived | Far below an upper bound |
| Upper bound: decode from the raw input | Reference | — |
| End-task metric on validation | Final acceptance | Loses to trivial baselines |
| Spectrum (top-k share, effective rank) | Reference only | Not an acceptance criterion |

## Notes
- Energy and shape cannot tell signal from noise: two representations with identical spectra can carry new information or pure noise.
- Information need not live in the highest-variance directions; compare variance-selected vs decoding-selected directions.
- Split by group (e.g. by channel, subject, or source): pooled spread can hide collapse inside each group.
- Track over training (start, early, mid) to locate *when* collapse happens before asking *which term* drives it.
- Small absolute error is not success; always compare against trivial baselines (zero / mean / persistence).
