---
title: "Integrative Transfer Network: Deep Transfer Learning Across Populations and Prediction Targets"
title_zh: 整合迁移网络：跨人群与预测目标的深度迁移学习
authors: "Gao, Y., Cui, Y."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.731936v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 跨群体和跨目标的深度迁移学习，可用于多基因风险评分计算
tldr: 大规模临床和生物医学数据常含多样亚组属性与多预测目标，现有方法独立处理亚组差异或多任务预测。本文提出Integrative Transfer Network (ITN)，一种深度神经网络，通过共享表示和亚组特定模块同时跨亚组和多个相关结果迁移学习。在分类与时间事件任务中，ITN一致提升亚组特定预测性能。ITN为从异质数据中学习亚组特定洞察提供了统一框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法未能联合利用跨亚组和多目标信息，导致亚组预测性能受限。
method: ITN采用共享层捕获全局特征，并设计亚组特定分支与目标特定输出，实现跨亚组和结果的知识迁移。
result: 在分类和时间事件任务中，ITN相比基线方法显著提升亚组预测准确性和一致性。
conclusion: ITN是处理异质数据集中亚组差异与多目标预测的统一有效框架。
---

## 摘要
大规模的临床和生物医学数据集日益包含多样的子组属性（例如，人口统计学或临床子组）和多个预测目标。尽管各种机器学习方法可以处理子组差异或多目标预测，但它们通常独立而非联合地考虑这些方面。为了更有效地捕获这些复杂数据集中的共享信息和子组特定信息，我们提出了整合迁移网络（ITN），这是一种深度神经网络，旨在同时利用跨子组和多个相关结果的数据。在广泛的实验中，包括常见人口统计子组和多个疾病终点的生存时间分析和分类任务，ITN通过从其他子组和结果中借用强度，展示了子组特定预测的一致改进。我们认为ITN是一个统一的框架，用于从子组特定见解至关重要的异构数据集中学习。

## Abstract
Large-scale clinical and biomedical datasets increasingly contain both diverse subgroup attributes (e.g., demographic or clinical subgroups) and multiple prediction targets. Although various machine learning approaches can address subgroup differences or multi-target prediction, they often consider these aspects independently rather than jointly. To more effectively capture the shared and subgroup-specific information in such complex datasets, we propose the Integrative Transfer Network (ITN), a deep neural network designed to leverage data across subgroups and multiple related outcomes simultaneously. In extensive experiments, including time-to-event and classification tasks where demographic subgroups and multiple disease end-points are prevalent, ITN demonstrates consistent improvements in subgroup-specific prediction by borrowing strength from other subgroups and outcomes. We envision ITN as a unified frame-work for learning from heterogeneous datasets where subgroup-specific insights are critical.