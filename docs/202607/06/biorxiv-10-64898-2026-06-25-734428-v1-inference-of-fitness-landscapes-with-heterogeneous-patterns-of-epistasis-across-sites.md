---
title: Inference of fitness landscapes with heterogeneous patterns of epistasis across sites
title_zh: 具有异质性位点间上位性模式的适应度景观推断
authors: "Marti-Gomez, C., McCandlish, D. M."
date: 2026-06-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.25.734428v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 适应度景观统计推断框架涉及上位效应，与GWAS交互效应统计方法相关
tldr: "适应性景观是理解遗传变异如何影响进化结果的关键框架，但复杂的高阶上位性使得其推断充满挑战。本文引入基于平均平方局部k阶上位系数的统计框架，可精确计算或从噪声数据中估计，并用于定义贝叶斯先验以差异化惩罚跨位点相互作用。应用于高通量蛋白质和RNA数据，揭示高度结构化的上位模式。进一步推断含65,536基因型的自剪接内含子景观，详尽解析了主要遗传相互作用与分子机制的联系。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有适应性景观推断方法难以处理异质性上位模式，缺乏对复杂遗传相互作用的系统总结与建模框架。
method: 基于平均平方局部k阶上位系数统计，推导其与高阶上位的关系，并构建经验贝叶斯先验用于景观推断。
result: "在蛋白质和RNA数据中观察到高度结构化的上位模式，成功推断65,536基因型内含子景观并识别关键相互作用。"
conclusion: 该框架为总结和建模复杂适应性景观提供新工具，有助于连接大规模实验数据与景观数学理论。
---

## 摘要
适应度景观为理解遗传变异如何塑造进化结果提供了框架。尽管这些景观长期被视为抽象的概念对象，但基因工程和高通量表型分析的最新进展使得能够在大型组合序列空间上经验测量表型值。这些发展催生了统计框架的需求，以便在存在复杂遗传相互作用时总结、推断和解释适应度景观。在此，我们引入一个框架，基于不同位点子集突变之间的平均平方局部k路上位性系数，来总结位点间遗传相互作用的结构，并推导出这些局部k路上位性系数在不同背景下的方差与高于k阶的上位性之间的精确关系。这些统计量可以精确计算完整的组合景观，并与适应度景观文献中的经典统计量相关。此外，当数据不完整或有噪声时，它们可以从经验相关性中估计，并用于定义适应度景观推断的经验贝叶斯先验，该先验对不同位点子集涉及的相互作用进行差异化惩罚。我们将此推断方法应用于多样化的高通量蛋白质和RNA组合诱变数据集，发现适应度景观通常显示出跨位置的高度结构化遗传相互作用模式。最后，我们使用此模型推断一个包含65,536种基因型的动态自剪接内含子的适应度景观，并详细描述了塑造该景观结构的主要遗传相互作用及其与潜在分子机制的关系。这些结果共同为总结和建模复杂适应度景观，以及将大规模经验数据与适应度景观数学理论联系起来提供了新工具。

## Abstract
Fitness landscapes provide a framework for understanding how genetic variation shapes evolutionary outcomes. Although these landscapes were long treated as abstract conceptual objects, recent advances in genetic engineering and high-throughput phenotyping have enabled the empirical measurement of phenotypic values across large combinatorial sequence spaces. These developments create a need for statistical frameworks that can summarize, infer, and interpret fitness landscapes in the presence of complex genetic interactions. Here, we introduce a framework for summarizing the structure of genetic interactions across sites based on the average squared local k-way epistatic coefficients between mutations at different subsets of sites, and derive the precise manner in which the variance in these local k-way epistatic coefficients across backgrounds relates to epistasis of orders higher than k. These statistics can be computed exactly for complete combinatorial landscapes and are related to classical statistics in the fitness landscape literature. Moreover, they can be estimated from empirical correlations when data are incomplete or noisy, and used to define an empirical Bayes prior for fitness landscape inference that differentially penalizes interactions involving different subsets of sites. We apply this inference method to diverse high-throughput protein and RNA combinatorial mutagenesis datasets and find that fitness landscapes often show highly structured patterns of genetic interactions across positions. Finally, we use this model to infer a fitness landscape for a dynamic self-splicing intron comprising 65,536 genotypes, and describe in detail the main genetic interactions that shape the structure of this landscape and how they relate to the underlying molecular mechanism. Together, these results provide new tools for summarizing and modeling complex fitness landscapes, and for linking large-scale empirical data to the mathematical theory of fitness landscapes.