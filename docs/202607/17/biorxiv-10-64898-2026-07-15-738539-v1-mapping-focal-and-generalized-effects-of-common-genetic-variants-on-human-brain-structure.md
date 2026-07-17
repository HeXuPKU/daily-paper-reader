---
title: Mapping Focal and Generalized Effects of Common Genetic Variants on Human Brain Structure
title_zh: 常见遗传变异对人脑结构局部与全局效应的映射
authors: "Gleave, E. J., Garcia-Marin, L. M., Ceja, Z., Renteria, M. E., Chattopadhyay, T., Gaser, C., Rajagopalan, P., Thompson, P. M."
date: 2026-07-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.15.738539v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 从GWAS位点计算多基因评分用于脑体积区域
tldr: 常见遗传变异对脑结构的影响既有局部也有全局模式。本研究利用GWAS位点构建十个脑区体积的多基因评分，在独立样本中通过体素形态学分析映射灰质体积关联。结果发现杏仁核、丘脑等区域的PGS显示局部效应，而脑干PGS关联全脑广泛差异。这些脑图揭示了基因影响的区域特异与分布特征，为解析脑结构遗传架构提供了新视角。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738539-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 883, \"height\": 711, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738539-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1879, \"height\": 1193, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738539-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1280, \"height\": 1180, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-15-738539-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 900, \"height\": 706, \"label\": \"Table\"}]"
motivation: 现有研究缺乏大脑全局遗传效应图，旨在揭示遗传变异对脑结构的影响模式是局灶性还是广泛性。
method: 从GWAS位点计算十个脑区体积的多基因评分，在独立样本中使用体素形态学映射灰质体积与PGS的关联3D图谱。
result: 杏仁核、丘脑和基底节PGS显示局部显著效应，而脑干PGS关联全脑广泛灰质差异。
conclusion: 脑图谱显示遗传影响既有局部也有分布模式，为解释脑结构基因组架构提供了新方法。
---

## 摘要
全基因组关联研究（GWAS）推动了我们对特定遗传变异如何影响人脑结构与功能的理解。近期研究已识别出数百个与皮层下脑体积相关的常见变异，激发了人们对这些遗传标记在脑网络中重叠程度的关注。虽然可以通过对遗传相关矩阵进行层次聚类来估计这种重叠，从而识别共享结构的模块化模式，但目前尚缺乏这些效应的全脑图谱。为解决此问题，我们基于与十个脑体积感兴趣区域（ROI）相关的位点计算了多基因评分（PGS）：九个主要皮层下结构以及颅内体积，每个位点根据其与区域体积的关联进行加权。在来自发现GWAS的独立样本中，我们使用基于体素的形态测量学（VBM）对三维容积T1加权MRI扫描进行大规模分割，以绘制与每个PGS相关的灰质体积（GMV）区域的三维分布图。我们发现，针对杏仁核、丘脑和基底节定义的PGS具有统计显著的局部效应，而脑干体积的PGS则与全脑广泛差异相关。这些全脑图谱揭示的模式与局部和分布式遗传影响均一致，为解释脑结构的基因组架构提供了一种新方法。

## Abstract
Genome-wide association studies (GWAS) have advanced the quest to understand how specific genetic variants influence human brain structure and function. Recent work has identified hundreds of common variants associated with subcortical brain volumes, sparking interest in how these genetic markers overlap across brain networks. While this can be estimated by hierarchical clustering of the genetic correlation matrix to identify modular patterns of shared architecture, no brain-wide maps of these effects are available. To address this, we computed polygenic scores (PGS) from loci associated with ten brain volume regions of interest (ROIs): nine major subcortical structures and intracranial volume, with each locus weighted by its association with regional volume. In an independent sample from the discovery GWAS, we performed large-scale segmentation of 3D volumetric T1-weighted MRI scans using voxel-based morphometry (VBM) to map 3D profile of regions where gray matter volume (GMV) was associated with each PGS. We found statistically significant, localized effects for PGS defined for the amygdala, thalamus, and basal ganglia, but PGS for brainstem volume was associated with widespread differences throughout the brain. These brain-wide maps reveal patterns consistent with both localized and distributed genetic influences, offering a novel approach to interpret the genomic architecture of brain structure.