---
title: "Melody: Decoding the Sequence Determinants of Locus-Specific DNA Methylation Across Human Tissues"
title_zh: "Melody: 解码人类组织特异性位点DNA甲基化的序列决定因素"
authors: "Jin, J., Wang, D., Qiao, J., Gao, W., Liu, Y., Chen, S., Zou, Q., Wu, S., Su, R., Wei, L."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.23.689975v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 深度学习模型从序列预测DNA甲基化，可与GWAS整合注释功能性非编码变异
tldr: DNA甲基化受DNA序列调控，但其序列决定因素尚不明确。Melody是一个深度学习框架，通过分析10kb基因组序列预测位点特异性甲基化，整合局部与长程信号。在39个人体组织中，Melody准确预测甲基化图谱，优于现有方法，并能推广至甲基化QTL效应预测和识别调控基序。扩展版Melody-G利用单细胞转录组数据推断未测细胞类型的甲基化状态，为理解人类甲基化组的调控逻辑提供了统一框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 探索DNA序列如何决定位点特异性DNA甲基化，揭示甲基化组的调控逻辑。
method: 构建Melody深度学习模型，从10kb序列整合局部与长程信号预测甲基化；Melody-G融合单细胞转录组嵌入推断未测组织状态。
result: 在39组织中准确预测甲基化，优于现有方法；可预测meQTL效应并识别调控基序，跨组织泛化能力强。
conclusion: Melody提供了连接基因组序列与细胞状态至DNA甲基化的统一框架，深化了对人类甲基化组调控机制的理解。
---

## 摘要
DNA甲基化是一种基本的表观遗传修饰，在转录调控、细胞分化和基因组稳定性中起着关键作用。然而，位点特异性DNA甲基化如何由内在DNA序列决定仍知之甚少。本文介绍Melody，一个深度学习框架，可从10-kb基因组序列预测DNA甲基化，从而实现局部和远程序列信号的整合。在39个人类组织中，Melody准确预测甲基化图谱，并在全染色体、低甲基化区域和细胞类型特异性基准测试中持续优于现有最先进方法。Melody还能泛化到甲基化数量性状位点（meQTL）效应预测，并识别与甲基化变异相关的调控序列基序。为了将预测扩展到已分析组织之外，我们进一步开发了Melody-G，它整合单细胞RNA-seq基础模型嵌入，直接从转录组数据推断先前未见细胞类型的甲基化状态。总之，Melody提供了一个统一框架，将基因组序列和细胞状态与DNA甲基化联系起来，并为控制人类甲基化组的调控逻辑提供了新见解。

## Abstract
DNA methylation is a fundamental epigenetic modification that plays crucial roles in transcriptional regulation, cellular differentiation, and genome stability. However, how locus-specific DNA methylation is determined by intrinsic DNA sequence remains poorly understood. Here, we introduce Melody, a deep learning framework that predicts DNA methylation from 10-kb genomic sequences, enabling the integration of both local and long-range sequence signals. Across 39 human tissues, Melody accurately predicts methylation profiles and consistently outperforms existing state-of-the-art methods in whole-chromosome, hypomethylated-region, and cell-type-specific benchmarks. Melody also generalizes to methylation quantitative trait locus (meQTL) effect prediction and identifies regulatory sequence motifs associated with methylation variability. To extend prediction beyond profiled tissues, we further develop Melody-G, which incorporates single-cell RNA-seq foundation model embeddings to infer methylation states in previously unseen cell types directly from transcriptomic data. Together, Melody provides a unified framework for linking genomic sequence and cellular state to DNA methylation and offers new insights into the regulatory logic governing the human methylome.