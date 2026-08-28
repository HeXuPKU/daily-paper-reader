---
title: "bulk2scDiff: A Pseudobulk-Conditioned Diffusion Model for Bulk-to-Single-Cell RNASeq Generation"
title_zh: bulk2scDiff：一种用于批量到单细胞RNA测序生成的伪批量条件扩散模型
authors: "Xiao, J., Raue, A."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.20.745960v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 单细胞谱的生成模型，与虚拟细胞生成相关
tldr: Bulk RNA测序聚合了细胞群体的转录信号，掩盖了细胞异质性，从bulk推断单细胞表达是欠定逆问题。现有反卷积方法仅能估计细胞类型比例或平均表达，无法解析单个细胞。本文提出bulk2scDiff条件扩散框架，将伪bulk转录组作为条件输入，生成匹配的单细胞表达谱。在乳腺癌和急性髓系白血病数据集上验证，该方法可重建训练样本细胞群，并为留出样本生成生物学合理的细胞群；伪bulk交换对照进一步确认了样本特异性条件生成。研究证明了条件扩散从bulk转录组生成单细胞群的可行性，为临床应用奠定基础。
source: biorxiv
selection_source: fresh_fetch
motivation: Bulk RNA测序掩盖细胞异质性，而现有方法仅估计比例或平均表达，无法解析单细胞水平；从bulk推断单细胞是欠定逆问题，需要新方法。
method: 提出bulk2scDiff，基于条件扩散模型，将单细胞数据聚合的伪bulk作为条件输入，学习生成与条件匹配的单细胞表达谱。
result: 在乳腺癌和AML数据集上，训练样本细胞群被准确重建，留出样本生成生物学合理的细胞群；交换对照验证了各样本由对应伪bulk条件特异性生成。
conclusion: 条件扩散模型可从伪bulk转录组生成单细胞群体，为利用临床bulk RNA-seq推断细胞异质性提供可行基础。
---

## 摘要
批量RNA测序仍是对大型临床队列进行特征分析的主要策略，但它会聚合细胞群体中的转录信号，从而掩盖潜在的细胞异质性。从现有的批量转录组数据中推断这种异质性，可以扩展已经完成特征分析的大型队列研究，但这构成一个欠定的逆问题，因为一个批量图谱可能与多个潜在的细胞群体兼容。现有的计算去卷积方法主要通过估计细胞类型比例或细胞类型平均表达谱来解决这一问题，而不是在单个细胞水平上解析表达。在此，我们提出了bulk2scDiff，一个概念验证性的条件扩散框架，它将批量到单细胞的推断重新表述为从伪批量转录组输入条件生成单细胞表达谱。我们在两个癌症单细胞RNA测序数据集（乳腺癌和急性髓系白血病）上评估了bulk2scDiff，其中从单细胞数据中导出伪批量图谱并用作条件输入，匹配的单细胞群体提供用于受控评估的真实标签。在两种情况下，bulk2scDiff都紧密地重建了训练样本中的群体，并为留出样本生成了生物学上一致的单细胞群体，对反复出现的免疫特征的泛化最为稳定。伪批量交换对照进一步证实了样本特异性条件化，在几乎所有情况下，每个样本对应的伪批量与其观察到的群体一致性最高。总体而言，我们的工作确立了条件扩散从伪批量转录组图谱生成单细胞群体的可行性，为未来使用临床批量RNA测序数据进行评估奠定了基础。

## Abstract
Bulk RNA sequencing remains the predominant profiling strategy for large clinical cohorts, but it aggregates transcriptional signals across cell populations, thereby masking the underlying cellular heterogeneity. Inferring this heterogeneity from existing bulk transcriptomic data could extend large cohort-based studies that have already been profiled, but constitutes an underdetermined inverse problem, as one bulk profile can be compatible with multiple underlying cellular populations. Existing computational deconvolution methods address this problem primarily by estimating cell-type proportions or cell-type-averaged expression profiles rather than resolving expression at the level of individual cells. Here, we present bulk2scDiff, a proof-of-concept conditional diffusion framework that reformulates bulk-to-single-cell inference as conditional generation of single-cell expression profiles from pseudobulk transcriptomic input. We evaluated bulk2scDiff on two cancer single-cell RNA sequencing datasets, breast cancer and acute myeloid leukemia, where pseudobulk profiles were derived from the single-cell data and used as conditioning inputs, with the matched single-cell populations providing ground truth for controlled evaluation. Across both cases, bulk2scDiff closely reconstructed populations from training samples and generated biologically coherent single-cell populations for held-out samples, generalizing most consistently to recurrent immune features. A pseudobulk-swap control further confirmed sample-specific conditioning, with each sample corresponding pseudobulk yielding the closest agreement with its observed population in nearly all cases. Overall, our work establishes the feasibility of conditional diffusion for generating single-cell populations from pseudobulk transcriptomic profiles, providing a foundation for future evaluation with clinical bulk RNA sequencing data.