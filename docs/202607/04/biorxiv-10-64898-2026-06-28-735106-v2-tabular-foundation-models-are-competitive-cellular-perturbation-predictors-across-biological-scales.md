---
title: Tabular Foundation Models Are Competitive Cellular Perturbation Predictors Across Biological Scales
title_zh: 表格基础模型是跨生物学尺度的竞争性细胞扰动预测器
authors: "Palla, G., Hillsley, A., Kim, Y.-J., Royer, L. A."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.735106v2.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 评估表格基础模型用于细胞扰动预测，与大规模基因组模型和基因组机器学习相关
tldr: 预测细胞对遗传和化学扰动的响应是药物发现和功能基因组学的核心挑战。本研究比较了通用表格基础模型（如TabICL、TabPFN）与多个领域特异性架构（如scGPT、PRESAGE等）在四个互补评估场景中的表现。结果显示，在细胞级跨细胞类型预测、伪批量扰动预测、全基因组CRISPR筛选及胚胎发育扰动预测中，表格基础模型与专门模型相当或更优，表明通用上下文学习是细胞扰动预测的强有力且可扩展的替代方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 评估通用表格基础模型是否在细胞扰动预测任务中优于或匹敌领域特异性模型。
method: 在细胞级、伪批量、全基因组CRISPR及胚胎发育层面，对比TabICL、TabPFN与PRESAGE、scGPT等模型。
result: 表格基础模型在大部分任务中与专门模型性能相当或更优，跨数据集和指标表现一致。
conclusion: 通用表格上下文学习可替代专用生物架构，用于多尺度细胞扰动响应建模。
---

## 摘要
预测细胞如何响应遗传和化学扰动是药物发现和功能基因组学中的一个核心挑战。为了解决这个问题，已经开发了一个日益壮大的专门化单细胞基础模型生态系统，然而它们相对于领域无关方法的实际优势仍不清楚。在这里，我们评估了表格基础模型（如TabICL和TabPFN，通用预训练回归模型）与领域特定架构（包括PRESAGE、scGPT、scLAMBDA、STACK和Prophet）在四个互补评估设置中的表现：细胞水平的上下文内跨细胞类型预测、基于五个Perturb-seq细胞系数据集的伪批量扰动预测、原代人CD4+ T细胞的全基因组CRISPR筛选，以及斑马鱼发育扰动图谱中的胚胎水平细胞类型组成预测。在细胞水平的跨细胞类型扰动预测中，表格基础模型的表现与专门化模型相当或更好。在伪批量扰动预测中，表格基础模型在多个评估指标和数据集上持续优于专门化基线。在全胚胎细胞类型组成预测中，表格基础模型与专门化基线具有竞争力。这些结果表明，通用的表格上下文学习为跨细胞系统和尺度的扰动响应建模提供了一种强大且可扩展的替代方案，替代了定制化的生物学架构。

## Abstract
Predicting how cells respond to genetic and chemical perturbations is a central challenge in drug discovery and functional genomics. A growing ecosystem of specialized single-cell foundation models has been developed to address this problem, yet their practical advantage over domain-agnostic approaches remains unclear. Here we evaluate the power of Tabular Foundation Models such as TabICL and TabPFN, general-purpose pre-trained regression models, against domain-specific architectures including PRESAGE, scGPT, scLAMBDA, STACK and Prophet across four complementary evaluation settings: cell-level in-context cross-cell-type prediction, pseudobulk perturbation prediction on five Perturb-seq datasets of cell-lines, a genome-wide CRISPR screen in primary human CD4+ T cells, and embryo-level cell-type composition prediction in a zebrafish developmental perturbation atlas. In the cell-level cross-cell type perturbation prediction, Tabular Foundation Models perform on par or better than specialized models. On pseudobulk perturbation prediction, Tabular Foundation Models consistently outperform specialized baselines across multiple evaluation metrics and datasets. On whole-emrbryo cell-type composition prediction, Tabular Foundation Models are competitive with specialized baselines. These results demonstrate that general-purpose tabular in-context learning provides a strong and scalable alternative to bespoke biological architectures for perturbation response modeling across cell systems and scales.