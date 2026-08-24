---
title: "bulk2scDiff: A Pseudobulk-Conditioned Diffusion Model for Bulk-to-Single-Cell RNASeq Generation"
title_zh: bulk2scDiff：用于批量到单细胞RNA测序生成的伪批量条件扩散模型
authors: "Xiao, J., Raue, A."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.20.745960v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 基于扩散模型的批量到单细胞RNA-seq生成方法，直接支撑虚拟细胞模型生成。
tldr: bulk RNA测序聚合了细胞群的转录信号，掩盖了细胞异质性，从bulk数据解析单细胞是欠定逆问题。现有方法多局限于估计细胞类型比例或平均表达，难以达到单细胞分辨率。本文提出bulk2scDiff，一种以伪bulk表达为条件的扩散模型，将bulk到单细胞推断转化为条件生成任务，并在乳腺癌和急性髓系白血病数据上验证。模型能重建训练样本的细胞群体，对留出样本生成生物学一致的群体，且对免疫特征泛化最稳定；伪bulk交换对照进一步确认了样本特异性条件作用。该工作证明了条件扩散模型从bulk转录组生成单细胞群体的可行性，为后续临床bulk数据应用奠定基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 从bulk转录组推断单细胞异质性属于欠定逆问题，现有方法仅估计细胞比例或平均表达，无法达到单细胞分辨率。
method: 提出bulk2scDiff，以伪bulk表达为条件输入，训练条件扩散模型生成单细胞表达谱，并用匹配单细胞数据作为真值进行受控评估。
result: 在乳腺癌和急性髓系白血病数据上，模型可重建训练样本群体，对留出样本生成生物学一致群体，免疫特征泛化最佳；交换对照确认样本特异性。
conclusion: 证明条件扩散模型可从bulk转录组生成单细胞群体，为临床bulk数据推断细胞异质性提供了可行基础。
---

## 摘要
批量RNA测序仍是对大型临床队列进行概况分析的主要策略，但它会聚合细胞群体间的转录信号，从而掩盖了潜在的细胞异质性。从已有的批量转录组数据中推断这种异质性，可以扩展已经完成概况分析的大型队列研究，但这构成了一个欠定的逆问题，因为一个批量概况可能与多个潜在细胞群体相容。现有的计算去卷积方法主要通过估计细胞类型比例或细胞类型平均表达谱来解决此问题，而非在单个细胞水平上解析表达。在此，我们提出了bulk2scDiff，一个概念验证的条件扩散框架，它将批量到单细胞的推断重新表述为从伪批量转录组输入条件生成单细胞表达谱。我们在两个癌症单细胞RNA测序数据集（乳腺癌和急性髓系白血病）上评估了bulk2scDiff，其中伪批量概况来源于单细胞数据并用作条件输入，匹配的单细胞群体为受控评估提供了真实值。在这两种情况下，bulk2scDiff都能从训练样本中紧密重建群体，并针对保留样本生成生物学上连贯的单细胞群体，最一致地泛化到复发性免疫特征。伪批量交换对照进一步确认了样本特异性条件作用，在几乎所有情况下，每个样本对应的伪批量与其观察到的群体达成最接近的一致。总体而言，我们的工作确立了从伪批量转录组概况生成单细胞群体的条件扩散可行性，为未来使用临床批量RNA测序数据进行评估奠定了基础。

## Abstract
Bulk RNA sequencing remains the predominant profiling strategy for large clinical cohorts, but it aggregates transcriptional signals across cell populations, thereby masking the underlying cellular heterogeneity. Inferring this heterogeneity from existing bulk transcriptomic data could extend large cohort-based studies that have already been profiled, but constitutes an underdetermined inverse problem, as one bulk profile can be compatible with multiple underlying cellular populations. Existing computational deconvolution methods address this problem primarily by estimating cell-type proportions or cell-type-averaged expression profiles rather than resolving expression at the level of individual cells. Here, we present bulk2scDiff, a proof-of-concept conditional diffusion framework that reformulates bulk-to-single-cell inference as conditional generation of single-cell expression profiles from pseudobulk transcriptomic input. We evaluated bulk2scDiff on two cancer single-cell RNA sequencing datasets, breast cancer and acute myeloid leukemia, where pseudobulk profiles were derived from the single-cell data and used as conditioning inputs, with the matched single-cell populations providing ground truth for controlled evaluation. Across both cases, bulk2scDiff closely reconstructed populations from training samples and generated biologically coherent single-cell populations for held-out samples, generalizing most consistently to recurrent immune features. A pseudobulk-swap control further confirmed sample-specific conditioning, with each sample corresponding pseudobulk yielding the closest agreement with its observed population in nearly all cases. Overall, our work establishes the feasibility of conditional diffusion for generating single-cell populations from pseudobulk transcriptomic profiles, providing a foundation for future evaluation with clinical bulk RNA sequencing data.