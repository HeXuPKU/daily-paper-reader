---
title: Coordinate- and Sequence-Based Features for a new Combined Annotation-Dependent Depletion Framework of Structural Variants (CADD-SV v2.0)
title_zh: 基于坐标和序列特征的结构变异联合注释依赖性缺失框架（CADD-SV v2.0）
authors: "Catona, O., Kircher, M."
date: 2026-07-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.08.736040v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 用功能注解对结构变异有害性打分的机器学习框架
tldr: 结构变异的精准功能解释是基因组医学的重要挑战，现有方法存在局限性。CADD-SV v2.0基于统一随机森林框架，整合人类与非人灵长类有害/中性变异，融合坐标注释与深度学习序列特征（SegmentNT）。统一模型在缺失、插入、重复和倒位的有害性预测上全面超越前版和其他工具，新增支持多种SV类型。该框架为全基因组结构变异优先级排序提供了更准确高效的解决方案，助力疾病相关SV的发现。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-736040-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1665, \"height\": 937, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-736040-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1706, \"height\": 828, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-736040-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1788, \"height\": 998, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-736040-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1705, \"height\": 800, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-08-736040-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1710, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-08-736040-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1713, \"height\": 488, \"label\": \"Table\"}]"
motivation: 现有结构变异功能预测工具性能有限，缺乏统一跨类型评估框架。
method: 构建集成坐标注释与SegmentNT序列特征的随机森林模型，训练数据涵盖多物种。
result: "CADD-SV v2.0在多种SV类型上AUC提升5-10%，优于现有工具。"
conclusion: 融合序列与坐标特征可显著提升结构变异有害性预测，支持全基因组分析。
---

## 摘要
结构变异是基因组变异的主要来源，并通过多种机制影响人类疾病和进化，但其功能解读仍然具有挑战性。我们提出CADD-SV v2.0，这是一个改进的机器学习框架，用于评估结构变异的有害性，该框架是对原始CADD-SV实现的扩展。该版本引入了一个统一的随机森林模型，该模型在从人类和非人灵长类基因组中提取的扩展代理中性和代理有害变异集上进行训练。该模型整合了更新的基因组注释，包括约束指标、调控元件和染色质结构特征。它基于一个单一的评分框架对缺失、插入、重复和倒位进行评分，该框架同时使用变异及其侧翼区域。为了补充这一框架，我们还探索了基于SegmentNT的序列注释，SegmentNT是一种深度学习模型，可从DNA序列中提供核苷酸分辨率的功能预测。我们的分析评估了序列衍生的功能信号是否能提供额外的信息用于结构变异优先级排序，以及是否可以使用仅包含这些特征或与先前基于坐标的注释相结合的额外模型。CADD-SV v2.0在主要结构变异类型（包括一些以前不支持的类型）中有害变异优先级排序方面优于其先前版本和其他工具，并显著改进了计算流程，提高了全基因组结构变异解读的预测能力。

## Abstract
Structural variants are a major source of genomic variation and contribute to human disease and evolution through diverse mechanisms, yet their functional interpretation remains challenging. We present CADD-SV v2.0, an improved machine learning framework for scoring SV deleteriousness that expands on the original CADD-SV implementation. This version introduces a unified Random Forest model trained on an expanded set of proxy-neutral and proxy-deleterious variants drawn from human and non-human primate genomes. The model integrates updated genomic annotations, including constraint metrics, regulatory elements, and chromatin architecture features. It scores Deletions, Insertions, Duplications and Inversions based on a single scoring framework that uses both the variant and its flanking regions. To complement this framework, we also explore sequence-based annotations derived from SegmentNT, a deep learning model that provides functional predictions from DNA sequence at nucleotide resolution. Our analysis evaluated whether sequence-derived functional signals can provide additional information for SV prioritization and whether additional models with these features alone or in combination with previous coordinate-based annotations can be used. CADD-SV v2.0 outperforms its previous version and other tools in prioritizing deleterious variants across major SV types, including some previously unsupported, and substantially improves the computational workflow, increasing predictive power for genome-wide SV interpretation.