---
name: literature-survey
description: 用户说"调研"时使用：查文献、提炼与我们问题的对应关系，不擅自做设计。
---

# 调研

## 规则
- 用户说"调研"= 做文献研究，不是给设计方案。
- 优先近三年、高质量来源（顶会/期刊/arXiv 原文、官方代码页）；引用要可点开。
- 读不到全文（限流等）要说明以哪部分为准。

## 输出结构
1. 一句话结论：文献里有没有、主流怎么做。
2. 按"做法类别"列：原理一句、关键公式、成本、来源。
3. **映射到我们的模型**：对应哪一处、范式差在哪（例：SADL 的 BN 投影头 ↔ 我们的查询读出）。
4. 文献帮不上的地方：需要我们自己实验确认的点。
5. 建议顺序（标明是建议，等用户定）。

## 已调研过的主题（避免重复）
- JEPA 防坍塌：LeJEPA/SIGReg、VISReg、SADL（供需、BN 盲区）、Drive vs Decay（早期稳定性、ResidualPred）、早期坍塌期
- 初始化：LSUV（数据驱动单位方差）
- 线性注意力尺度：DeltaNet（q/k L2、输出归一化）、RetNet GroupNorm、TransNormer
- 二阶优化：GN/自然梯度、ViViT 低秩 GGN、Woodbury/ENGD、FNGD、K-FAC/Shampoo、谱偏置与预条件
