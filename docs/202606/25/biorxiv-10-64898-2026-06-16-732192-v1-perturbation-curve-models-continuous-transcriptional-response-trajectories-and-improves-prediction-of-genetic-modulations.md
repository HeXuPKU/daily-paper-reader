---
title: Perturbation Curve models continuous transcriptional response trajectories and improves prediction of genetic modulations
title_zh: 扰动曲线模型化连续转录响应轨迹并改进遗传调控预测
authors: "Zhong, Y., wang, l., Yang, G., Yu, L., Qi, X., Jiang, H."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.16.732192v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 建模连续转录响应轨迹以改善遗传调控预测
tldr: 单细胞CRISPR筛选（Perturb-seq）中扰动效果呈连续多样，但传统离散标签无法解耦强度与响应异质性。本文提出PertCurve，一种基于非线性曲线的计算框架，按扰动强度排序细胞并建模转录组响应轨迹。该框架精确还原响应幅度，揭示下游基因的模块化异步行为及比例、敏感、阈值三种原型模式，在病毒、凋亡、增殖等过程中识别普适特征，并发现分化中背景特异性调控。整合PertCurve可提升预测模型性能，为优化现有模型提供可行洞见。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有框架无法有效解耦单细胞CRISPR筛选中扰动强度的连续性与下游响应多样性。
method: 提出PertCurve，基于非线性曲线建模按扰动强度排序细胞的转录组响应轨迹。
result: 精确还原响应幅度，揭示基因行为的模块化异步模式及三种原型，识别普适与背景特异性特征。
conclusion: 整合PertCurve可提升预测模型性能，提供改进现有模型的可行见解。
---

## 摘要
单细胞CRISPR筛选（Perturb-seq）通过揭示生物学因果关系彻底改变了功能基因组学。然而，尽管扰动分配通常被表示为离散标签，但细胞水平的扰动有效强度通常是连续且多样化的。当前的分析框架难以将扰动强度的变异性与下游响应的多样性解耦。本文提出扰动曲线（PerturbCurve），一种基于非线性和曲线的计算框架，通过明确纳入不同的扰动幅度和强度来建模转录组响应的轨迹。通过按扰动强度对细胞排序，我们证明PertCurve能够准确重现响应幅度，并揭示下游基因行为的独特模块化和异步性模式。这些模式可归类为原型，包括比例响应、敏感响应和阈值响应。通过在CRISPRi/a模式上应用该框架，我们识别出病毒感染、凋亡和增殖基因中的通用响应模式，并在细胞分化中揭示了先前被忽视的上下文特异性调控特征。最后，将PertCurve纳入扰动预测模型和评估指标可提升预测性能，为改进现有模型提供可操作的见解。

## Abstract
Single-cell CRISPR screens, Perturb-seq, have revolutionized functional genomics by revealing biological causality. However, although perturbation assignments are typically represented as discrete labels, the cell-level effective strength of perturbations is often continuous and diverse. Current analytical frameworks struggle to decouple the variability in perturbation strength from the diversity of downstream responses. Here, we present Perturbation Curve (PertCurve), a nonlinear, curve-based computational framework that models the trajectories of transcriptomic responses by explicitly incorporating diverse perturbation magnitudes and strengths. By ordering cells by perturbation strength, we demonstrate that PertCurve accurately recapitulates the response magnitudes and reveals the distinct modularity and asynchrony patterns of downstream gene behaviors. These patterns are categorized into archetypes, including proportional, sensitive, and threshold responses. By applying this framework across CRISPRi/a modalities, we identify universal response patterns in viral infection, apoptosis, and proliferation genes, and reveal previously overlooked context-specific regulatory features in cell differentiation. Finally, incorporating PertCurve into perturbation prediction models and evaluation metrics enhances predictive performance, delivering actionable insights for refining established models.