---
title: "GR-SAFS: A Graph-Regularized Stacking Framework with Adaptive Feature Selection for High-Dimensional Prognostic Biomarker Discovery"
title_zh: GR-SAFS：一种用于高维预后生物标志物发现的图正则化堆叠框架与自适应特征选择
authors: "He, J., Guan, J."
date: 2026-06-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.23.733986v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 图正则化堆叠框架用于高维转录组生物标志物发现，与整合功能基因组学与GWAS相关
tldr: 高维转录组数据中识别预后生物标志物面临稀疏性、网络拓扑保持和异构模型融合三重挑战。GR-SAFS框架并行运行图拉普拉斯Lasso和随机森林，通过eCDF对齐和多样性惩罚凸二次规划融合输出。在TCGA-LUAD上获得20基因签名，训练C指数0.700，并在两个独立外部队列中唯一保持显著风险分层。该框架开源实现，功能富集锚定Wnt/β-catenin轴，为整合网络先验和非线性信号提供新范式。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法忽略基因网络结构、遗漏非线性交互或缺乏融合异构模型的原则性机制。
method: GR-SAFS并行运行嵌入基因共表达网络Laplacian先验的Graph-Lasso和随机森林，经eCDF对齐后，通过多样性惩罚的凸二次规划路由器融合。
result: 在TCGA-LUAD上训练C指数0.700，20基因签名在独立微阵列队列中唯一保持显著风险分层，富集于Wnt/β-catenin通路。
conclusion: GR-SAFS有效整合网络拓扑先验与互补非线性信号，实现稳健且可复现的高维预后标志物发现。
---

## 摘要
从高维转录组数据中识别预后生物标志物面临三重挑战：实现稀疏性、保留生物网络拓扑结构以及整合互补的非线性信号。现有方法通常忽略网络结构、遗漏非线性交互，或缺乏将异构模型输出融合的原则性机制。我们提出了GR-SAFS（图正则化堆叠与自适应特征选择），该框架包含三个模块：嵌入基因共表达网络拉普拉斯先验的Graph-Lasso引擎，与随机森林引擎并行运行；一个经验累积分布函数（eCDF）对齐层，将稀疏和密集的重要性置于共同的百分位尺度上；以及一个多样性惩罚二次规划路由器，其严格凸性确保了唯一的全局最优解。在TCGA-LUAD队列中，GR-SAFS识别出一个20基因特征，训练一致性指数为0.700。在两个独立的跨平台微阵列队列中，GR-SAFS是唯一一个其冻结特征在每个队列中均能保留显著风险分层的方法，而强C指数基线方法至少在一个外部队列中失去显著性。功能富集将特征锚定于一致的Wnt/β-连环蛋白轴上。我们发布了开源实现以确保完全可重复性。

## Abstract
Identifying prognostic biomarkers from high-dimensional transcriptomic data poses a triple challenge: achieving sparsity, preserving biological network topology, and integrating complementary nonlinear signals. Existing methods typically ignore network structure, miss nonlinear interactions, or lack a principled mechanism to fuse heterogeneous model outputs. We introduce GR-SAFS (Graph-Regularized Stacking with Adaptive Feature Selection), a framework with three modules: a Graph-Lasso engine embedding gene co-expression network Laplacian priors, run in parallel with a Random Forest engine; an empirical cumulative distribution function (eCDF) alignment layer that places sparse and dense importances on a common percentile scale; and a diversity-penalized quadratic programming router whose strict convexity yields a unique global optimum. On the TCGA-LUAD cohort, GR-SAFS identifies a 20-gene signature with a training concordance index of 0.700. Across two independent crossplatform microarray cohorts, GR-SAFS is the only method whose frozen signature retains statistically significant risk stratification in every cohort, where stronger-C-index baselines lose significance on at least one external cohort. Functional enrichment anchors the signature to a coherent Wnt/{beta};-catenin axis. An open-source implementation is released for full reproducibility.