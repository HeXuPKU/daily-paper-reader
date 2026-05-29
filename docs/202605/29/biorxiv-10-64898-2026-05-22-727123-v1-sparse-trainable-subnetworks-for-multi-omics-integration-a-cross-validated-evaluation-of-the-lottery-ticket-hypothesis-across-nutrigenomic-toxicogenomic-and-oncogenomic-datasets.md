---
title: "Sparse, trainable subnetworks for multi-omics integration: a cross-validated evaluation of the Lottery Ticket Hypothesis across nutrigenomic, toxicogenomic, and oncogenomic datasets"
title_zh: 针对多组学整合的稀疏可训练子网络：在营养基因组学、毒物基因组学和肿瘤基因组学数据集上对彩票假说的交叉验证评估
authors: "Miszczak, R."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.22.727123v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 评估彩票假说在多组学集成中的稀疏子网络
tldr: "多组学整合面临表达性与可解释性的权衡，深度神经网络虽强但参数稠密、缺乏特征选择。本研究将彩票假说（LTH）应用于多输入融合多层感知机，在覆盖营养基因组学、毒理基因组学、肿瘤基因组学的8个数据集上，通过25轮迭代幅度剪枝和权重倒带实现99.6%累积稀疏度。在TCGA Pan-Cancer任务中，83%稀疏度的子网络达到84%测试准确率，接近稠密网络的86%；剪枝还在两个TCGA分期任务上提升了准确率。LTH提供了一种领域无关、无需先验的稀疏神经整合方法，与基于图或通路的方法互补。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有多组学整合方法难以兼顾表达性与可解释性，深度学习虽灵活但参数稠密且缺乏特征选择，彩票假说可能提供解决方案。
method: 在8个多组学数据集上，使用迭代幅度剪枝和权重倒带，对多输入融合多层感知机进行25轮剪枝，通过外层5折交叉验证和内层验证选择获胜子网络。
result: "在TCGA Pan-Cancer任务中，83%稀疏度的子网络达84%测试准确率（稠密网络86%）；两个TCGA分期任务上剪枝后准确率提升；网络压缩6至270倍。"
conclusion: 彩票假说可作为多组学数据稀疏神经整合的领域无关通用方法，与现有图或通路约束方法互补。
---

## 摘要
多组学整合，即对同一生物样本收集的两种或多种高维分子数据类型的联合分析，现已成为营养基因组学、毒物基因组学、微生物组研究和疾病基因组学中的标准分析方法。现有方法在表达能力和可解释性之间存在权衡：隐变量方法（如MOFA和DIABLO）产生紧凑且生物学可解释的特征，但假设了严格的线性结构；树集成方法（如随机森林）实现了强大的预测性能，但抵制机制解释；深度神经网络结合了两者的缺点，拥有大量不透明的权重且没有内置特征选择。我探究彩票假说（LTH）——即随机初始化的密集网络包含一个稀疏子网络，当从原始初始化训练时能达到相同精度——是否有助于调和多组学设置中的这种权衡。我在一个多输入融合多层感知机上应用了迭代幅度剪枝与权重回滚，共25轮（累计稀疏度99.6%），涉及跨越四个生物学领域的八个数据集（样本量从40到1,492），采用5折外部交叉验证和内部验证获胜票选择以避免测试集信息泄露。在最大的任务——TCGA泛癌（4类组织起源，n=1,492）中，一个2,952权重的子网络（83%稀疏度）达到了84%±3%的测试准确率，而密集网络为86%±2%。剪枝在两个TCGA分期任务中提高了测试准确率（TCGA-LUAD：51%±1% vs 45%±5%；TCGA-KIRC：50%±4% vs 48%±7%）。网络被压缩了6倍到270倍，同时在明确指定的任务上保留了任务级信号。我建议将LTH作为多组学数据稀疏神经整合的一种领域无关、无先验的选择，与基于图和路径约束的方法互补。

## Abstract
Multi-omics integration, the joint analysis of two or more high-dimensional molecular data types collected on the same biological samples, is now a standard analytical approach across nutrigenomics, toxicogenomics, microbiome research, and disease genomics. Existing methods sit on a trade-off between expressiveness and interpretability: latent-variable methods such as MOFA and DIABLO yield compact, biologically interpretable signatures but assume a restrictive linear structure; tree ensembles such as Random Forests achieve strong predictive performance but resist mechanistic interpretation; deep neural networks combine the drawbacks of both, with large numbers of opaque weights and no built-in feature selection. I ask whether the Lottery Ticket Hypothesis (LTH), the conjecture that a randomly initialised dense network contains a sparse subnetwork that matches its accuracy when trained from the original initialisation, can help reconcile this trade-off in the multi-omics setting. I apply Iterative Magnitude Pruning with weight rewinding for 25 rounds (cumulative sparsity 99.6%) on a multi-input fused multi-layer perceptron across eight datasets spanning four biological domains (n=40 to n=1,492), with 5-fold outer cross-validation and inner-validation winning-ticket selection to avoid test-set leakage. On the largest task, TCGA Pan-Cancer (4-class tissue-of-origin, n=1,492), a 2,952-weight subnetwork (83% sparsity) reached 84% +/- 3% test accuracy compared with 86% +/-2 % for the dense network. Pruning improved test accuracy on two TCGA staging tasks (TCGA-LUAD: 51% {+/-} 1% vs 45% {+/-} 5%; TCGA-KIRC: 50% {+/-} 4% vs 48% {+/-} 7%). Networks compressed by 6x to 270x while retaining task-level signal on well-specified tasks. I suggest LTH as a domain-agnostic, prior-free option for sparse neural integration of multi-omics data, complementary to graph-based and pathway-constrained methods.