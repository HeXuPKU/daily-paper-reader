---
title: HOMED enables hierarchical and multimodal optimization of DNA methylation deconvolution across tissues
title_zh: HOMED：实现跨组织DNA甲基化去卷积的分层与多模态优化
authors: "Liu, Y., Chen, Y., Du, Y., Garmire, L."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.730896v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 开发DNA甲基化去卷积的统计优化方法，类似于GWAS统计方法
tldr: 针对DNA甲基化去卷积中细胞异质性问题，现有方法忽略细胞层次且泛化性差。HOMED框架整合细胞谱系层次、单细胞RNA-seq引导和配对多组学数据，优化CpG签名。在模拟及真实PBMC、肺、胎盘数据中，HOMED取得最高PCC和最低RMSE，优于现有方法。显著提高了去卷积准确性、分辨率和跨组织泛化能力。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有DNA甲基化去卷积方法忽略细胞层次，且因参考谱变异有限而泛化性差。
method: 提出HOMED，利用细胞谱系层次、单细胞RNA-seq引导及配对bulk RNA-seq/DNAm数据优化CpG签名。
result: 在PBMC、肺和胎盘数据中，HOMED取得最高PCC和最低RMSE，优于现有方法。
conclusion: HOMED提高了DNA甲基化去卷积的准确性、分辨率和跨组织泛化性。
---

## 摘要
细胞异质性是表观基因组关联研究中批量DNA甲基化数据的主要混杂因素。现有的基于参考的DNA甲基化去卷积方法往往忽略相关细胞类型间的层次结构，且由于参考谱的变异性有限，可能在不同数据集间泛化能力较差。我们开发了HOMED（分层优化甲基化去卷积）框架，该框架整合了细胞谱系层次结构、单细胞RNA测序引导的去卷积以及成对的批量RNA-seq/DNA甲基化数据，用于CpG特征优化。在模拟和真实的外周血单核细胞、肺和胎盘数据集中，HOMED始终获得最高的皮尔逊相关系数和最低的均方根误差，优于现有的单细胞RNA测序引导的DNA甲基化去卷积方法，提高了准确性、分辨率和跨组织泛化能力。

## Abstract
Cellular heterogeneity is a major confounder in bulk DNA methylation data for epigenome-wide association studies. Existing reference-based DNAm deconvolution methods often ignore hierarchies among related cell types and may generalize poorly across datasets due to limited variability in reference profiles. We developed HOMED (Hierarchically Optimized Methylation Deconvolution), a framework that integrates cell-lineage hierarchies, single-cell RNA sequencing-guided deconvolution, and paired bulk RNA-seq/DNAm data for CpG signature optimization. Across simulated and real peripheral blood mononuclear cell, lung, and placental datasets, HOMED consistently yielded the highest PCCs and lowest RMSEs, outperforming existing scRNA-seq-guided DNAm deconvolution methods, improving accuracy, resolution, and cross-tissue generalizability.