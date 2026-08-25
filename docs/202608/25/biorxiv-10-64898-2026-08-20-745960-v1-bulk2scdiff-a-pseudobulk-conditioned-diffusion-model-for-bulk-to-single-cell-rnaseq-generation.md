---
title: "bulk2scDiff: A Pseudobulk-Conditioned Diffusion Model for Bulk-to-Single-Cell RNASeq Generation"
title_zh: bulk2scDiff：用于批量到单细胞RNA测序生成的伪批量条件扩散模型
authors: "Xiao, J., Raue, A."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.20.745960v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 基于扩散模型的bulk到单细胞转录组生成，与虚拟细胞模型生成相关
tldr: 批量RNA测序在大型临床队列中广泛使用，但会掩盖细胞异质性。从批量数据推断单细胞表达是欠定逆问题，现有方法多估计细胞类型比例或平均表达。本文提出bulk2scDiff，一种基于条件扩散的框架，将批量到单细胞的推断转化为由伪bulk输入生成单细胞表达谱的条件生成任务。在乳腺癌和急性髓系白血病两个数据集上，该方法能重建训练样本群体并为留出样本生成生物学一致的单细胞群体，验证了条件扩散在该任务上的可行性。
source: biorxiv
selection_source: fresh_fetch
motivation: 批量RNA测序掩盖细胞异质性，现有反卷积方法无法解析到单细胞水平，需新方法从批量数据生成单细胞表达谱。
method: 提出bulk2scDiff，以伪bulk转录组为条件输入，通过条件扩散模型生成匹配的单细胞表达谱。
result: 在乳腺癌和AML数据中，bulk2scDiff精确重建训练群体，对留出样本生成一致群体，伪bulk对照验证了样本特异性。
conclusion: 证明了条件扩散从批量转录组生成单细胞群体的可行性，为未来临床应用奠定基础。
---

## 摘要
批量RNA测序仍然是大规模临床队列的主要分析策略，但它会聚合细胞群体中的转录信号，从而掩盖潜在的细胞异质性。从已有的批量转录组数据推断这种异质性可以扩展已经完成分析的大型队列研究，但这构成了一个欠定的逆问题，因为一个批量谱图可能与多个潜在的细胞群体兼容。现有的计算去卷积方法主要通过估计细胞类型比例或细胞类型平均表达谱来解决此问题，而非在单个细胞水平上解析表达。在此，我们提出了bulk2scDiff，一个概念验证的条件扩散框架，将批量到单细胞的推断重新表述为从伪批量转录组输入条件生成单细胞表达谱。我们在两个癌症单细胞RNA测序数据集（乳腺癌和急性髓系白血病）上评估了bulk2scDiff，其中伪批量谱图源自单细胞数据并用作条件输入，匹配的单细胞群体提供真值用于受控评估。在两种情况下，bulk2scDiff都能紧密重建训练样本中的群体，并为保留样本生成生物学上连贯的单细胞群体，最一致地泛化到复发性免疫特征。伪批量交换对照进一步确认了样本特异性条件，在几乎所有情况下，每个样本对应的伪批量都与其观察到的群体最一致。总体而言，我们的工作证明了从伪批量转录组谱图生成单细胞群体的条件扩散的可行性，为未来使用临床批量RNA测序数据进行评估奠定了基础。

## Abstract
Bulk RNA sequencing remains the predominant profiling strategy for large clinical cohorts, but it aggregates transcriptional signals across cell populations, thereby masking the underlying cellular heterogeneity. Inferring this heterogeneity from existing bulk transcriptomic data could extend large cohort-based studies that have already been profiled, but constitutes an underdetermined inverse problem, as one bulk profile can be compatible with multiple underlying cellular populations. Existing computational deconvolution methods address this problem primarily by estimating cell-type proportions or cell-type-averaged expression profiles rather than resolving expression at the level of individual cells. Here, we present bulk2scDiff, a proof-of-concept conditional diffusion framework that reformulates bulk-to-single-cell inference as conditional generation of single-cell expression profiles from pseudobulk transcriptomic input. We evaluated bulk2scDiff on two cancer single-cell RNA sequencing datasets, breast cancer and acute myeloid leukemia, where pseudobulk profiles were derived from the single-cell data and used as conditioning inputs, with the matched single-cell populations providing ground truth for controlled evaluation. Across both cases, bulk2scDiff closely reconstructed populations from training samples and generated biologically coherent single-cell populations for held-out samples, generalizing most consistently to recurrent immune features. A pseudobulk-swap control further confirmed sample-specific conditioning, with each sample corresponding pseudobulk yielding the closest agreement with its observed population in nearly all cases. Overall, our work establishes the feasibility of conditional diffusion for generating single-cell populations from pseudobulk transcriptomic profiles, providing a foundation for future evaluation with clinical bulk RNA sequencing data.