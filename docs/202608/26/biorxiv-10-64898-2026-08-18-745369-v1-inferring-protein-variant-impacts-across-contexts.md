---
title: Inferring Protein Variant Impacts Across Contexts
title_zh: 推断蛋白质变异在不同背景下的影响
authors: "Rasoulzadeh Hosseini, A., Senguttuvan, V., van Loggerenberg, W., Border, R., Roth, F. P."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.18.745369v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 基于MAVE数据的多情境蛋白质变异效应插补，将功能证据迁移至GWAS变异解读
tldr: 上下文相关蛋白变体效应的全面测量受实验预算限制，难以覆盖无限可能的遗传和环境上下文。该研究提出利用亚饱和上下文MAVE数据通过插补填补空白，系统比较线性混合模型、随机森林和自编码器等插补方案。结果发现最优方法取决于插补任务及测量密度：数据充足时灵活模型占优，数据稀疏时简单模型更可靠，但简单回归无法推断未测变体。研究提供了多上下文插补的概念框架和初步评估，有助于扩大上下文依赖变体效应研究范围。
source: biorxiv
selection_source: fresh_fetch
motivation: 全面测量上下文相关蛋白变体效应受限于实验预算，需要有效的插补策略填补未测量上下文和变体的空白。
method: 系统比较线性混合效应模型、随机森林和自编码器等插补方法，评估不同任务和数据密度下的表现。
result: 最优方法取决于上下文测量密度：数据丰富时灵活模型占优，稀疏时简单模型更可靠，但无法推断未测变体。
conclusion: 建议根据插补任务和测量密度选择方法，并提供了多上下文插补框架，以扩展大规模上下文变体效应研究。
---

## 摘要
多重变异效应分析（MAVEs）可并行测量许多蛋白质序列变异的功能影响，可能覆盖所有可能的单氨基酸替换。与当前的计算变异效应预测器不同，MAVEs能够揭示变异在不同遗传和环境背景下的效应。然而，可能的背景空间实际上是无限的，而背景性MAVE研究受限于有限的实验预算。为了最大化跨背景的覆盖率，一种策略是进行亚饱和背景MAVEs，然后通过插补填补空白。在此，我们对不同的插补挑战进行分类和比较，探索一系列多背景插补解决方案，包括线性混合效应模型、随机森林和自编码器，并为如何针对特定插补任务最佳地进行提供见解。我们发现，最优方法取决于插补任务以及背景测量的密集程度。更灵活的模型在测量充足时表现出色，而最简单的模型在测量稀疏时被证明最为可靠。然而，简单的源到目标回归模型虽然非常适合插补在源背景中测量到的变异得分，却无法插补在任何背景中均未被测量的变异得分。当两个图谱均测量稀疏时，这是一个主要限制。我们提供了一个概念框架，并对多背景插补方法进行了初步评估，这些方法可扩展大规模背景依赖性变异效应研究的范围。

## Abstract
Multiplexed assays of variant effects (MAVEs) measure the functional impact of many protein sequence variants in parallel, potentially covering all possible single amino acid substitutions. Unlike current computational variant effect predictors, MAVEs can reveal the effects of variants under different genetic and environmental contexts. However, whereas the space of possible contexts is effectively infinite, contextual MAVE studies are limited by finite experimental budgets. To maximize coverage across contexts, one strategy is to carry out sub-saturation contextual MAVEs and then fill in the gaps via imputation. Here, we categorize and compare different imputation challenges, explore a collection of multi-context imputation solutions, including linear mixed-effects models, random forests, and autoencoders, and provide insight into how best to proceed for a given imputation task. We find that the optimal method depends on the imputation task and how densely the contexts have been measured. More flexible models excel when measurements are plentiful, whereas the simplest models prove most reliable when measurements are sparse. However, the simple source-to-target regression models, although well suited to imputing scores for variants measured in the source context, cannot impute scores for variants that were not measured in either context. This is a major limitation when both maps are sparsely measured. We provide a conceptual framework and an initial evaluation of multi-context imputation methods that can extend the scope of large-scale studies of context-dependent variant effects.