---
title: Benchmarking gene expression reconstruction from single-cell latent representations
title_zh: 从单细胞潜在表示重建基因表达的基准测试
authors: "Fu, X., Klein, D., Antipov, E., Palma, A., Tejada-Lapuerta, A., Bahrami, M., Kummerle, L. B., Lubetzki, M., Casale, F. P., Luecken, M. D., Theis, F. J."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.731445v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 基准测试从潜在表示重建基因表达用于虚拟细胞模型
tldr: 单细胞转录组学常用低维潜在表示，但缺乏对基因表达重建能力的系统评估。本文提出ReconEval基准，评估PCA、自编码器、变分自编码器及预训练基础模型嵌入等表示的重建性能。结果显示自编码器在低维度下重建最强，变分正则化不改善重建；预训练嵌入的基因信息可恢复性依赖解码器；高维PCA在扰动建模中媲美基础模型。该基准将重建确立为评估单细胞基础模型的关键维度，提升潜在空间建模的生物学可解释性。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有单细胞潜在表示选择缺乏对基因表达重建能力的系统评估，阻碍生物学解释。
method: 提出ReconEval基准，评估PCA、自编码器、变分自编码器及预训练基础模型嵌入的重建性能，包括直接重建和扰动预测后重建。
result: 自编码器在低维下重建最优；变分正则化不改善重建；预训练嵌入重建质量依赖解码器；高维PCA在扰动建模中媲美基础模型。
conclusion: 重建性能取决于表示与下游模型交互，简单表示可能优于复杂模型，重建应成为单细胞基础模型评估标准。
---

## 摘要
单细胞转录组学通常建模为低维潜在表示，以提高数据的信噪比。这类表示支撑着数据整合、细胞状态发现和扰动预测，应用范围从大规模器官图谱到潜在轨迹建模。最近的虚拟细胞方法进一步利用这些表示，将细胞反应预测为潜在空间中的分布偏移。这些应用最终都需要从潜在空间忠实重建基因表达以进行生物学解释，从而能够对预测的扰动或批次校正细胞进行基因水平分析。然而，表示的选择通常被视为实现细节而非主要建模决策，缺乏对潜在表示支持基因表达重建程度的系统评估。在此，我们引入ReconEval，一个用于评估从单细胞潜在空间重建基因表达的基准。我们基准测试了两类潜在表示：端到端训练的模型，如PCA、自编码器和变分自编码器，以及预训练的单细胞基础模型嵌入结合新训练的解码器。重建评估既直接进行，也在潜在空间扰动预测后进行。在总计超过1亿个细胞的扰动和观察数据集中，我们的指标套件量化了统计保真度；生物信号保留，包括差异表达、共表达、细胞周期结构、细胞因子反应和通路活性；以及扰动特异性效应。我们发现自编码器在低维度下实现了最强的独立重建，而变分正则化并未改善重建的泛化性能。冻结的基础模型嵌入保留了可恢复的基因水平信息，重建质量强烈依赖于解码器架构和预训练目标。在潜在扰动建模中，高维PCA与基础模型嵌入相当，而低维自编码器嵌入对于基于流的生成模型是最优的。总体而言，重建关键取决于表示与下游模型之间的相互作用，在适当容量的情况下，更简单的表示可以胜过复杂的替代方案。我们的基准将重建确立为单细胞基础模型的关键评估轴。我们期望它能提高潜在空间建模的生物学可解释性，这是未来虚拟细胞模型获得领域专家验证并扎根于生物学的先决条件。

## Abstract
Single-cell transcriptomics is typically modeled in low-dimensional latent representations that improve the signal-to-noise ratio of the data. Such representations underpin data integration, cell state discovery, and perturbation prediction, with applications ranging from large-scale organ atlases to latent trajectory modeling. Recent virtual cell approaches further leverage these representations to predict cellular responses as distributional shifts in latent space. Each of these applications ultimately requires faithful gene expression reconstruction from latent spaces for biological interpretation, enabling gene-level analysis of predicted perturbed or batch-corrected cells. Yet representation choice is typically treated as an implementation detail rather than a primary modeling decision, with no systematic evaluation of how well latent representations support gene expression reconstruction. Here, we introduce ReconEval, a benchmark for evaluating gene expression reconstruction from single-cell latent spaces. We benchmark two classes of latent representations: end-to-end trained models such as PCA, autoencoders, and variational autoencoders, and pretrained single-cell foundation model embeddings coupled to newly trained decoders. Reconstruction is evaluated both directly and after latent-space perturbation prediction. Across perturbational and observational datasets totaling over 100 million cells, our metric suite quantifies statistical fidelity; biological signal preservation, including differential expression, coexpression, cell-cycle structure, cytokine response and pathway activity; and perturbation-specific effects. We find that autoencoders achieve the strongest stand-alone reconstruction at low dimensionality, while variational regularization does not improve generalization in reconstruction. Frozen foundation model embeddings retain recoverable gene-level information, with reconstruction quality depending strongly on decoder architecture and pretraining objective. In latent perturbation modeling, high-dimensional PCA matches foundation model embeddings, while low-dimensional AE embeddings are optimal for flow-based generative models. Overall, reconstruction depends critically on the interplay between representation and downstream model, and simpler representations can outperform complex alternatives given appropriate capacity. Our benchmark establishes reconstruction as a critical evaluation axis for single-cell foundation models. We envision it improving the biological interpretability of latent-space modeling, a prerequisite for future virtual cell models to be validated by domain experts and grounded in biology.