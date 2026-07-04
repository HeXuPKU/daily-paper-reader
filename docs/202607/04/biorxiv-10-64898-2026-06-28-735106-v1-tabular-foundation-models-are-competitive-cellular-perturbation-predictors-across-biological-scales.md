---
title: Tabular Foundation Models Are Competitive Cellular Perturbation Predictors Across Biological Scales
title_zh: 表格基础模型在跨生物学尺度的细胞扰动预测中具有竞争力
authors: "Palla, G., Hillsley, A., Kim, Y.-J., Royer, L. A."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.735106v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 评估表格基础模型在跨生物学尺度（包括全基因组）的细胞扰动预测能力
tldr: 预测细胞对扰动的响应是药物发现和功能基因组学的核心挑战。本文系统比较了通用表格基础模型（TabICL、TabPFN）与多种领域特定模型在四个跨尺度任务上的性能，包括细胞级跨细胞类型预测、伪批量扰动预测、全基因组CRISPR筛选和胚胎级细胞类型组成预测。结果表明，通用模型在大多数任务中表现出与专门化模型相当或更优的性能，且在伪批量预测中持续领先。这证明通用表格上下文学习无需定制生物架构，即可提供可扩展且强大的扰动响应建模方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有专门化单细胞基础模型众多，但通用表格基础模型在扰动预测中的潜力尚未被充分评估。
method: 在四个跨尺度任务（细胞级、伪批量、全基因组CRISPR、胚胎级）上对比通用表格基础模型与专门化模型。
result: 通用表格基础模型在细胞级和伪批量预测中优于或持平专门化模型，在胚胎级预测中具有竞争力。
conclusion: 通用表格上下文学习为扰动响应建模提供了可扩展且强竞争力的替代方案，无需专门生物架构。
---

## 摘要
预测细胞如何响应遗传和化学扰动是药物发现和功能基因组学中的核心挑战。为解决这一问题，出现了日益增长的专业化单细胞基础模型生态系统，然而与领域无关的方法相比，它们的实际优势尚不明确。本文评估了表格基础模型（如TabICL和TabPFN）——通用预训练回归模型——与特定领域架构（包括PRESAGE、scGPT、scLAMBDA、STACK和Prophet）在四个互补评估设置中的能力：细胞层面上下文内跨细胞类型预测、基于五个细胞系Perturb-seq数据集的伪批量扰动预测、原代人CD4+ T细胞的全基因组CRISPR筛选，以及斑马鱼发育扰动图谱中的胚胎层面细胞类型组成预测。在细胞层面跨细胞类型扰动预测中，表格基础模型的表现与专业模型相当或更优。在伪批量扰动预测中，表格基础模型在多个评估指标和数据集上持续优于专业基线。在胚胎整体细胞类型组成预测中，表格基础模型与专业基线具有竞争力。这些结果表明，通用表格上下文学习为跨细胞系统和尺度的扰动响应建模提供了一种强大且可扩展的替代方案，可替代定制化的生物学架构。

## Abstract
Predicting how cells respond to genetic and chemical perturbations is a central challenge in drug discovery and functional genomics. A growing ecosystem of specialized single-cell foundation models has been developed to address this problem, yet their practical advantage over domain-agnostic approaches remains unclear. Here we evaluate the power of Tabular Foundation Models such as TabICL and TabPFN, general-purpose pre-trained regression models, against domain-specific architectures including PRESAGE, scGPT, scLAMBDA, STACK and Prophet across four complementary evaluation settings: cell-level in-context cross-cell-type prediction, pseudobulk perturbation prediction on five Perturb-seq datasets of cell-lines, a genome-wide CRISPR screen in primary human CD4+ T cells, and embryo-level cell-type composition prediction in a zebrafish developmental perturbation atlas. In the cell-level cross-cell type perturbation prediction, Tabular Foundation Models perform on par or better than specialized models. On pseudobulk perturbation prediction, Tabular Foundation Models consistently outperform specialized baselines across multiple evaluation metrics and datasets. On whole-emrbryo cell-type composition prediction, Tabular Foundation Models are competitive with specialized baselines. These results demonstrate that general-purpose tabular in-context learning provides a strong and scalable alternative to bespoke biological architectures for perturbation response modeling across cell systems and scales.