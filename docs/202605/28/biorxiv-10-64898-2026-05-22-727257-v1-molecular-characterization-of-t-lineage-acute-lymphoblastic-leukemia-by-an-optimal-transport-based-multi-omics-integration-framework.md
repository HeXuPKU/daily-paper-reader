---
title: Molecular Characterization of T-Lineage Acute Lymphoblastic Leukemia by an Optimal-Transport Based Multi-Omics Integration Framework
title_zh: 基于最优传输的多组学整合框架对T系急性淋巴细胞白血病的分子特征描述
authors: "Li, L., Wang, J., Wan, S."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.22.727257v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 基于最优传输的多组学整合框架用于分子表征
tldr: T-ALL是一种异质性强的儿童血液肿瘤，现有诊断方法耗时且依赖单模态数据。本文提出OTTER框架，利用模态特异变分自编码器编码RNA-seq和基因组变异，并通过Gromov-Wasserstein最优传输对齐潜在空间以保持几何结构。在1309例患者17个亚型中，OTTER识别出亚型驱动特征和跨模态协调程序。该框架提供了可解释的多组学整合方法，可推广至其他癌症。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决T-ALL多组学数据有效整合的挑战，克服单模态数据在分子分型中的局限性。
method: 使用模态特异VAE编码转录组和基因组变异，通过Gromov-Wasserstein最优传输对齐潜在表示，保留各模态内部几何结构。
result: 在COG AALL0434队列中成功识别17个亚型的驱动分子特征及跨组学相互作用模式。
conclusion: OTTER为多组学驱动的T-ALL分子表征提供可解释且通用的计算框架，可推广至其他癌症。
---

## 摘要
T系急性淋巴细胞白血病（T-ALL）是一种侵袭性儿童恶性肿瘤，其特点是在多个分子层面上存在复杂的异质性。准确的亚型分类对于理解疾病机制、风险分层和指导靶向治疗策略至关重要。然而，当前的诊断方法劳动强度大且耗时，现有计算方法受限于依赖单一模态数据或简单的整合策略。异构多组学数据的有效整合仍然是一个主要的计算挑战。我们提出了OTTER（基于最优传输的转录组学和基因组学表示融合），这是一种新颖的多模态深度学习框架，可联合建模RNA-seq基因表达和体细胞基因组变异数据，用于T-ALL的分子特征描述。OTTER通过模态特定的变分自编码器对每个组学模态进行编码，并使用Gromov-Wasserstein最优传输（GW-OT）对齐产生的潜在表示，该方法在不需要共享特征空间的情况下保留了每个模态的内部几何结构。我们将OTTER应用于儿童肿瘤组（COG）AALL0434队列，该队列包含17种T-ALL亚型的1309名患者。在保留集上进行了基于梯度的特征重要性和跨组学相互作用分析，以识别亚型驱动的分子特征和跨模态协调程序。OTTER为多组学驱动的T-ALL分子特征描述提供了一个有原则、生物学可解释且计算高效的框架。通过利用GW-OT进行几何保持的跨模态对齐和基于梯度的可解释性进行跨组学相互作用分析，OTTER超越了单模态方法，揭示了T-ALL的协调分子景观。该框架可推广至其他癌症和多组学整合任务。

## Abstract
T-lineage acute lymphoblastic leukemia (T-ALL) is an aggressive pediatric malignancy characterized by complex heterogeneity across multiple molecular layers. Accurate subtyping is essential for understanding disease mechanisms, risk stratification, and guiding targeted therapeutic strategies. However, current diagnostic approaches are labor-intensive and time-consuming, and existing computational methods are limited by reliance on single-modality data or simple integration strategies. Effective integration of heterogeneous multi-omics data remains a major computational challenge. We present OTTER (Optimal Transport-based Transcriptomics and gEnomics Representation fusion), a novel multi-modal deep learning framework that jointly models RNA-seq gene expression and somatic genomic variant data for T-ALL molecular characterization. OTTER encodes each omics modality through a modality-specific variational autoencoder and aligns the resulting latent representations using Gromov-Wasserstein optimal transport (GW-OT), which preserves the internal geometric structure of each modality without requiring a shared feature space. We applied OTTER to the Children's Oncology Group (COG) AALL0434 cohort comprising 1,309 patients across 17 T-ALL subtypes. Gradient-based feature importance and cross-omics interaction analysis were performed on the holdout set to identify subtype-driving molecular features and cross-modal coordinated programs. OTTER provides a principled, biologically interpretable, and computationally effective framework for multi-omics-driven T-ALL molecular characterization. By leveraging GW-OT for geometry-preserving cross-modal alignment and gradient-based interpretability for cross-omics interaction profiling, OTTER goes beyond single-modality approaches to uncover the coordinated molecular landscape of T-ALL. The framework is generalizable to other cancers and multi-omics integration tasks.