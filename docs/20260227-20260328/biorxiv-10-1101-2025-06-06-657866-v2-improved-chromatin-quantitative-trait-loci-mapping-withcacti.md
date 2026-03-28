---
title: Improved chromatin quantitative trait loci mapping withCACTI
title_zh: 利用 CACTI 改进染色质数量性状位点（cQTL）图谱绘制
authors: "Wang, L., Qi, Z., Liu, X."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.1101/2025.06.06.657866v2.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 映射染色质数量性状位点以阐明调节机制的新方法
tldr: "染色质定量性状位点（cQTL）映射对理解基因调控至关重要，但传统方法受限于检测效能。本文提出CACTI，通过利用相邻调控元件间的相关性，在多种组蛋白修饰中识别出比传统方法多51%-255%的cQTL信号。CACTI显著提升了与GWAS位点的共定位效率，并揭示了大量eQTL无法解释的调控机制，为复杂性状的功能解读提供了强有力的工具。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-06-06-657866-v2/fig-001.webp\", \"caption\": \"Figure 2. Performance comparison of CACTI versus standard single-peak–based methods.\", \"page\": 9, \"index\": 1, \"width\": 1020, \"height\": 979}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-06-06-657866-v2/fig-002.webp\", \"caption\": \"Figure 4. Colocalization of GWAS loci of 36 blood related traits and 8 immune diseases with cQTLs versus eQTLs.\", \"page\": 18, \"index\": 2, \"width\": 1020, \"height\": 1208}]"
motivation: 现有的cQTL映射方法由于检测效能有限且受限于峰值调用的准确性，难以全面揭示复杂性状的调控机制。
method: 开发了名为CACTI的新方法，通过整合相邻调控元件之间的相关性信息来增强cQTL的检测能力。
result: "CACTI在五种组蛋白修饰中识别出的信号量提升了51%-255%，且与GWAS位点的共定位数量比标准方法高出15%-424%。"
conclusion: CACTI显著提高了cQTL映射的灵敏度，能够发现eQTL分析无法检测到的调控机制，极大地增强了对GWAS结果的功能解释。
---

## 摘要
绘制染色质数量性状位点（cQTL）图谱对于阐明调控基因表达和复杂性状的分子机制至关重要。然而，目前的 cQTL 绘图方法检测效能有限，特别是在现有样本量下，且受限于峰值调用（peak-calling）的准确性。为解决这些局限性，我们提出了 CACTI，这是一种通过利用相邻调控元件之间的相关性来改进 cQTL 绘图的新方法。在多种组蛋白修饰（H3K4me1、H3K4me3、H3K27ac、H3K27me3 和 H3K36me3）和细胞类型中，与传统的基于单峰的方法相比，CACTI 识别出的 cQTL 信号增加了 51%-255%。利用 CACTI，我们为多种细胞类型中的五种组蛋白修饰生成了全面的 cQTL 图谱，并对来自 44 种复杂性状的 GWAS 位点进行了共定位分析。CACTI cQTL 与 6%-47% 的 GWAS 位点共定位，在不同修饰中，这比标准 cQTL 绘图方法平均多出 15%-424%。24%-75% 的共定位 GWAS 位点未显示出与 eQTL 的共定位。这突显了 CACTI 揭示调控机制的独特能力，而这些机制仅靠 eQTL 分析是无法检测到的，从而显著提高了对 GWAS 发现的功能解释。

## Abstract
Mapping chromatin quantitative trait loci (cQTLs) is crucial for elucidating the regulatory mechanisms governing gene expression and complex traits. However, current cQTL mapping methods suffer from limited detection power, particularly at existing sample sizes, and are constrained by peak-calling accuracy. To address these limitations, we present CACTI, a novel method that improves cQTL mapping by leveraging correlations between neighboring regulatory elements. Across diverse histone marks (H3K4me1, H3K4me3, H3K27ac, H3K27me3 and H3K36me3) and cell types, CACTI identifies 51%-255% more cQTL signals compared to traditional single-peak-based approaches. Using CACTI, we generate a comprehensive cQTL map for the five histone marks across multiple cell types and perform colocalization analyses with GWAS loci from 44 complex traits. CACTI cQTLs colocalize with 6%-47% of GWAS loci, which is on average 15%-424% more than the standard cQTL mapping method across different marks. 24%-75% of colocalized GWAS loci show no colocalization with eQTLs. This underscores CACTI's unique ability to uncover regulatory mechanisms that would otherwise remain undetected by eQTL analysis alone, significantly improving the functional interpretation of GWAS findings.