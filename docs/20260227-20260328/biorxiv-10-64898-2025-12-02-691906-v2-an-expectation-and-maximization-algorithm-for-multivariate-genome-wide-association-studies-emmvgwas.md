---
title: An Expectation and Maximization Algorithm for Multivariate Genome-wide Association Studies (EMmvGWAS)
title_zh: 一种用于多变量全基因组关联分析的期望最大化算法 (EMmvGWAS)
authors: "Teng, C.-S., Wang, X., Liu, C., Wang, Q., Cui, Y., Xu, S."
date: 2026-03-14
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.02.691906v2.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 用于多变量全基因组关联分析的 EM 算法
tldr: 本研究开发了EMmvGWAS，一种针对多性状全基因组关联分析（GWAS）的高效计算框架。该方法利用期望最大化（EM）算法估计协方差矩阵，并通过固定协方差比例的半精确方法实现标记效应的闭式解，在显著降低计算成本的同时保持了检测多效性效应的统计效力，特别适用于中等规模性状的联合分析。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-02-691906-v2/fig-001.webp\", \"caption\": \"Figure 1. Computational runtime of EMmvGWAS and GEMMA across datasets and trait dimensions. 438\", \"page\": 13, \"index\": 1, \"width\": 1054, \"height\": 396}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-02-691906-v2/fig-002.webp\", \"caption\": \"Figures 436\", \"page\": 13, \"index\": 2, \"width\": 976, \"height\": 428}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-02-691906-v2/fig-003.webp\", \"caption\": \"Figure 4. QQ plots for null simulations in the mouse and the rice data. 455\", \"page\": 15, \"index\": 3, \"width\": 1033, \"height\": 587}]"
motivation: 传统多性状GWAS在处理高维多基因协方差结构和全基因组扫描时面临巨大的计算压力。
method: 利用EM算法估计遗传与环境协方差矩阵，并采用半精确方法在扫描过程中通过闭式解快速计算标记效应。
result: 在水稻、小鼠和人类数据集上的仿真与实证分析表明，该方法在不损失统计效力的前提下大幅提升了计算效率。
conclusion: EMmvGWAS为多性状遗传关联研究提供了一个高效、可扩展的工具，有助于揭示复杂性状间的共享遗传机制。
---

## 摘要
全基因组关联分析 (GWAS) 通常一次只关注一个数量性状，即使在收集了多个性状的情况下也是如此。然而，通过利用性状间的相关性，多个性状的联合分析可以提高检测遗传关联的统计效能。多变量 GWAS 对于识别多效性效应和揭示复杂性状背后的共享遗传架构尤为重要。尽管具有巨大潜力，但由于多基因协方差结构的高维性以及扫描全基因组标记的成本，多变量 GWAS 方法面临着严峻的计算挑战。我们提出了 EMmvGWAS，这是一个以 R 语言实现的高效计算框架，它显著缩短了涉及中等数量性状的多变量 GWAS 的计算时间。该算法利用期望最大化 (EM) 算法从纯多基因模型中估计遗传和环境协方差矩阵。为了提高全基因组扫描期间的计算效率，我们采用了一种半精确方法，该方法固定估计的协方差矩阵，并将其比率（定义为遗传协方差矩阵与环境协方差矩阵之逆的乘积）视为所有标记的已知常数。这种方法实现了每个位点标记效应的闭式解，在不损失统计效能的情况下大幅缩短了计算时间。我们通过模拟研究以及来自水稻、小鼠和人类群体的真实数据集分析，证明了该方法的可扩展性和性能。该方法在 R 中实现，旨在支持涉及中等数量性状的多变量 GWAS，同时也将单变量分析作为特例涵盖在内。该 R 软件包可在 https://github.com/Jason-Teng/EMmvGWAS 获取。

## Abstract
Genome-wide association studies (GWAS) commonly focus on one quantitative trait at a time, even when multiple traits are collected. However, joint analysis of multiple traits can increase the power to detect genetic associations by leveraging trait correlations. Multivariate GWAS is particularly important for identifying pleiotropic effects and uncovering shared genetic architecture underlying complex traits. Despite its great potential, multivariate GWAS methods face substantial computational challenges due to the high dimensionality of polygenic covariance structures and the cost of scanning genome-wide markers. We present EMmvGWAS, an efficient computational framework implemented as an R, which dramatically reduces computation time for multivariate GWAS involving a moderate number of traits. The algorithm estimates the genetic and environmental covariance matrices from a pure polygenic model using an Expectation-Maximization (EM) algorithm. To improve computational efficiency during genome-wide scanning, we use a semi-exact method that fixes the estimated covariance matrices and treats their ratio, defined as the genetic covariance matrix multiplied by the inverse of the environmental covariance matrix, as a known constant across all markers. This approach enables closed-form solutions for marker effects at each locus, dramatically reducing the computation time without compromising statistical power. We demonstrate the scalability and performance of our method through both simulation studies and real dataset analyses from rice, mouse and human populations. The method is implemented in R and is designed to support multivariate GWAS involving a moderate number of traits, while also accommodating univariate analyses as a special case. The R package is available at https://github.com/Jason-Teng/EMmvGWAS.