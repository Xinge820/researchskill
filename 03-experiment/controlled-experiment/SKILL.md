---
name: controlled-experiment
description: Run experiments that can actually answer a question - one change, pre-registered criteria, a known noise floor, held-out decisions, honest logging. Use before designing, dispatching, or reading any experiment.
---

# Controlled Experiment

## Before running
1. **One question.**
2. **One change** relative to a fixed, named baseline. Never swap the baseline silently.
3. **Criteria in advance**: what result supports, what refutes, with thresholds.
4. **Out of scope**: what must not change.
5. **Stop condition**: which outcome means "stop and report".
6. **Cost**: resources relative to the baseline.

## Noise floor
- Repeat the same configuration and vary seeds to learn run-to-run variation first.
- Count an effect only if it clearly exceeds that variation or holds consistently across paired runs.
- A single run with a small difference decides nothing.

## Decisions
- Choose on validation data; read test data only for the final report.
- Prefer a cheap probe (one step, frozen model, small scale) before an expensive full run.

## Logging
- One short ledger entry per experiment: change, key numbers, one-sentence conclusion, strongest counter-evidence, where the results are.
- Mark retracted conclusions explicitly.
