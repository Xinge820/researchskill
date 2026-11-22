---
name: single-factor-protocol
description: Pre-registration, single-factor check, noise floor, decision criteria, and stop conditions for controlled experiments. Use before designing, dispatching, or reading any experiment.
---

# Single-Factor Protocol

## Before running (pre-register)
1. **Purpose** - one question only.
2. **The one change** - relative to which baseline, at which code location. The baseline is fixed and named; never swap it silently.
3. **Criteria** - write down in advance what result supports or refutes the hypothesis, with numeric thresholds.
4. **Out of scope** - what must not change (losses, data, test access, main branch).
5. **Stop condition** - which result means "stop and report" instead of improvising.
6. **Cost** - per-step time relative to baseline.

## Noise floor
- Nondeterministic kernels and discrete early-stopping choices make reruns of the same config differ.
- Measure it first: repeat the same config 3-5 times and across seeds; record the standard deviation per metric.
- Count an improvement only if it exceeds roughly 2σ or holds consistently across paired seeds.
- Use deterministic mode only to prove two implementations are bit-identical.

## Reading results
- Select on validation; read test only for the final report.
- Run a frozen one-step probe before a full training run.
- Keep one-step probes at realistic step sizes.

## Logging
- One ledger entry per experiment, ≤ 10 lines: change, key table, one-sentence conclusion, strongest counter-evidence, result path.
- Mark retracted conclusions explicitly in the ledger.
