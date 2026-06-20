---
title: Benchmarking gene expression reconstruction from single-cell latent representations
title_zh: 基于单细胞潜在表示重构基因表达的基准测试
authors: "Fu, X., Klein, D., Antipov, E., Palma, A., Tejada-Lapuerta, A., Bahrami, M., Kummerle, L. B., Lubetzki, M., Casale, F. P., Luecken, M. D., Theis, F. J."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.731445v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 为虚拟细胞模型进行基因表达重建基准测试
tldr: 单细胞转录组学通常用低维潜在表示改善信噪比，但不同表示对基因表达重建的支持缺乏系统评估。本文提出ReconEval基准，在超1亿细胞数据集上评估端到端模型（PCA、自编码器、变分自编码器）和预训练基础模型嵌入的重建性能。结果显示自编码器在低维度重建最优，变分正则化无增益；基础模型重建质量依赖解码器架构和预训练目标。该工作将重建确立为单细胞基础模型的关键评估维度，提升潜在空间建模的生物可解释性。
source: biorxiv
selection_source: fresh_fetch
motivation: 潜在表示的选择通常被视为实现细节，缺乏对其支持基因表达重建能力的系统评估，阻碍了生物学解释。
method: 提出ReconEval基准，在观测和扰动数据集上评估两类潜在表示（端到端模型和预训练嵌入）的统计保真度、生物信号保留及扰动效应。
result: 自编码器在低维度重建最强；变分正则化无改善；冻结基础模型嵌入重建质量依赖解码器；高维PCA在扰动建模中与基础模型相当。
conclusion: 重建能力应作为单细胞基础模型的关键评估指标，简单表示配合适当容量可超越复杂替代方案。
---

## 摘要
单细胞转录组学通常通过低维潜在表示进行建模，以提高数据的信噪比。这些表示支撑着数据整合、细胞状态发现和扰动预测，应用范围从大规模器官图谱到潜在轨迹建模。最近的虚拟细胞方法进一步利用这些表示来预测细胞响应，即潜在空间中的分布偏移。这些应用最终都需要从潜在空间忠实地重构基因表达，以实现生物学解释，从而对预测的扰动或批次校正细胞进行基因水平分析。然而，表示选择通常被视为实现细节而非主要建模决策，缺乏对潜在表示支持基因表达重构效果的系统性评估。在此，我们介绍ReconEval，一个用于评估单细胞潜在空间基因表达重构的基准测试。我们对两类潜在表示进行基准测试：端到端训练的模型（如PCA、自编码器和变分自编码器），以及预训练的单细胞基础模型嵌入结合新训练的解码器。重构评估既直接进行，也在潜在空间扰动预测之后进行。在总计超过1亿个细胞的扰动和观察数据集中，我们的指标套件量化了统计保真度；生物信号保留，包括差异表达、共表达、细胞周期结构、细胞因子反应和通路活性；以及扰动特异性效应。我们发现，在低维下，自编码器实现了最强的独立重构，而变分正则化并未改善重构的泛化能力。冻结的基础模型嵌入保留了可恢复的基因水平信息，重构质量强烈依赖于解码器架构和预训练目标。在潜在扰动建模中，高维PCA与基础模型嵌入相当，而低维自编码器嵌入对于基于流的生成模型是最优的。总体而言，重构关键取决于表示与下游模型之间的相互作用，在适当容量的情况下，更简单的表示可以胜过复杂的替代方案。我们的基准测试将重构确立为单细胞基础模型的关键评估轴。我们预期这将提高潜在空间建模的生物学可解释性，这是未来虚拟细胞模型能够被领域专家验证并扎根于生物学的先决条件。

## Abstract
Single-cell transcriptomics is typically modeled in low-dimensional latent representations that improve the signal-to-noise ratio of the data. Such representations underpin data integration, cell state discovery, and perturbation prediction, with applications ranging from large-scale organ atlases to latent trajectory modeling. Recent virtual cell approaches further leverage these representations to predict cellular responses as distributional shifts in latent space. Each of these applications ultimately requires faithful gene expression reconstruction from latent spaces for biological interpretation, enabling gene-level analysis of predicted perturbed or batch-corrected cells. Yet representation choice is typically treated as an implementation detail rather than a primary modeling decision, with no systematic evaluation of how well latent representations support gene expression reconstruction. Here, we introduce ReconEval, a benchmark for evaluating gene expression reconstruction from single-cell latent spaces. We benchmark two classes of latent representations: end-to-end trained models such as PCA, autoencoders, and variational autoencoders, and pretrained single-cell foundation model embeddings coupled to newly trained decoders. Reconstruction is evaluated both directly and after latent-space perturbation prediction. Across perturbational and observational datasets totaling over 100 million cells, our metric suite quantifies statistical fidelity; biological signal preservation, including differential expression, coexpression, cell-cycle structure, cytokine response and pathway activity; and perturbation-specific effects. We find that autoencoders achieve the strongest stand-alone reconstruction at low dimensionality, while variational regularization does not improve generalization in reconstruction. Frozen foundation model embeddings retain recoverable gene-level information, with reconstruction quality depending strongly on decoder architecture and pretraining objective. In latent perturbation modeling, high-dimensional PCA matches foundation model embeddings, while low-dimensional AE embeddings are optimal for flow-based generative models. Overall, reconstruction depends critically on the interplay between representation and downstream model, and simpler representations can outperform complex alternatives given appropriate capacity. Our benchmark establishes reconstruction as a critical evaluation axis for single-cell foundation models. We envision it improving the biological interpretability of latent-space modeling, a prerequisite for future virtual cell models to be validated by domain experts and grounded in biology.