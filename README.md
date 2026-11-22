# researchskill

Research principles for AI research assistants, written as skills. Each skill is one transferable principle - how to think, diagnose, experiment, design, collaborate, and communicate - not knowledge about any specific problem or project.

## Skills

| Category | Skill | Principle in one line |
|---|---|---|
| 00 Overview | [research-style](00-overview/research-style/SKILL.md) | The short list every task starts from |
| 01 Thinking | [first-principles](01-thinking/first-principles/SKILL.md) | Explain by mechanism, inside a frame you can analyze |
| 01 Thinking | [strongest-opponent](01-thinking/strongest-opponent/SKILL.md) | Assume you are wrong and try hard to prove it |
| 01 Thinking | [cross-domain-transfer](01-thinking/cross-domain-transfer/SKILL.md) | Find the same problem in another field before inventing |
| 02 Diagnosis | [diagnose-before-fix](02-diagnosis/diagnose-before-fix/SKILL.md) | Locate where and when it breaks; check what you asked vs. what happened |
| 02 Diagnosis | [metric-validity](02-diagnosis/metric-validity/SKILL.md) | A metric is only as good as what it can and cannot see |
| 03 Experiment | [controlled-experiment](03-experiment/controlled-experiment/SKILL.md) | One change, pre-registered criteria, known noise, held-out decisions |
| 04 Design | [fix-the-cause](04-design/fix-the-cause/SKILL.md) | No patches; one component, one job |
| 05 Workflow | [literature-survey](05-workflow/literature-survey/SKILL.md) | Survey means survey, mapped back to our problem |
| 05 Workflow | [directing-an-executor](05-workflow/directing-an-executor/SKILL.md) | Direct another agent with tight, single-task instructions |
| 06 Communication | [plain-talk](06-communication/plain-talk/SKILL.md) | Conclusion first, grouped points, details on demand |
| 06 Communication | [proposal-writing](06-communication/proposal-writing/SKILL.md) | Significance → problems → evidence-backed related work |
| — | [LESSONS.md](LESSONS.md) | Recurring failure patterns, phrased as general rules |

## Install

**Claude Code** (all projects):
```bash
git clone https://github.com/Xinge820/researchskill ~/researchskill
mkdir -p ~/.claude/skills
for d in ~/researchskill/*/*/; do ln -sfn "$d" ~/.claude/skills/$(basename "$d"); done
```
`git pull` updates every skill. Invoke with `/<skill-name>`, or let the assistant choose by `description`.

**Other agents** (e.g. reading `AGENTS.md`): reference a file, e.g. "Follow researchskill/06-communication/plain-talk/SKILL.md when answering."

## Maintenance rules

- Only universal principles. No project names, datasets, numbers, paths, machines, or personal details; no problem-specific recipes.
- A new lesson goes to `LESSONS.md` first (symptom → root cause → rule, phrased generally). Promote it into a skill when it recurs.
- One skill, one principle. The `description` says *when* to apply it.
