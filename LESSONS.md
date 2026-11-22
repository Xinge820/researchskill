# Lessons (symptom → root cause → rule)

General failure patterns. Append new ones; promote to a skill when a pattern recurs.

| # | Symptom | Root cause | Rule |
|---|---|---|---|
| 1 | A regularizer looks right but weak directions never grow | The update rule (via the tangent kernel) redirects the request to strong directions | Measure intended vs actual before redesigning the loss |
| 2 | A "shape" metric looks good while the scale is near zero | The term was not exactly scale-invariant (e.g. an epsilon); shape at near-zero scale is meaningless | Make shape terms exactly scale-invariant; distrust shape metrics at tiny scale |
| 3 | A per-coordinate variance constraint is satisfied, yet the representation is low-rank | Coordinates can be satisfied by rotation | Define scale and shape in rotation-invariant terms |
| 4 | Concentration happens within the first few training steps | Tiny initial scale + multiplicative growth: strong directions win early | Start at the right scale (data-dependent initialization) |
| 5 | Recurrent memory produces spikes on rare inputs after re-scaling | Read/write loop gain > 1 | Check the loop gain; keep state updates contractive |
| 6 | The target representation shrinks; the model barely beats a zero predictor | A prediction loss through the target can be lowered by shrinking the target | Normalize by the target's centered variance |
| 7 | After making the loss scale-invariant, the scale drifts freely | Scale became an unconstrained direction | Guard scale with a separate centered-energy term |
| 8 | Forcing uniformity widens weak directions but hurts decoding | The data cannot support that many directions; the model fills them with noise | Goal is anti-collapse, not uniformity |
| 9 | After adding a per-sample normalization layer, samples converge | Mean-inclusive scales are satisfied by identical outputs; the anti-collapse term was removed at the same time | Normalization ≠ anti-collapse; compute statistics on centered data |
| 10 | A Lagrange-multiplier constraint keeps pushing after the target is met | The multiplier accumulates stale error | Be careful with accumulating multipliers; closer to target is not automatically better |
| 11 | A cheap low-rank second-order approximation keeps only part of the gain | Heavy-tailed curvature and batch-specific requests | Measure request energy outside the kept subspace first |
| 12 | Two variants seem to conflict in a one-step probe | The probe step was unrealistically large | Use realistic step sizes |
| 13 | Reruns of the same config disagree | Nondeterminism + discrete early stopping | Measure the noise floor; decide with multiple seeds |
| 14 | Configurations compared on the test set | Selection rule violated | Select on validation only |
| 15 | The executor changed the baseline | The instruction did not pin it | Name the baseline in every instruction; revert deviations |
| 16 | The selected checkpoint is the most collapsed one | The selection metric included the shared mean | Select on the end-task validation metric |
