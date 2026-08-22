---
title: "bulk2scDiff: A Pseudobulk-Conditioned Diffusion Model for Bulk-to-Single-Cell RNASeq Generation"
title_zh: bulk2scDiff：一种用于批量到单细胞RNA测序生成的伪批量条件扩散模型
authors: "Xiao, J., Raue, A."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.20.745960v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 面向单细胞转录组生成的扩散模型，与虚拟细胞建模相关
tldr: 批量RNA测序聚合并掩盖细胞异质性，从已有bulk数据推断单细胞表达构成欠定逆问题。现有方法多估计细胞类型比例或平均表达，难以还原单细胞层面。本文提出bulk2scDiff，一种基于条件扩散的生成框架，以伪bulk转录组为条件生成单细胞表达谱。在乳腺癌和急性髓系白血病数据上验证，模型能重构训练集种群并为保留样本生成生物学合理的单细胞群体，样本特异性条件控制进一步确认了生成可靠性。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有bulk转录组数据无法直接揭示细胞异质性，而传统反卷积仅估计细胞类型比例或平均表达，缺乏单细胞分辨率的推断能力。
method: 提出bulk2scDiff条件扩散模型，将bulk-to-single-cell推断重构为以伪bulk转录组为条件的单细胞表达谱生成问题。
result: 在乳腺癌和AML数据上，模型能重构训练样本种群，并对保留样本生成生物学一致的单细胞群体，尤其在免疫特征上泛化稳定；伪bulk交换对照验证了样本特异性。
conclusion: 该工作证明条件扩散可从伪bulk转录组生成单细胞群体，为未来应用于临床bulk RNA-seq数据奠定了基础。
---

## 摘要
批量RNA测序仍是大规模临床队列的主要分析策略，但它聚合了细胞群中的转录信号，从而掩盖了潜在的细胞异质性。从已有的批量转录组数据中推断这种异质性，可以扩展已经完成分析的大型队列研究，但这构成一个欠定的逆问题，因为一个批量谱可能与多个潜在的细胞群兼容。现有的计算反卷积方法主要通过估计细胞类型比例或细胞类型平均表达谱来解决这一问题，而非在单细胞水平上解析表达。在这里，我们提出了bulk2scDiff，一个概念验证性的条件扩散框架，它将批量到单细胞的推断重新表述为从伪批量转录组输入条件生成单细胞表达谱。我们在两个癌症单细胞RNA测序数据集（乳腺癌和急性髓系白血病）上评估了bulk2scDiff，其中伪批量谱由单细胞数据派生并用作条件输入，匹配的单细胞群体为受控评估提供真实值。在两种情况下，bulk2scDiff都能从训练样本中紧密重建细胞群，并为保留样本生成生物学上连贯的单细胞群，对反复出现的免疫特征具有最一致的外推能力。伪批量交换对照进一步确认了样本特异性条件处理，在几乎所有情况下，每个样本对应的伪批量与其观察到的群体最接近。总体而言，我们的工作确立了从伪批量转录组谱生成单细胞群体的条件扩散的可行性，为未来使用临床批量RNA测序数据进行评估奠定了基础。

## Abstract
Bulk RNA sequencing remains the predominant profiling strategy for large clinical cohorts, but it aggregates transcriptional signals across cell populations, thereby masking the underlying cellular heterogeneity. Inferring this heterogeneity from existing bulk transcriptomic data could extend large cohort-based studies that have already been profiled, but constitutes an underdetermined inverse problem, as one bulk profile can be compatible with multiple underlying cellular populations. Existing computational deconvolution methods address this problem primarily by estimating cell-type proportions or cell-type-averaged expression profiles rather than resolving expression at the level of individual cells. Here, we present bulk2scDiff, a proof-of-concept conditional diffusion framework that reformulates bulk-to-single-cell inference as conditional generation of single-cell expression profiles from pseudobulk transcriptomic input. We evaluated bulk2scDiff on two cancer single-cell RNA sequencing datasets, breast cancer and acute myeloid leukemia, where pseudobulk profiles were derived from the single-cell data and used as conditioning inputs, with the matched single-cell populations providing ground truth for controlled evaluation. Across both cases, bulk2scDiff closely reconstructed populations from training samples and generated biologically coherent single-cell populations for held-out samples, generalizing most consistently to recurrent immune features. A pseudobulk-swap control further confirmed sample-specific conditioning, with each sample corresponding pseudobulk yielding the closest agreement with its observed population in nearly all cases. Overall, our work establishes the feasibility of conditional diffusion for generating single-cell populations from pseudobulk transcriptomic profiles, providing a foundation for future evaluation with clinical bulk RNA sequencing data.