---
title: Inferring Protein Variant Impacts Across Contexts
title_zh: 跨情境推断蛋白质变异影响
authors: "Rasoulzadeh Hosseini, A., Senguttuvan, V., van Loggerenberg, W., Border, R., Roth, F. P."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.18.745369v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 跨遗传与环境背景的变异效应插补；对应基因-环境交互作用信号
tldr: 上下文相关变体效应研究受无限上下文空间与有限实验预算的制约，本文采用亚饱和MAVE实验并借助插补方法补全数据。系统比较线性混合效应模型、随机森林和自编码器在多上下文插补中的表现。发现最优方法取决于上下文测量密度：数据丰富时灵活模型更强，数据稀疏时简单模型更可靠。揭示了简单源-目标回归在双缺失场景下的局限，并为多上下文插补提供了概念框架与基准。
source: biorxiv
selection_source: fresh_fetch
motivation: 上下文空间近乎无限而实验预算有限，需用亚饱和实验与插补来扩展上下文相关变体效应的覆盖范围。
method: 系统比较线性混合模型、随机森林和自编码器在不同稀疏程度的多上下文插补任务中的表现。
result: 最优方法依赖测量密度，数据多时灵活模型更优，数据少时简单模型更可靠，且简单回归无法处理双缺失。
conclusion: 提供多上下文插补的概念框架和初步基准，指导不同插补任务的方法选择。
---

## 摘要
变异效应的多重分析（MAVEs）并行测量许多蛋白质序列变体的功能影响，可能覆盖所有可能的单氨基酸替换。与当前的计算性变异效应预测器不同，MAVEs可以揭示变体在不同遗传和环境情境下的效应。然而，尽管可能情境的空间实际上是无限的，情境性MAVE研究却受到有限实验预算的限制。为了最大化跨情境的覆盖，一种策略是进行亚饱和情境MAVE，然后通过插补填补空白。在此，我们对不同的插补挑战进行分类和比较，探索一系列多情境插补解决方案，包括线性混合效应模型、随机森林和自编码器，并为给定插补任务提供最佳操作见解。我们发现，最优方法取决于插补任务以及情境测量的密集程度。当测量数据丰富时，更灵活的模型表现优异，而当测量数据稀疏时，最简单的模型被证明最可靠。然而，简单的源到目标回归模型虽然非常适合为在源情境中测量的变体插补分数，但无法为在任一情境中都未测量的变体插补分数。当两个图谱都稀疏测量时，这是一个主要限制。我们提供了一个概念框架以及对多情境插补方法的初步评估，这些方法可以扩展大规模情境依赖性变体效应研究的范围。

## Abstract
Multiplexed assays of variant effects (MAVEs) measure the functional impact of many protein sequence variants in parallel, potentially covering all possible single amino acid substitutions. Unlike current computational variant effect predictors, MAVEs can reveal the effects of variants under different genetic and environmental contexts. However, whereas the space of possible contexts is effectively infinite, contextual MAVE studies are limited by finite experimental budgets. To maximize coverage across contexts, one strategy is to carry out sub-saturation contextual MAVEs and then fill in the gaps via imputation. Here, we categorize and compare different imputation challenges, explore a collection of multi-context imputation solutions, including linear mixed-effects models, random forests, and autoencoders, and provide insight into how best to proceed for a given imputation task. We find that the optimal method depends on the imputation task and how densely the contexts have been measured. More flexible models excel when measurements are plentiful, whereas the simplest models prove most reliable when measurements are sparse. However, the simple source-to-target regression models, although well suited to imputing scores for variants measured in the source context, cannot impute scores for variants that were not measured in either context. This is a major limitation when both maps are sparsely measured. We provide a conceptual framework and an initial evaluation of multi-context imputation methods that can extend the scope of large-scale studies of context-dependent variant effects.