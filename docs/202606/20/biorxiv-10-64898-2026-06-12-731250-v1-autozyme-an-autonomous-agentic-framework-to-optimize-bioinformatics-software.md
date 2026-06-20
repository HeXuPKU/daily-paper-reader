---
title: "AutoZyme: An Autonomous Agentic Framework to Optimize Bioinformatics Software"
title_zh: "AutoZyme: 一种用于优化生物信息学软件的自主体智能框架"
authors: "Xie, E., Cheng, L., Cai, Y., Shireman, J., Kendziorski, C."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.731250v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 用于优化基因组学软件的自主智能体框架，与医疗数据中的AI智能体相关
tldr: "生物信息学软件的性能瓶颈随数据增大而加重，但优化依赖专家手动，难以扩展。AutoZyme是一个自主智能体框架，可自动为目标函数构建基准、识别瓶颈并迭代测试代码更改，仅保留提升运行时间且保持输出正确的优化。在45个函数中超过95%实现了性能提升，对基因组学软件包中38个函数的中位数加速达8.52倍，最大超过676倍。该框架以即插即用库形式发布优化函数，并可作为通用框架用于其他软件优化。"
source: biorxiv
selection_source: fresh_fetch
motivation: 基因组学和生物信息学软件性能瓶颈依赖专家手动优化，难以规模化，亟需自动化方法。
method: AutoZyme利用智能体自动构建基准测试、识别瓶颈、迭代生成并测试代码更改，仅保留提升运行时间且不改变输出的优化。
result: "评估45个函数，95%以上运行时间改善，对38个来自Seurat等包的函数中位数加速8.52倍，最大676倍，内存无显著增加。"
conclusion: AutoZyme提供即插即用的优化函数库和可重用框架，有效加速现有分析流程并支持扩展。
---

## 摘要
随着生物数据集在规模和数量上的持续增长，广泛使用的基因组学和生物信息学软件中的性能瓶颈构成了日益沉重的负担。缓解这些瓶颈主要依赖专家手动优化，因此难以规模化。本文提出AutoZyme，一个面向科学软件优化的智能体框架。给定目标函数，AutoZyme构建基准测试、识别瓶颈并迭代测试代码变更，仅保留那些能提升运行时间且保持输出不变的变更。我们在45个函数上评估了AutoZyme，在超过95%的案例中提升了运行时间且未显著增加内存。对于来自Seurat、Scanpy及其相关基因组学和生物信息学包的38个函数，AutoZyme将运行时间中位数降低了8.52倍，最大降幅超过676倍。优化后的函数通过AutoZyme-Library分发，可作为现有分析流程的即插即用替代。我们还发布了AutoZyme作为一个可重用框架，用于优化用户指定的其他包和函数。

## Abstract
Performance bottlenecks in widely used genomics and bioinformatics software present a substantial and growing burden as biological datasets continue to increase in size and number. Relieving these bottlenecks relies largely on expert manual optimization and therefore remains difficult to scale. Here we present AutoZyme, an agentic framework for scientific software optimization. Given a target function, AutoZyme builds benchmarks, identifies bottlenecks, and iteratively tests code changes, retaining only those that improve runtime while preserving output. We evaluated AutoZyme on 45 functions, improving runtime without substantial memory increases in over 95% of cases considered. Across 38 functions from Seurat, Scanpy and related packages in genomics and bioinformatics, AutoZyme reduced runtime by a median of 8.52-fold, with the largest reductions exceeding 676-fold. The optimized functions are distributed through AutoZyme-Library as drop-in replacements for existing analysis pipelines. We also release AutoZyme as a reusable framework for optimizing additional user-specified packages and functions.