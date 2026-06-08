---
title: "inGSEA: An Improved Method for Gene Set Enrichment Analysis Using a Weighted Integral Statistic"
title_zh: inGSEA：使用加权积分统计量的基因集富集分析改进方法
authors: "Zhang, Q., Li, Q."
date: 2026-06-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.729106v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 改进的基因集富集分析方法，可用于GWAS下游功能解读
tldr: 标准GSEA在处理异质性或非协调表达模式时统计效力有限。inGSEA引入Anderson-Darling加权积分统计量作为新的富集分数，并通过Cauchy组合积分与经典最大统计量增强对不同表达模式的鲁棒性。模拟和真实数据研究表明，inGSEA在保持错误发现率校正的同时，检测稀疏和双向信号的效力显著优于标准GSEA。通过广义伽马分布近似零分布，inGSEA降低了置换检验的计算成本，并提供了便捷的web工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有GSEA方法在检测异质性或非协调表达模式的通路时统计效力不足。
method: inGSEA采用Anderson-Darling加权积分统计量计算富集分数，并通过Cauchy组合增强对不同表达模式的鲁棒性。
result: 模拟和真实数据表明，inGSEA在保持错误发现率的同时，检测稀疏和双向信号的效力优于标准GSEA。
conclusion: inGSEA通过改进统计量和零分布近似，提供了更强大且计算高效的基因集富集分析工具。
---

## 摘要
基因集富集分析（GSEA）是转录组分析中最常用的方法之一，但当生物通路呈现出异质性或非一致表达模式时，其统计功效有限。我们提出了一种改进的GSEA方法——基于积分的GSEA（inGSEA）。inGSEA引入了一种基于安德森-达林加权积分统计量的新型富集分数。该新富集分数增强了对复杂信号（特别是稀疏和双向信号）的检测能力，同时采用积分与经典最大统计量的柯西组合提供了针对不同表达模式的鲁棒性。广泛的数值研究表明，inGSEA具有优越的功效和良好校准的假阳性控制。应用于真实世界数据集，揭示了标准GSEA遗漏的生物学相关通路。inGSEA通过使用广义伽马分布近似零分布，减少了置换检验的计算负担。inGSEA可作为用户友好的基于网络的软件工具使用（https://amss-stat.github.io/inGSEA）。

## Abstract
Gene Set Enrichment Analysis (GSEA) is one of the most popular methods for transcriptomic analysis, yet its statistical power is limited when the biological pathways exhibit heterogeneous or non-concordant expression patterns. We propose an improved GSEA method, \textbf{in}tegral-based GSEA (inGSEA). inGSEA introduces a novel enrichment score based on the Anderson-Darling weighted integral statistic. The new enrichment score enhances detection power for complex signals, particularly sparse and bidirectional ones, while the Cauchy combination of integral and classic maximum statistics provides robustness across diverse expression patterns. Extensive numerical studies demonstrate that inGSEA achieves superior power and well-calibrated false discoveries. Application to real-world datasets reveals biologically relevant pathways missed by the standard GSEA. inGSEA reduces the computational burden of permutation testing by employing a generalized gamma distribution to approximate the null distribution. inGSEA is accessible as a user-friendly web-based software tool (https://amss-stat.github.io/inGSEA).