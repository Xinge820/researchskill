---
name: metric-ruler-audit
description: List and unify every normalization, denominator, and pooling scope ("one ruler"), and find blind spots created by mean-inclusive or learnable scales. Use when scales are confusing or a change has a counterintuitive effect.
---

# Metric Ruler Audit

## Step 1: Inventory (from the code, not from memory)
For every place that touches "scale", record: location, formula, statistical scope (per sample / per pool / across batches), whether the mean is removed, whether a learnable gain is involved.
**Include the validation/selection metric.** It biases which checkpoint you keep just like a training loss biases training.

## Step 2: Classify
- **Numerical** (input standardization, vector normalization, per-sample norm layers): keep values well-conditioned. They must not be used to judge collapse or quality.
- **Statistical** (loss denominators, regularizers, monitoring metrics, selection metrics): must all use the *same* ruler.

## Step 3: Define one ruler
Pick the population that the question is about, remove nuisance means at the right level (e.g. subtract each group's own mean before pooling when group identity is not what you want to measure), then compute every statistical quantity on that same centered pool.

## Blind-spot rules
- A scale that **includes the shared mean** can be satisfied by mapping every sample to the same vector. It silently rewards collapse.
- Any downstream mean removal or normalization creates directions upstream that receive zero gradient.
- A **learnable gain** can inflate absolute magnitudes and bypass an absolute-value constraint. Use a ratio, or remove the gain.
- Normalization and anti-collapse are **different jobs**. Never remove an anti-collapse term while adding a normalization layer.
- Prefer per-sample normalization over batch statistics when train and test distributions drift.

## Step 4: Switch one place at a time
Move one quantity onto the shared ruler per experiment and judge on validation data. Suggested order: selection metric → loss denominator → distribution regularizer → energy/scale term.
