---
title: "There and back again: a multi-omics tale of thyroid co-expression network rewiring"
title_zh: 去而复返：甲状腺共表达网络重连的多组学故事
authors: "Pozhidaeva, M., Bussmann, H., Huisinga, M., Buesen, R., Hackermüller, J., Canzler, S."
date: 2026-05-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.21.726849v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 多组学共表达网络框架，可应用于GWAS功能整合
tldr: 多组学数据整合分析在揭示复杂生物系统调控机制方面潜力巨大，但面临分析挑战。本文提出一套基于WGCNA的最佳实践框架，通过样本级拼接多组学数据构建共表达网络，并引入基于置换检验的差异连接性分析（DiffK）。在甲状腺毒性大鼠模型中，该方法识别出超过4400个显著重连的分子特征，其中多数表达水平稳定但网络关系改变。研究表明，集成多组学网络分析能够捕获传统差异表达分析遗漏的系统级动态调控重连。
source: biorxiv
selection_source: fresh_fetch
motivation: 多组学数据整合面临挑战，现有方法难以有效捕捉跨层次分子相互作用的动态重连。
method: 提出样本级拼接多组学WGCNA框架，结合置换检验的差异连接性分析（DiffK）进行统计推断。
result: 在PTU诱导的甲状腺毒性模型中鉴定出超4400个显著重连特征，多数表达稳定但网络关系改变。
conclusion: 集成多组学网络分析可揭示传统方法无法发现的动态系统调控变化。
---

## 摘要
多组学数据的整合为复杂生物系统提供了前所未有的洞察，但也带来了显著的分析挑战。在本研究中，我们提出了一个最佳实践框架，用于从转录组学、蛋白质组学和代谢组学数据构建同步加权基因共表达网络（WGCNA）。使用丙基硫氧嘧啶（PTU）诱导的甲状腺毒性啮齿动物模型，我们分析了来自对照组、处理组和恢复组的甲状腺组织。我们证明，在样本水平上串联单独处理的组学层次——无需额外缩放——保留了有意义的关联结构，并反映了构建生物学可解释网络的最佳实践。为每组构建了共表达网络，揭示了处理下分子相互作用的广泛破坏以及恢复期间的部分修复。我们强调了两种分析策略的互补优势：模块保留分析识别出被破坏的共调控结构，而差异连接性分析则检测特征级别的重连事件。作为方法学进展，我们引入了一种基于置换的方法来计算差异连接性（DiffK）的特征特异性p值，从而实现稳健的统计推断。该策略揭示了超过4400个显著重连的特征，其中许多显示出稳定的表达，这突显了基于网络分析的附加价值。我们的发现证明了整合多组学WGCNA和差异网络分析在捕捉动态、系统范围的调控变化方面的实用性。

## Abstract
The integration of multi-omics data offers unprecedented insight into complex biological systems but presents significant analytical challenges. In this study, we propose a best-practice framework for constructing simultaneous weighted gene co-expression networks (WGCNA) from transcriptomics, proteomics, and metabolomics data. Using a rodent model of thyroid toxicity induced by propylthiouracil (PTU), we analyzed thyroid tissues from control, treated, and recovery groups. We demonstrate that concatenating individually processed omics layers at the sample level--without additional scaling--preserves meaningful correlation structures and reflects best practices for biologically interpretable network construction. Co-expression networks were constructed for each group, revealing extensive disruption of molecular interactions under treatment and partial restoration during recovery. We highlight the complementary strengths of two analytical strategies: module preservation analysis identifies disrupted co-regulatory structures, while differential connectivity analysis detects feature-level rewiring events. As a methodological advance, we introduce a permutation-based approach for calculating feature-specific p-values for differential connectivity (DiffK), enabling robust statistical inference. This strategy uncovered over 4,400 significantly rewired features, many of which showed stable expression, underscoring the added value of network-based analyses. Our findings demonstrate the utility of integrated multi-omics WGCNA and differential network analysis in capturing dynamic, system-wide regulatory changes.