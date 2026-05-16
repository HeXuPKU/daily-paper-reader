---
title: "simPIC: flexible simulation of single-cell ATAC-seq paired-insertion counts from individuals to populations"
title_zh: simPIC：从个体到群体的单细胞 ATAC-seq 双端插入计数的灵活模拟
authors: "Chugh, S., Shim, H. S., McCarthy, D. J."
date: 2026-05-15
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.21.676689v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 用于群体规模染色质开放性QTL映射的模拟工具
tldr: simPIC是一个高效的单细胞ATAC-seq数据模拟框架，旨在解决群体规模研究中缺乏灵活模拟工具的问题。它能够模拟细胞群体、批次效应及受基因型影响的染色质开放性变异（如caQTL）。该工具在保持与真实数据分布高度一致的同时，具备极佳的内存效率和扩展性，支持大规模队列模拟，为单细胞群体遗传学研究提供了可靠的基准测试平台。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的单细胞ATAC-seq模拟工具缺乏灵活性，且难以支持大规模群体水平及基因型相关的变异模拟。
method: simPIC通过建模细胞组、批次效应和基因型依赖的开放性变异，实现从个体到群体的高效、低内存消耗的数据模拟。
result: 实验表明simPIC生成的模拟数据在多种细胞类型中均能紧密拟合真实数据分布，且其扩展性远超现有工具。
conclusion: simPIC为评估群体规模的单细胞染色质开放性分析方法（如QTL映射）提供了一个强大且灵活的模拟框架。
---

## 摘要
单细胞转座酶可及染色质测序 (scATAC-seq) 正越来越多地应用于群体规模，以研究遗传变异如何塑造染色质可及性。由于缺乏具有已知基准真值 (ground truth) 的灵活模拟工具，方法学的发展受到了限制。在此，我们提出了 simPIC，这是一个快速且内存高效的框架，用于模拟跨个体和群体的真实单细胞 ATAC-seq 计数数据。simPIC 对细胞群、批次效应和基因型依赖的可及性变异进行建模，从而能够对群体规模的方法进行受控评估，包括染色质可及性数量性状位点 (QTL) 定位。在多个数据集和细胞类型中，simPIC 与真实数据分布高度匹配，同时能够扩展到现有工具无法处理的队列规模。

## Abstract
Single-cell Assay for Transposase Accessible Chromatin (scATAC-seq) is increasingly used at population scale to study how genetic variation shapes chromatin accessibility. Method development is limited by the lack of flexible simulation tools with known ground truth. Here, we present simPIC, a fast, memory efficient framework for simulating realistic single-cell ATAC-seq count data across individuals and populations. simPIC models cell groups, batch effects, and genotype-dependent accessibility variation, enabling controlled evaluation of population-scale methods, including chromatin accessibility quantitative traits locus (QTL) mapping. Across multiple datasets and cell types, simPIC closely matches real data distributions while scaling to cohort sizes impractical for current tools.