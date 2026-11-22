# researchskill

个人研究风格的 Skill 仓库。每个 Skill 是一个文件夹，里面一个 `SKILL.md`，按用途分类。
内容来自真实研究过程（JEPA 时序表征 / 防坍塌正则 / 指挥执行 Agent），踩过的坑都沉淀成规则。

## 目录

| 类别 | Skill | 什么时候用 |
|---|---|---|
| 00 原则 | [research-style](00-principles/research-style/SKILL.md) | 任何研究任务开始前，先读 |
| 01 诊断 | [collapse-geometry-diagnosis](01-diagnosis/collapse-geometry-diagnosis/SKILL.md) | 怀疑表征坍塌、要判断"有没有丢信息" |
| 01 诊断 | [request-vs-realized](01-diagnosis/request-vs-realized/SKILL.md) | 损失"想要"的变化和训练"实际"的变化对不上 |
| 01 诊断 | [statistics-ruler-audit](01-diagnosis/statistics-ruler-audit/SKILL.md) | 归一化、分母、池化口径混乱时 |
| 02 实验 | [single-factor-protocol](02-experiment/single-factor-protocol/SKILL.md) | 设计、预注册、判读任何对照实验 |
| 02 实验 | [strongest-opponent-review](02-experiment/strongest-opponent-review/SKILL.md) | 得出结论之前做反证 |
| 03 方法 | [first-principles-method-design](03-method/first-principles-method-design/SKILL.md) | 设计新的正则 / 优化器 / 结构 |
| 04 调研 | [literature-survey](04-survey/literature-survey/SKILL.md) | 用户说"调研" |
| 05 协作 | [command-execution-agent](05-agent/command-execution-agent/SKILL.md) | 指挥 Codex 等执行 Agent |
| 06 写作 | [thesis-proposal-writing](06-writing/thesis-proposal-writing/SKILL.md) | 开题报告 / 研究现状类写作 |
| 06 写作 | [plain-reporting](06-writing/plain-reporting/SKILL.md) | 给用户汇报结果 |
| 坑 | [PITFALLS.md](PITFALLS.md) | 踩过的坑与对应规则，持续追加 |

## 维护约定

- 新坑先写进 `PITFALLS.md`（现象 → 根因 → 规则），同类坑出现两次再提炼进对应 Skill。
- 每个 Skill 只管一件事；`description` 写清"什么时候用"。
- 改动走分支 + PR，提交信息写清改了哪条规则、依据是哪次实验。
