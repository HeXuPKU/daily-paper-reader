---
title: Tabular Foundation Models Are Competitive Cellular Perturbation Predictors Across Biological Scales
title_zh: 表格基础模型在跨生物尺度的细胞扰动预测中具有竞争力
authors: "Palla, G., Hillsley, A., Kim, Y.-J., Royer, L. A."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.735106v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 表格基础模型作为机器学习工具应用于基因组扰动预测
tldr: 预测细胞对遗传和化学扰动的响应是药物发现的关键挑战。本研究评估了通用表格基础模型TabICL和TabPFN在四种互补设置中的表现：跨细胞类型预测、五个Perturb-seq细胞系伪bulk预测、原代CD4+T细胞全基因组CRISPR筛选、斑马鱼胚胎细胞类型组成预测。结果表明，表格模型在跨细胞类型预测中与专业模型持平或更优，在伪bulk预测中一致超越所有专业基线，在胚胎预测中具有竞争力。该发现挑战了需要专门生物架构的假设，证明通用表格上下文学习是跨细胞系统尺度的强有力、可扩展替代方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 评估通用表格基础模型在细胞扰动预测中是否优于领域特定模型。
method: 在四种预测任务上对比TabICL、TabPFN与PRESAGE、scGPT等专业模型。
result: 表格模型在跨细胞类型和伪bulk预测中一致更优，全胚胎预测竞争力相当。
conclusion: 通用表格基础模型是细胞扰动预测的强有力且可扩展的替代方案。
---

## 摘要
预测细胞如何响应遗传和化学扰动是药物发现和功能基因组学中的一个核心挑战。为解决这一问题，越来越多的专用单细胞基础模型被开发出来，但相较于与领域无关的方法，它们的实际优势尚不明确。在此，我们评估了TabICL和TabPFN等表格基础模型（通用预训练回归模型）与领域特定架构（包括PRESAGE、scGPT、scLAMBDA、STACK和Prophet）在四个互补评估设置中的能力：细胞层面的上下文内跨细胞类型预测、基于五个细胞系Perturb-seq数据集的伪批量扰动预测、原代人CD4+ T细胞的全基因组CRISPR筛选，以及斑马鱼发育扰动图谱中的胚胎层面细胞类型组成预测。在细胞层面的跨细胞类型扰动预测中，表格基础模型的表现与专用模型相当甚至更优。在伪批量扰动预测中，表格基础模型在多个评估指标和数据集上持续优于专用基线。在胚胎整体细胞类型组成预测中，表格基础模型与专用基线具有竞争力。这些结果表明，通用表格上下文内学习为跨细胞系统和尺度的扰动响应建模提供了一种强大且可扩展的替代方案，取代了定制化的生物架构。

## Abstract
Predicting how cells respond to genetic and chemical perturbations is a central challenge in drug discovery and functional genomics. A growing ecosystem of specialized single-cell foundation models has been developed to address this problem, yet their practical advantage over domain-agnostic approaches remains unclear. Here we evaluate the power of Tabular Foundation Models such as TabICL and TabPFN, general-purpose pre-trained regression models, against domain-specific architectures including PRESAGE, scGPT, scLAMBDA, STACK and Prophet across four complementary evaluation settings: cell-level in-context cross-cell-type prediction, pseudobulk perturbation prediction on five Perturb-seq datasets of cell-lines, a genome-wide CRISPR screen in primary human CD4+ T cells, and embryo-level cell-type composition prediction in a zebrafish developmental perturbation atlas. In the cell-level cross-cell type perturbation prediction, Tabular Foundation Models perform on par or better than specialized models. On pseudobulk perturbation prediction, Tabular Foundation Models consistently outperform specialized baselines across multiple evaluation metrics and datasets. On whole-emrbryo cell-type composition prediction, Tabular Foundation Models are competitive with specialized baselines. These results demonstrate that general-purpose tabular in-context learning provides a strong and scalable alternative to bespoke biological architectures for perturbation response modeling across cell systems and scales.