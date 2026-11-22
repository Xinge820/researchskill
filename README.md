# researchskill

A personal research-style skill set for AI research assistants. Each skill is a folder with one `SKILL.md`, grouped by purpose. The skills encode *how* to do research, not facts about any particular project.

## Skills

| Category | Skill | Use when |
|---|---|---|
| 00 Principles | [research-style](00-principles/research-style/SKILL.md) | Before any research discussion, experiment, or method design |
| 01 Diagnosis | [intended-vs-actual](01-diagnosis/intended-vs-actual/SKILL.md) | An objective "should" work but training does not do what it asks |
| 01 Diagnosis | [metric-ruler-audit](01-diagnosis/metric-ruler-audit/SKILL.md) | Normalizations, denominators, or pooling scopes are inconsistent or confusing |
| 01 Diagnosis | [representation-collapse-check](01-diagnosis/representation-collapse-check/SKILL.md) | Judging whether a learned representation has collapsed or lost information |
| 02 Experiment | [single-factor-protocol](02-experiment/single-factor-protocol/SKILL.md) | Designing, dispatching, or reading any controlled experiment |
| 02 Experiment | [strongest-opponent-review](02-experiment/strongest-opponent-review/SKILL.md) | Before accepting a conclusion or a proposed method |
| 03 Method | [first-principles-design](03-method/first-principles-design/SKILL.md) | Designing a new loss, regularizer, optimizer, initialization, or architecture change |
| 04 Survey | [literature-survey](04-survey/literature-survey/SKILL.md) | The user asks to "survey" / "research" a topic |
| 05 Agent | [directing-an-executor](05-agent/directing-an-executor/SKILL.md) | Directing another coding/execution agent to run experiments |
| 06 Writing | [plain-talk](06-writing/plain-talk/SKILL.md) | Every answer, report, or explanation |
| 06 Writing | [proposal-writing](06-writing/proposal-writing/SKILL.md) | Writing research significance / problem statement / related work |
| — | [LESSONS.md](LESSONS.md) | General failure patterns turned into rules; append new ones |

## Install

**Claude Code** (all projects):
```bash
git clone https://github.com/Xinge820/researchskill ~/researchskill
mkdir -p ~/.claude/skills
for d in ~/researchskill/*/*/; do ln -sfn "$d" ~/.claude/skills/$(basename "$d"); done
```
`git pull` later updates every skill. Invoke explicitly with `/<skill-name>`, or let the assistant pick skills by their `description`.

**Other agents** (e.g. ones that read `AGENTS.md`): reference the file, e.g. "Follow researchskill/06-writing/plain-talk/SKILL.md when answering."

## Maintenance rules

- Keep skills project-agnostic: no dataset names, numbers, paths, machines, or personal details.
- A new lesson goes to `LESSONS.md` first (symptom → root cause → rule). Promote it into a skill once a similar lesson appears twice.
- One skill, one job. The `description` says *when* to use it.
