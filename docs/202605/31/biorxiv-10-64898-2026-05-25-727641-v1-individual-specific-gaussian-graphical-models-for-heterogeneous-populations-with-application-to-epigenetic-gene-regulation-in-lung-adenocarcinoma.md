---
title: Individual-Specific Gaussian Graphical Models for Heterogeneous Populations with Application to Epigenetic Gene Regulation in Lung Adenocarcinoma
title_zh: 面向异质性群体的个体特异性高斯图模型及其在肺腺癌表观遗传基因调控中的应用
authors: "Saha, E."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.25.727641v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 个体特异性网络方法用于多组学与遗传整合
tldr: SIREN针对精准肿瘤学中患者间分子异质性挑战，提出一种估计每个样本部分相关网络的方法。它结合群体经验贝叶斯先验与秩1个体更新，无需MCMC。模拟显示优于OAS、Ledoit-Wolf等群体平均方法；在肺腺癌数据中识别出个体特异性基因-甲基化调控边，实现生存分层。该方法可扩展，揭示了染色质重塑和WNT信号通路的表观遗传异质性。
source: biorxiv
selection_source: fresh_fetch
motivation: 患者间分子异质性导致群体平均网络无法揭示个体差异，需要个体特异性网络推断方法。
method: SIREN利用经验贝叶斯先验对每个样本的精度矩阵进行秩1更新，得到闭合形式的个体后验。
result: 模拟中边恢复优于OAS、Ledoit-Wolf等；在肺腺癌中识别出分层生存的个体特异性调控边。
conclusion: SIREN可扩展，适用于异质性群体，揭示了表观遗传异质性中的关键通路。
---

## 摘要
患者间分子异质性是精准肿瘤学中的基本挑战：群体水平的多组学网络揭示了跨群体聚合的平均生物学特征，但却掩盖了驱动不同临床结果的个体变异。我们提出SIREN（通过正则化经验贝叶斯网络进行样本特异性推断）方法，该方法通过结合群体水平经验贝叶斯先验与秩1个体特异性更新，为每个样本跨组学层估计一个偏相关网络。由于无法从单个观测中估计样本特异性精度矩阵，SIREN使用共轭逆Wishart先验，其均值为Oracle近似收缩估计量，从而无需MCMC即可得到闭式个体特异性后验。在模拟的异质性群体中，SIREN在边恢复方面优于包括OAS、Ledoit-Wolf和图Lasso在内的群体平均方法，同时在同质性环境中保持竞争力。应用于肺腺癌的配对转录组和甲基化组谱时，SIREN识别出个体特异性基因-甲基化调控边，这些边能够以群体水平分析无法做到的方式根据生存对患者进行分层，暗示染色质重塑和WNT信号通路在表观遗传异质性中的作用。SIREN计算可扩展，并作为Python包提供。

## Abstract
Inter-patient molecular heterogeneity is a fundamental challenge in precision oncology: population-level multi-omics networks reveal average biology aggregated across the population but obscure individual variations that drive differential clinical outcomes. We introduce SIREN (Sample-specific Inference via Regularized Empirical-Bayes Networks), a method that estimates one partial correlation network per sample across omics layers by combining a population-level empirical Bayes prior with a rank-1 individual-specific update. Since a sample-specific precision matrix cannot be estimated from a single observation, SIREN uses a conjugate Inverse Wishart prior whose mean is the Oracle Approximating Shrinkage estimator, yielding closed-form individual-specific posteriors without MCMC. On simulated heterogeneous populations, SIREN achieves superior edge recovery over population-average methods including OAS, Ledoit-Wolf, and graphical Lasso, while remaining competitive in homogeneous settings. Applied to paired transcriptomic and methylomic profiles from lung adenocarcinoma, SIREN identifies individual-specific gene-methylation regulatory edges that stratify patients by survival in ways population-level analysis cannot, implicating chromatin remodeling and WNT signaling pathways in epigenetic heterogeneity. SIREN is computationally scalable and available as a Python package.