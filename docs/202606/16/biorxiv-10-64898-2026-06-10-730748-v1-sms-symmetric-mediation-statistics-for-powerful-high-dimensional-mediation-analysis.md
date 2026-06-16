---
title: "SMS: Symmetric Mediation Statistics for Powerful High-Dimensional Mediation Analysis"
title_zh: SMS：用于高效高维中介分析的对称中介统计量
authors: "Wang, Y., Yan, S., Wang, H.-J., Hu, Y.-J."
date: 2026-06-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.730748v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 适用于组学的高维中介分析新统计方法
tldr: 高维中介分析面临复合零假设检验和功效不足的挑战，尤其当暴露-中介与中介-结局的统计显著性不平衡时。本文提出SMS框架，利用对称性校准复合零分布以控制FDR，并允许灵活组合关联p值（如最大值）构建Omnibus检验，还可直接使用效应量。模拟和实际代谢组、甲基化数据表明，SMS在控制FDR的同时，灵敏度显著高于HDMT等现有方法（提升约20个百分点），并发现了被遗漏的潜在中介。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有高维中介分析方法在复合零假设检验和功效方面存在缺陷，尤其是当暴露-中介与中介-结局的关联显著性差异巨大时，FDR控制不稳定且功效有限。
method: 提出对称中介统计量SMS，通过对称性校准复合零分布，灵活组合关联p值（如取最大值）构建Omnibus检验，并允许直接使用效应量估计。
result: 模拟中SMS稳定控制FDR，灵敏度比HDMT、DACT等方法提升约20个百分点；实际代谢组和DNA甲基化数据中发现多个被现有方法遗漏的潜在中介。
conclusion: SMS为高维中介分析提供了更强的FDR控制和更高的统计功效，适用于组学数据中中介发现的场景。
---

## 摘要
背景：高维特征（特别是分子水平的组学特征）的中介分析为揭示人类健康和疾病背后的生物学机制提供了重要机会。然而，两个核心统计挑战仍然存在：检验复合零假设以及当暴露-中介和中介-结局关联在统计显著性上差异较大时保持检验功效。现有方法通常依赖于对三种零假设比例的准确估计或对两个关联p值的最大值，在FDR控制上可能不总是理想，且在非平衡显著性下功效有限。方法：我们提出SMS，一种基于对称中介统计量的新统计框架。通过利用对称性，SMS将复合零分布作为一个整体进行校准以控制FDR。它还允许灵活组合两个关联p值（包括最大值），从而能够构建综合检验。此外，它允许直接使用效应量估计，从而避免计算p值。结果：在广泛的模拟场景中，SMS控制了FDR，同时实现了显著的灵敏度提升，通常比现有方法（包括HDMT、DACT和DEI-B）高出约20个百分点。应用于代谢组学数据集和DNA甲基化数据集进一步证实了这些发现。值得注意的是，SMS在代谢组学数据集中发现了五个可能的介导因子，而这些因子被所有考虑的现有方法遗漏。

## Abstract
Background: Mediation analysis of high-dimensional features, particularly molecular-level omics features, provides important opportunities to uncover biological mechanisms underlying human health and disease. However, two central statistical challenges remain: testing the composite-null hypothesis and maintaining power when the exposure-mediator and mediator-outcome associations differ substantially in statistical significance. Existing methods typically rely on accurate estimation of the proportions of the three null types or on the maximum of the two association p-values, and may not always control the FDR well and may have limited power under imbalanced significance. Methods: We propose SMS, a new statistical framework based on symmetric mediation statistics. By exploiting symmetry, SMS calibrates the composite null distribution as a whole for FDR control. It also allows flexible combinations of the two association p-values, including the maximum, and then enables construction of an omnibus test. Moreover, it permits direct use of effect-size estimates, bypassing the need to compute p-values. Results: SMS controlled the FDR across a wide range of simulation scenarios while achieving a substantial sensitivity gain, often around 20 percentage points, over existing methods including HDMT, DACT, and DEI-B. Applications to a metabolomics dataset and a DNA methylation dataset further corroborated these findings. Notably, SMS discovered five plausible mediators in the metabolomics dataset that were missed by all existing methods considered.