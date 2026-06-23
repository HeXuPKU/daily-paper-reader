---
title: "GenoME: a MoE-based generative model for individualized, multimodal prediction and perturbation of genomic profiles"
title_zh: GenoME：基于MoE的生成模型，用于个体化、多模态预测和扰动基因组图谱
authors: "Wei, J., Xue, Y., Chai, H., Gao, Y. Q."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.28.696482v2.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 基于MoE的基因组多模态预测生成模型，属于基因组大模型
tldr: 基因组调控涉及复杂多尺度系统，现有模型难以整合多种数据类型。本文提出GenoME，一个基于混合专家模型的生成模型，利用DNA序列和ATAC-seq信号统一预测表观组、转录组和染色质构型。该模型不仅能预测保留区域的多尺度特征，还可仅从单个ATAC-seq输入泛化至未知细胞类型。结合in silico扰动框架，GenoME准确预测遗传扰动的多模态后果并识别增强子-启动子连接，性能优于Activity-by-Contact，为多尺度调控基因组提供了通用研究和因果推断平台。
source: biorxiv
selection_source: fresh_fetch
motivation: 非编码基因组多尺度调控系统复杂，现有模型难以整合表观组、转录组和染色质构型等多种数据进行统一预测。
method: 基于混合专家模型（MoE），以DNA序列和ATAC-seq为输入，生成包含表观组、转录组和染色质构型的统一多尺度基因组图谱。
result: 可预测保留区域并泛化至未见细胞类型；in silico扰动准确预测遗传扰动多模态后果，识别增强子-启动子连接，优于Activity-by-Contact。
conclusion: 为多尺度调控基因组提供一体化生成建模、跨细胞类型泛化和因果机制研究平台。
---

## 摘要
非编码基因组通过一个复杂的多尺度调控系统运作，其中受调控的基因表达与细胞类型特异性的组蛋白修饰、转录因子结合及三维构象密切相关。开发能够整合这些模式以预测和解读调控系统的计算模型仍然具有挑战性。在此，我们提出GenoME，一种基于专家混合（MoE）的生成模型，它利用DNA序列和细胞类型特异性的ATAC-seq信号，预测从碱基对到千碱基分辨率下包含表观基因组学、转录组学和染色质结构的统一基因组图谱。GenoME能够对保留的基因组区域进行多尺度预测，并且关键的是，它能够从单个ATAC-seq输入泛化到预测未见或个体化细胞类型的完整调控景观。我们为GenoME配备了一个计算机扰动框架，该框架能够准确预测遗传扰动的多模态后果，并识别功能性的增强子-启动子连接，其性能优于Activity-by-Contact等专门模型。这些预测还可用于解读细胞类型特异性增强子的转录因子语法。因此，GenoME为多尺度调控基因组的生成建模、跨细胞类型泛化以及因果机制研究提供了一个多功能的一体化平台。

## Abstract
The non-coding genome operates through a complex, multiscale regulatory system where regulated gene expressions are closely associated with cell-type-specific histone modifications, transcription factor binding and 3D conformation. Developing computational models that can integrate these patterns to predict and interpret the regulatory system remains challenging. Here, we present GenoME, a Mixture of Experts (MoE)-based generative model that uses DNA sequence and cell-type-specific ATAC-seq signals to predict a unified genomic profile encompassing epigenomics, transcriptomics, and chromatin architecture at base-pair to kilobase resolutions. GenoME enables multiscale predictions for held-out genomic regions and, critically, generalizes to predict the full regulatory landscape of unseen or individualized cell types from a single ATAC-seq input. We equip GenoME with an in silico perturbation framework that accurately forecasts the multimodal consequences of genetic perturbations and identifies functional enhancer-promoter connections, outperforming specialized models like Activity-by-Contact. These predictions can also be used to decipher the transcription factor grammar of cell-type-specific enhancers. GenoME thus provides a versatile, all-in-one platform for generative modeling, cross-cell-type generalization, and causal mechanistic investigation of the multiscale regulatory genome.