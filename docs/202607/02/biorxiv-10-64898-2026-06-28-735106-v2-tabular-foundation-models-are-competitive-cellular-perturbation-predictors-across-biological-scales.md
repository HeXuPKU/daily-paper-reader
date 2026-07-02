---
title: Tabular Foundation Models Are Competitive Cellular Perturbation Predictors Across Biological Scales
title_zh: 表格基础模型在跨生物尺度的细胞扰动预测中具有竞争力
authors: "Palla, G., Hillsley, A., Kim, Y.-J., Royer, L. A."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.735106v2.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 评估表格基础模型用于细胞扰动预测，与医疗AI中的虚拟细胞模型生成和大型基因组模型相关。
tldr: 预测细胞对扰动的反应是药物发现的核心挑战。评估了通用表格基础模型（如TabICL、TabPFN）与领域专用模型在多种扰动预测任务上的性能。结果表明表格基础模型在多个任务上与专用模型相当或更优，尤其在伪批量预测中一致领先。证明了通用表格上下文学习可作为可扩展的替代方案，适用于跨细胞系统和尺度的扰动建模。
source: biorxiv
selection_source: fresh_fetch
motivation: 探索通用表格基础模型在细胞扰动预测任务中是否优于领域专用模型及其实际优势。
method: 在细胞级跨细胞类型预测、伪批量预测、全基因组CRISPR筛选和胚胎级组成预测四种设置中，比较表格基础模型与专用架构的性能。
result: 表格基础模型在多个任务中表现与专用模型相当或更好，尤其伪批量预测中一致优于专用基线。
conclusion: 通用表格上下文学习为扰动响应建模提供强大且可扩展的替代方案，可跨细胞系统和尺度应用。
---

## 摘要
预测细胞如何响应遗传和化学扰动是药物发现和功能基因组学中的核心挑战。针对这一问题，已有越来越多的专用单细胞基础模型被开发出来，但相对于非领域特定方法，它们的实际优势尚不明确。本文评估了TabICL和TabPFN等表格基础模型（通用预训练回归模型）与包括PRESAGE、scGPT、scLAMBDA、STACK和Prophet在内的领域特定架构在四个互补评估设置中的表现：细胞层面的上下文中跨细胞类型预测、基于五个细胞系Perturb-seq数据集的伪批量扰动预测、原代人CD4+ T细胞的全基因组CRISPR筛选，以及斑马鱼发育扰动图谱中的胚胎水平细胞类型组成预测。在细胞层面的跨细胞类型扰动预测中，表格基础模型的表现与专用模型相当或更优。在伪批量扰动预测中，表格基础模型在多个评估指标和数据集上持续优于专用基线模型。在全胚胎细胞类型组成预测中，表格基础模型与专用基线模型具有竞争力。这些结果表明，通用表格上下文学习为跨细胞系统和尺度的扰动响应建模提供了一种强大且可扩展的替代方案，可替代定制化的生物学架构。

## Abstract
Predicting how cells respond to genetic and chemical perturbations is a central challenge in drug discovery and functional genomics. A growing ecosystem of specialized single-cell foundation models has been developed to address this problem, yet their practical advantage over domain-agnostic approaches remains unclear. Here we evaluate the power of Tabular Foundation Models such as TabICL and TabPFN, general-purpose pre-trained regression models, against domain-specific architectures including PRESAGE, scGPT, scLAMBDA, STACK and Prophet across four complementary evaluation settings: cell-level in-context cross-cell-type prediction, pseudobulk perturbation prediction on five Perturb-seq datasets of cell-lines, a genome-wide CRISPR screen in primary human CD4+ T cells, and embryo-level cell-type composition prediction in a zebrafish developmental perturbation atlas. In the cell-level cross-cell type perturbation prediction, Tabular Foundation Models perform on par or better than specialized models. On pseudobulk perturbation prediction, Tabular Foundation Models consistently outperform specialized baselines across multiple evaluation metrics and datasets. On whole-emrbryo cell-type composition prediction, Tabular Foundation Models are competitive with specialized baselines. These results demonstrate that general-purpose tabular in-context learning provides a strong and scalable alternative to bespoke biological architectures for perturbation response modeling across cell systems and scales.