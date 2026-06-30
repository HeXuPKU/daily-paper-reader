---
title: Complex-valued representations of time-series gene expression profiles for network analysis
title_zh: 用于网络分析的时序基因表达谱复数值表示
authors: "Sun, J., Cao, W., Ikumi, K., Shimizu, K. K., Sese, J."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.16.732574v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 时间序列基因表达网络的复数表示方法
tldr: 传统时间序列基因表达分析使用实值向量，受量子信息理论启发，本研究提出复数编码框架。将表达谱编码为振幅，时间差异和局部变化方向编码为相位，用 fidelity 度量基因相似性。在多个RNA-seq数据上，fidelity分布与相关性不同但相关，构建的网络社区识别出主要时序表达程序，功能注释与WGCNA等方法可比。本研究为转录组时序组织提供互补视角。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统实值向量表示和相关性度量无法充分捕获时间序列中的动态信息，受量子信息理论启发，提出复数编码方案。
method: 将基因表达谱编码为复数向量，振幅表示表达值，相位编码时间差异及局部变化方向，用 fidelity 量化基因相似性。
result: 多个物种数据中，fidelity分布与相关系数分布不同但相关；网络社区捕获主要时序程序，功能富集与WGCNA等经典方法可比。
conclusion: 提供时序转录组组织的互补视角，而非传统方法的统一替代。
---

## 摘要
时间序列RNA测序为研究动态基因调控提供了强大的框架，但常规分析通常将基因表达谱表示为欧几里得空间中的实值向量，并使用相关性或距离来量化相似性。受量子信息理论启发，我们提出了一种框架，将时间序列基因表达谱编码为希尔伯特空间中包含振幅和相位分量的复值向量。我们设计了多种编码模型，将基因表达表示为复值向量的振幅，将时间差异编码为相位，并扩展相位表示以包含局部表达变化的方向。然后使用保真度（fidelity）量化基因-基因相似性，该保真度测量两个编码向量之间的重叠。使用跨不同物种和生物学背景的时间序列RNA-seq数据集进行的评估表明，不同的编码模型产生了不同的保真度分布，这些分布与传统的相关性度量相关但有所不同。然后，我们使用成对保真度值构建基因-基因网络，并检测包含具有相似时间谱的基因的群落。尽管不同编码模型的保真度分布不同，但所得群落捕获了主要的时间表达程序，基于基因本体和京都基因与基因组百科全书通路分析的功能注释提供了探索性的生物学背景。检测到的群落与使用传统方法（包括加权相关网络分析和模糊c均值聚类）得到的群落相当。此外，作为概念验证，我们进行了SWAP测试电路模拟，以在量子计算机上模拟保真度计算；在噪声感知条件下，这些模拟产生的保真度估计精度较低，计算成本高于经典计算。作为概念验证，本研究提供了时间转录组组织的补充视角，而非传统方法的统一优越替代方案。

## Abstract
Time-series RNA sequencing provides a powerful framework for studying dynamic gene regulation, yet conventional analyses usually represent gene expression profiles as real-valued vectors in Euclidean space and quantify similarity using correlation or distance. Inspired by quantum information theory, we present a framework for encoding time-series gene expression profiles as complex-valued vectors comprising amplitude and phase components in Hilbert space. We designed multiple encoding models to represent gene expression in the amplitude of complex-valued vectors, encode temporal differences in the phase, and extend the phase representation to incorporate the direction of local expression changes. Gene-gene similarity was then quantified using fidelity, which measures the overlap between two encoded vectors. Evaluation using time-series RNA-seq datasets across diverse species and biological contexts showed that different encoding models produced distinct fidelity distributions that were related to, but distinct from, conventional correlation measures. We then constructed gene-gene networks using pairwise fidelity values and detected communities containing genes with similar temporal profiles. Although fidelity distributions differed across encoding models, the resulting communities captured major temporal expression programs, and functional annotations based on gene ontology and Kyoto encyclopedia of genes and genomes pathway analyses provided exploratory biological context. The detected communities were comparable to those obtained using conventional methods, including weighted correlation network analysis and fuzzy c-means clustering. Furthermore, as a proof-of-concept, we performed SWAP-test circuit simulations to mimic fidelity computation on a quantum computer; under noise-aware conditions, these simulations produced less accurate fidelity estimates with higher computational cost than classical computation. As a proof-of-concept, this study provides a complementary view of temporal transcriptome organization, rather than a uniformly superior alternative to conventional methods.