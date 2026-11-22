# Lessons (symptom → root cause → rule)

Recurring failure patterns, phrased generally. Append new ones; promote to a skill when a pattern recurs.

| # | Symptom | Root cause | Rule |
|---|---|---|---|
| 1 | A design looks right on paper but has no effect | What it asks for is not what the execution path delivers | Measure intended vs. actual before redesigning |
| 2 | A metric looks great in a degenerate state | The metric is undefined or meaningless near that state | Check metrics at the extremes before trusting them |
| 3 | A constraint is satisfied but the goal is not met | The constraint can be met by a transformation the goal does not care about | Ask what transformations leave the constraint unchanged |
| 4 | The outcome is decided very early | Starting conditions plus self-reinforcing dynamics | Look at the start of the process, not only the end |
| 5 | A proxy keeps improving while the end goal worsens | The proxy has a loophole | Find the cheapest way to game a metric before optimizing it |
| 6 | Fixing one loophole opens a drift elsewhere | The removed pressure was also holding something else in place | After a fix, check what is now unconstrained |
| 7 | Forcing an ideal shape makes results worse | Demanding more than the data supports fills the gap with noise | Set goals by what matters, not by an idealized reference |
| 8 | Replacing one component breaks something unrelated | Two jobs were coupled; the replacement dropped one | One component, one job; never remove a job by accident |
| 9 | An adaptive correction keeps pushing after the target is met | It accumulates stale history | Check whether feedback reflects the current state |
| 10 | A cheap approximation keeps only part of the benefit | It discards what the problem actually needs | Measure what the approximation drops before adopting it |
| 11 | Two options seem to conflict | The probe was run at an extreme setting | Probe at realistic settings |
| 12 | Repeated runs disagree | Hidden nondeterminism and discrete choices | Measure the noise floor; decide with repeats |
| 13 | A decision was made on the test set | Selection discipline slipped | Decide on validation only |
| 14 | An executor quietly changed the setup | The instruction did not pin it | Pin baselines and conditions in every instruction |
| 15 | The "best" selected result is the worst in reality | The selection rule shares the metric's loophole | Select on the end goal measured on held-out data |
