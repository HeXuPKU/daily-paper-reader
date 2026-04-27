---
title: A Correspondence-Driven Framework for Un-paired Spatial Multi-Omics Integrative Analysis
title_zh: 一种用于非配对空间多组学整合分析的对应驱动框架
authors: "Cai, W., Li, W."
date: 2026-04-21
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.14.676067v2.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 多组学整合分析的深度学习框架
tldr: SpatialFuser是一个针对非配对空间多组学数据整合的深度学习框架。它通过多头协作图注意力自动编码器（MCGATE）和迭代优化的最优传输算法，实现了跨表观组学、转录组学、蛋白质组学和代谢组学的精细整合。该框架能有效处理不同空间分辨率、发育阶段和分子模态的数据，在空间域识别和跨切片对齐方面表现优异，为理解组织微环境提供了全面视角。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的空间多组学技术在整合异质性、非配对数据集（如不同分辨率或模态）时面临巨大挑战。
method: 提出SpatialFuser框架，利用MCGATE推断多尺度细胞对应关系，并结合几何预匹配与迭代细化的最优传输实现跨切片对齐。
result: 在空间域识别、跨切片对齐和多组学整合的基准测试中，该方法显著优于现有最先进技术，并能揭示被掩盖的生物学变异。
conclusion: SpatialFuser是一个通用且灵活的工具，能够实现跨模态的信号恢复和发育动态分析，具有极高的扩展潜力。
---

## 摘要
空间多组学技术的最新进展为解释组织微环境中的分子特征提供了前所未有的机遇，但在跨异构数据集的整合分析方面仍面临挑战。在此，我们提出了 SpatialFuser，这是一个用于非配对空间表观组学、转录组学、蛋白质组学和代谢组学整合分析的对应驱动深度学习框架。SpatialFuser 引入了多头协同图注意力自动编码器（MCGATE），用于推断多尺度细胞对应关系，从而实现超越预定义空间邻域的空间异质性细粒度表征。通过结合灵活的几何预匹配进行粗略初始化，并利用迭代优化的最优传输推断自适应跨切片对应关系，SpatialFuser 能够实现跨具有不同几何形状、空间分辨率、发育阶段和分子模态的异构数据集的稳健整合。基准测试表明，在空间域识别、跨切片比对和多组学整合方面，该方法优于现有的最先进方法。在真实数据集上的应用表明，SpatialFuser 能够解析精确的分子模式，揭示发育动态，并恢复跨模态的互补信号。通过我们的方法对弱相关模态进行跨分辨率整合，进一步揭示了此前被掩盖的生物学变异。我们的

## Abstract
Recent advances in spatial multi-omics technologies provide unprecedented opportunities to interpret molecular features in tissue micro-environments but remain challenging in integrative analysis across heterogeneous datasets. Here we present SpatialFuser, a correspondence-driven deep learning framework for integrative analysis across un-paired spatial epigenomics, transcriptomics, proteomics, and metabolomics. SpatialFuser introduces a Multi-head Collaborative Graph Attention auToEncoder (MCGATE) to infer multi-scale cellular correspondences for fine-grained characterization of spatial heterogeneity beyond predefined spatial neighbourhoods. By incorporating flexible geometric pre-matching for coarse initialization and inferring adaptive cross-slice correspondences via iteratively refined optimal transport, SpatialFuser enables robust integration across heterogeneous datasets with varying geometries, spatial resolutions, developmental stages, and molecular modalities. Benchmarking demonstrates superior performance and reliability against existing state-of-the-art methods in spatial domain identification, cross-slice alignment, and multi-omics integration. Applications to real datasets demonstrate that SpatialFuser resolves precise molecular patterns, reveals developmental dynamics, and recovery of complementary signals across modalities. Cross-resolution integration of weakly correlated modalities by our method further uncovers previously obscured biological variation. Our framework is generalizable and versatile, enabling customized analytical scenarios and potential extension for emerging omics.

HighlightsO_LIA unified deep learning framework for spatial multi-omics integrative data analysis
C_LIO_LISuperior performance against state-of-the-art methods in spatial identification, alignment, and multi-omics integration
C_LIO_LIUnprecedented cross-modality analysis scenarios to offer a holistic view of spatial multi-omics
C_LIO_LIComprehensive framework design with generalizability and versatility for customized scenarios and potential extension
C_LI