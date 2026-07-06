---
title: Tabular Foundation Models Are Competitive Cellular Perturbation Predictors Across Biological Scales
title_zh: 表格基础模型在多种生物学尺度上成为有竞争力的细胞扰动预测器
authors: "Palla, G., Hillsley, A., Kim, Y.-J., Royer, L. A."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.735106v2.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 表格基础模型用于跨生物尺度的细胞扰动预测
tldr: 预测细胞对遗传化学扰动的响应是药物发现和功能基因组学的核心挑战。本文评估了Tabular Foundation Models（如TabICL、TabPFN）这类通用预训练回归模型，与scGPT、STACK等专用架构在四种场景下的性能：细胞级跨细胞类型预测、五组Perturb-seq伪批量预测、CD4+ T细胞全基因组CRISPR筛选以及斑马鱼胚胎发育扰动细胞类型组成预测。结果显示，通用表模型在多数任务上表现持平或更优，证明了通用上下文学习作为扰动响应建模可扩展替代方案的有效性。
source: biorxiv
selection_source: fresh_fetch
motivation: 评估通用表基模型是否能在细胞扰动预测任务中超越或匹配领域专用模型。
method: 在四种互补评估设置中对比Tabular Foundation Models与专用模型的预测性能。
result: 通用表模型在细胞级和伪批量预测中表现更优，在胚胎级预测中与专用模型竞争力相当。
conclusion: 通用表上下文学习为跨细胞系统和尺度的扰动响应建模提供了强健且可扩展的替代方案。
---

## 摘要
预测细胞如何响应遗传和化学扰动是药物发现和功能基因组学中的一个核心挑战。为了解决这个问题，越来越多专门化的单细胞基础模型被开发出来，然而它们相对于领域无关方法的实际优势仍不清楚。在这里，我们评估了表格基础模型（如TabICL和TabPFN）——通用预训练回归模型——相对于领域特定架构（包括PRESAGE、scGPT、scLAMBDA、STACK和Prophet）在四种互补评估设定中的能力：细胞层面的上下文内跨细胞类型预测、基于五个细胞系Perturb-seq数据集的伪批量扰动预测、原代人CD4+ T细胞的全基因组CRISPR筛选，以及斑马鱼发育扰动图谱中的胚胎水平细胞类型组成预测。在细胞层面的跨细胞类型扰动预测中，表格基础模型的表现与专门模型相当或更优。在伪批量扰动预测中，表格基础模型在多个评估指标和数据集上持续优于专门基线。在整体胚胎细胞类型组成预测中，表格基础模型与专门基线具有竞争力。这些结果表明，通用表格上下文学习为跨细胞系统和尺度的扰动响应建模提供了强大且可扩展的替代方案，以取代定制化的生物学架构。

## Abstract
Predicting how cells respond to genetic and chemical perturbations is a central challenge in drug discovery and functional genomics. A growing ecosystem of specialized single-cell foundation models has been developed to address this problem, yet their practical advantage over domain-agnostic approaches remains unclear. Here we evaluate the power of Tabular Foundation Models such as TabICL and TabPFN, general-purpose pre-trained regression models, against domain-specific architectures including PRESAGE, scGPT, scLAMBDA, STACK and Prophet across four complementary evaluation settings: cell-level in-context cross-cell-type prediction, pseudobulk perturbation prediction on five Perturb-seq datasets of cell-lines, a genome-wide CRISPR screen in primary human CD4+ T cells, and embryo-level cell-type composition prediction in a zebrafish developmental perturbation atlas. In the cell-level cross-cell type perturbation prediction, Tabular Foundation Models perform on par or better than specialized models. On pseudobulk perturbation prediction, Tabular Foundation Models consistently outperform specialized baselines across multiple evaluation metrics and datasets. On whole-emrbryo cell-type composition prediction, Tabular Foundation Models are competitive with specialized baselines. These results demonstrate that general-purpose tabular in-context learning provides a strong and scalable alternative to bespoke biological architectures for perturbation response modeling across cell systems and scales.