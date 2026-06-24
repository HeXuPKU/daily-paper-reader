---
title: A tailored variant filtering procedure for multi-breed and multi-species unbalanced animal SNP collections
title_zh: 一种针对多品种和多物种不平衡动物SNP集合的定制化变异过滤方法
authors: "Lazzari, B., Milanesi, M., Talenti, A., Bionda, A., Li, Y., Jiang, L., Lenstra, J. A., Bardou, P., Tosser Klopp, G., Crepaldi, P., Colli, L."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.1101/2025.10.14.682050v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 针对多品种SNP集合的定制化变体过滤程序，是GWAS预处理的关键步骤
tldr: 多品种多物种SNP数据因群体结构差异，标准MAF和LD过滤会引入偏差。本文针对VarGoats山羊基因组计划，提出基于群体内亚抽样、最小等位基因计数和标记间距的过滤方法，从1372个动物的2800万SNP中筛选出750个个体的低于1400万标记数据集，避免了偏差且满足后续分析需求，适用于类似的非平衡多品种数据集。
source: biorxiv
selection_source: fresh_fetch
motivation: 标准MAF和LD过滤在多品种多物种不平衡数据集中因群体结构差异而产生偏差，需要更鲁棒的过滤策略。
method: 采用群体内亚抽样、最小等位基因计数和标记间距作为过滤指标，替代传统MAF和LD过滤。
result: VarGoats山羊基因组计划中1372个动物的2800万SNP被过滤为750个个体的低于1400万标记数据集。
conclusion: 新过滤流程有效避免标准方法偏差，适用于多品种多物种不平衡SNP数据集。
---

## 摘要
技术进步和全基因组测序成本的下降产生了大量重测序数据。现在可以轻松组装包含多个物种和/或种群分子变异的大型数据集。然而，这些数据集在地理来源和样本量方面差异极大，分类群从单一到数百个条目不等。因此，应用标准过滤方法可能会偏向某些群体或基因库的代表性。通常采用的依赖次要等位基因频率（MAF）和连锁不平衡（LD）的变异过滤方法并不合适，因为代表多个种群和物种局部及全局多样性的数据集中存在显著的LD结构和等位基因变异频率差异。因此，利用VarGoats 1000山羊基因组项目，我们设计了一种新方法，通过采用群体内子采样、次要等位基因计数（MAC）和标记间距（bp空间）作为过滤器，避免了标准过滤程序的偏差。从包含1372个动物、超过2800万个SNP的质量过滤数据集中，我们生成了一个包含不到1400万个标记和750个个体的数据集，满足了初始要求并促进了后续计算步骤。

## Abstract
Technological advancements and decreasing costs of whole-genome sequencing have generated a huge amount of resequencing data. Large-sized datasets, encompassing the molecular variation of several species and/or populations can now be assembled easily. However, these are extremely variable in terms of geographical provenance and sample sizes, with taxonomic groups varying from one single to hundreds of entries. Consequently, the application of standard filtering approaches may bias the representation of groups or gene pools. Commonly adopted variant filtering approaches relying on minor allele frequency (MAF) and linkage disequilibrium (LD) are not adequate because of remarkable differences in LD structure and frequency of allele variants within datasets representing both local and global diversity of multiple populations and species. Thus, by using the VarGoats 1000 goat genome project, we devised a novel approach which avoids the biases of the standard filtering procedures by adopting within-population subsampling, minor allele count (MAC) and marker spacing (bp-space) as filters. Starting from a quality-filtered dataset of >28M SNPs from 1372 animals, we generated a dataset of <14M markers and 750 individuals, complying with the initial requirements and facilitating further computational steps.