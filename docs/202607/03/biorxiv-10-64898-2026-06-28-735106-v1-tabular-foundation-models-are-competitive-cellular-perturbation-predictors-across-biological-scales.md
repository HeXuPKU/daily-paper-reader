---
title: Tabular Foundation Models Are Competitive Cellular Perturbation Predictors Across Biological Scales
title_zh: 表格基础模型在跨生物尺度的细胞扰动预测中具有竞争力
authors: "Palla, G., Hillsley, A., Kim, Y.-J., Royer, L. A."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.735106v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 评估表格基础模型在跨尺度（包括全基因组）的细胞扰动预测能力
tldr: 预测细胞对遗传和化学扰动的反应是药物发现和功能基因组学的核心挑战。虽然已有多种专用单细胞基础模型，但其相对于通用方法的优势尚不明确。本文评估了表格基础模型（如TabICL和TabPFN）与多个领域专用模型的性能。结果显示，表格基础模型在细胞层面跨细胞类型预测、伪批量扰动预测以及胚胎层面细胞类型组成预测中均具有竞争力甚至更优，表明通用表格上下文学习是扰动反应建模的强有力可扩展替代方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 评估通用表格基础模型与专用单细胞模型在细胞扰动预测中的性能差异。
method: 在细胞层面跨细胞类型预测、伪批量扰动预测、全基因组CRISPR筛选和胚胎发育扰动图谱四种设置下，比较TabICL、TabPFN与PRESAGE、scGPT等专用模型。
result: 表格基础模型在多个评估指标和数据集中一致优于或持平于专用基线模型。
conclusion: 通用表格上下文学习可作为专用生物架构的有力可扩展替代方案，适用于不同细胞系统和尺度。
---

## 摘要
预测细胞如何响应遗传和化学扰动是药物发现和功能基因组学的核心挑战。为解决这一问题，越来越多的专用单细胞基础模型生态系统被开发出来，但它们相对于领域无关方法的实际优势仍不明确。本文评估了表格基础模型（如TabICL和TabPFN，即通用预训练回归模型）与领域特定架构（包括PRESAGE、scGPT、scLAMBDA、STACK和Prophet）在四个互补评估设置中的能力：细胞层面的上下文内跨细胞类型预测、基于五个人类细胞系Perturb-seq数据集的伪批量扰动预测、原代人CD4+ T细胞的全基因组CRISPR筛选，以及斑马鱼发育扰动图谱中的胚胎层面细胞类型组成预测。在细胞层面的跨细胞类型扰动预测中，表格基础模型的表现与专用模型相当甚至更好。在伪批量扰动预测中，表格基础模型在多个评估指标和数据集上持续优于专用基线模型。在胚胎整体细胞类型组成预测中，表格基础模型与专用基线模型具有竞争力。这些结果表明，通用表格上下文内学习为跨细胞系统和尺度的扰动响应建模提供了一种强大且可扩展的替代方案，超越特制的生物架构。

## Abstract
Predicting how cells respond to genetic and chemical perturbations is a central challenge in drug discovery and functional genomics. A growing ecosystem of specialized single-cell foundation models has been developed to address this problem, yet their practical advantage over domain-agnostic approaches remains unclear. Here we evaluate the power of Tabular Foundation Models such as TabICL and TabPFN, general-purpose pre-trained regression models, against domain-specific architectures including PRESAGE, scGPT, scLAMBDA, STACK and Prophet across four complementary evaluation settings: cell-level in-context cross-cell-type prediction, pseudobulk perturbation prediction on five Perturb-seq datasets of cell-lines, a genome-wide CRISPR screen in primary human CD4+ T cells, and embryo-level cell-type composition prediction in a zebrafish developmental perturbation atlas. In the cell-level cross-cell type perturbation prediction, Tabular Foundation Models perform on par or better than specialized models. On pseudobulk perturbation prediction, Tabular Foundation Models consistently outperform specialized baselines across multiple evaluation metrics and datasets. On whole-emrbryo cell-type composition prediction, Tabular Foundation Models are competitive with specialized baselines. These results demonstrate that general-purpose tabular in-context learning provides a strong and scalable alternative to bespoke biological architectures for perturbation response modeling across cell systems and scales.