---
name: metric-validity
description: Check what a metric can and cannot see, close its loopholes, and keep all compared quantities on one consistent ruler. Use when choosing, reading, or optimizing any metric, loss, or selection criterion.
---

# Metric Validity

## Principle
A metric is a proxy. Anything optimized against it will find its blind spots. Know them before trusting the number.

## Checks
1. **State what it measures**, in one sentence, in terms of the real goal.
2. **Find the loophole.** What is the cheapest way to make this number look good while defeating the goal? If one exists, assume the system will find it.
3. **Find the blind spot.** Which changes leave the metric unchanged? Things outside its view are uncontrolled.
4. **One ruler.** Every compared or combined quantity should use the same population, the same reference point, and the same normalization. Inventory them from the actual implementation, not from memory.
5. **Separate jobs.** A quantity that keeps numbers well-behaved is not the same as one that judges quality. Do not let one stand in for the other.
6. **Selection is a metric too.** The rule that picks the final model or checkpoint biases results exactly like a training objective; check it the same way.
7. **Prefer what you care about.** When possible, judge on the end goal measured on held-out data; keep proxies for monitoring and diagnosis.

## Red flags
- The proxy improves while the end goal gets worse.
- A ratio improves because its denominator shrank.
- Two metrics labelled the same thing are computed differently.
