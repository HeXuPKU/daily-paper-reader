---
title: "ANCHOR: haplotype-aware allelic and isoform inference from single-cell long-read RNA sequencing with de novo variant calling"
title_zh: "ANCHOR: 基于从头变异检测的单细胞长读长RNA测序中单倍型感知的等位基因和异构体推断"
authors: "Fu, Z.-C., Zhang, C., Yan, Y., Xu, Y., Yin, X., Tao, T., Lu, P., Liang, Y., Wu, H., Cui, W., Hou, R., Chen, X., Ke, Y., Li, Y., Chen, Z.-J., Huang, T., Wu, K., Yuan, S."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.730656v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 长读长RNA测序的单倍型感知变异检测和等位基因推断，整合功能基因组学与GWAS
tldr: 单细胞长读长RNA测序的等位基因分析面临覆盖稀疏、参考偏倚等挑战。ANCHOR通过签名图变异调用、配对隐马尔可夫模型和beta-binomial聚合，实现单倍型感知的从头变异检测和等位基因量化。在人类基准中优于现有方法，在小鼠胚胎数据中鉴定出细胞类型特异性印记和拮抗性母系偏倚Sgce异构体。为二倍体单细胞长读长转录组提供了通用分析框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法无法有效处理单细胞长读长RNA测序的稀疏覆盖和参考偏倚，缺乏单倍型感知的等位基因与异构体解析能力。
method: ANCHOR联合签名图变异调用、配对隐马尔可夫模型与beta-binomial UMI聚合，实现从头表达变异发现、分子单倍型分配和异构体等位基因量化。
result: 在人类单细胞数据中提升变异调用性能并降低深度驱动的假阳性；在小鼠胚胎数据中解析细胞类型特异性印记，发现母系偏倚Sgce异构体。
conclusion: ANCHOR为单细胞长读长转录组提供广泛的等位基因和异构体解析分析框架，无需预先生成基因型。
---

## 摘要
长读长RNA测序能够对转录组进行单倍型和异构体分辨的等位基因分析，但由于稀疏覆盖度、测序错误、不完整的变异信息以及参考偏差的转录本分配，将这一能力扩展到单细胞和不同细胞类型在计算上仍具有挑战性。在此，我们提出ANCHOR，一个用于单细胞长读长RNA测序的单倍型感知框架，可进行从头表达的变异发现、分子水平单倍型分配和异构体分辨的等位基因定量。ANCHOR结合了符号图变异检测器、配对隐马尔可夫建模和β-二项UMI聚合，以推断基因和剪接分辨异构体的亲本等位基因计数，无需预先存在的分型基因型或深度学习。在人类单细胞长读长RNA基准测试中，ANCHOR在单细胞和低至中等覆盖度下，相比测试的长读长RNA检测器提高了变异检测性能，其β-二项模型减少了等位基因特异性表达测试中深度驱动的假阳性。应用于来自小鼠原肠胚形成过程中相互杂交的新产生的单细胞长读长RNA-seq数据，ANCHOR解析了细胞类型和异构体特异性亲本印记，并识别出一个拮抗的母亲偏向的Sgce异构体。ANCHOR为二倍体单细胞长读长转录组的等位基因和异构体分辨分析提供了一个通用框架。

## Abstract
Long-read RNA sequencing enables haplotype- and isoform-resolved allelic analysis of transcriptomes, yet extending this capability to single cells and distinct cell types remains computationally challenging due to sparse coverage, sequencing errors, incomplete variant information, and reference-biased transcript assignment. Here we present ANCHOR, a haplotype-aware framework for single-cell long-read RNA sequencing that performs de novo expressed-variant discovery, molecule-level haplotype assignment and isoform-resolved allelic quantification. ANCHOR combines a signed-graph variant caller, pair hidden Markov modelling and beta-binomial UMI aggregation to infer parental allele counts for genes and splice-resolved isoforms, without requiring a pre-existing phased genotype or deep learning. In human single-cell long-read RNA benchmarks, ANCHOR improved variant-calling performance over tested long-read RNA callers at single-cell and low-to-moderate coverage, and its beta-binomial model reduced depth-driven false positives in allele-specific expression testing. Applied to newly generated single-cell long-read RNA-seq data from reciprocal mouse crosses during gastrulation, ANCHOR resolved cell-type- and isoform-specific parent-of-origin imprinting and identified an antagonistic maternally biased Sgce isoform. ANCHOR provides a general framework for allele- and isoform-resolved analysis of diploid single-cell long-read transcriptomes.