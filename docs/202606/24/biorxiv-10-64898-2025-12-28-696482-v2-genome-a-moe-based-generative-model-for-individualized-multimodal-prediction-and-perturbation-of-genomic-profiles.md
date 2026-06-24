---
title: "GenoME: a MoE-based generative model for individualized, multimodal prediction and perturbation of genomic profiles"
title_zh: GenoME：基于MoE的生成模型，用于个性化、多模态预测和扰动基因组图谱
authors: "Wei, J., Xue, Y., Chai, H., Gao, Y. Q."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.28.696482v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 基于MoE的多模态基因组预测模型，支持功能基因组学整合
tldr: 非编码基因组通过复杂的多尺度调控系统运作，现有模型难以整合多种基因组特征进行预测。本研究提出基于混合专家模型（MoE）的生成模型GenoME，利用DNA序列和细胞类型特异的ATAC-seq信号，预测统一的多模态基因组图谱，涵盖表观组、转录组和染色质三维结构。GenoME能对未观测区域进行多尺度预测，并通过少量ATAC-seq数据泛化至未知细胞类型。该模型配备的计算机扰动框架可准确模拟基因扰动后的多模态后果，并识别功能增强子-启动子连接，优于Activity-by-Contact等专用模型。GenoME提供了一个集生成建模、跨细胞类型泛化和因果机制研究于一体的通用平台。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有计算模型难以同时整合表观修饰、转录因子结合和三维染色质构象，预测非编码基因组的多尺度调控机制。
method: 提出GenoME，基于MoE架构，以DNA序列和细胞类型ATAC-seq为输入，端到端预测表观组、转录组和染色质结构的多模态基因组图谱。
result: GenoME可精准预测未知区域及未见细胞类型的全调控景观，其扰动框架在多模态预测和增强子-启动子连接识别上优于Activity-by-Contact等对比方法。
conclusion: GenoME为多尺度调控基因组提供了统一框架，支持跨细胞类型泛化与因果机制解析，推动个性化基因组学发展。
---

## 摘要
非编码基因组通过复杂的多尺度调控系统运作，其中受调控的基因表达与细胞类型特异性的组蛋白修饰、转录因子结合和三维构象密切相关。开发能够整合这些模式以预测和解释调控系统的计算模型仍然具有挑战性。这里，我们提出GenoME，一种基于专家混合（MoE）的生成模型，利用DNA序列和细胞类型特异性的ATAC-seq信号，预测涵盖表观基因组学、转录组学和染色质结构（从碱基对到千碱基分辨率）的统一基因组图谱。GenoME能够对留出的基因组区域进行多尺度预测，关键在于，它能够从单一的ATAC-seq输入泛化预测未见或个体化细胞类型的完整调控景观。我们为GenoME配备了一个计算机模拟扰动框架，该框架能够准确预测遗传扰动的多模态后果，并识别功能性增强子-启动子连接，优于诸如Activity-by-Contact等专门模型。这些预测还可用于解读细胞类型特异性增强子的转录因子语法。因此，GenoME为多尺度调控基因组的生成建模、跨细胞类型泛化以及因果机制研究提供了一个多功能、一体化的平台。

## Abstract
The non-coding genome operates through a complex, multiscale regulatory system where regulated gene expressions are closely associated with cell-type-specific histone modifications, transcription factor binding and 3D conformation. Developing computational models that can integrate these patterns to predict and interpret the regulatory system remains challenging. Here, we present GenoME, a Mixture of Experts (MoE)-based generative model that uses DNA sequence and cell-type-specific ATAC-seq signals to predict a unified genomic profile encompassing epigenomics, transcriptomics, and chromatin architecture at base-pair to kilobase resolutions. GenoME enables multiscale predictions for held-out genomic regions and, critically, generalizes to predict the full regulatory landscape of unseen or individualized cell types from a single ATAC-seq input. We equip GenoME with an in silico perturbation framework that accurately forecasts the multimodal consequences of genetic perturbations and identifies functional enhancer-promoter connections, outperforming specialized models like Activity-by-Contact. These predictions can also be used to decipher the transcription factor grammar of cell-type-specific enhancers. GenoME thus provides a versatile, all-in-one platform for generative modeling, cross-cell-type generalization, and causal mechanistic investigation of the multiscale regulatory genome.