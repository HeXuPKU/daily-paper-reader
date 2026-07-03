---
title: Scalable and rare-variant aware genome inference across the 1kGP cohort
title_zh: 可扩展且罕见变异感知的基因组推断：面向1kGP群体
authors: "Ebler, J., Prodanov, T., Blair, A., Lee, S. K., Ebert, P., Human Pangenome Reference Consortium,, Paten, B., Marschall, T."
date: 2026-07-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735275v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 稀有变异感知的基因组推断用于GWAS
tldr: 基于pangenome图的PanGenie无法检测稀有变异且限于254个单倍型。为此引入单倍型采样步骤，利用样本特异性k-mers减少计算量，使速度提升十二倍、内存降低1.4倍。同时开发polishing流程，用低覆盖ONT数据修正基因型错误并纳入稀有突变。在1000 Genomes Project的3202个样本中应用，达到中位QV 46，并贡献1934个polished单倍型序列作为社区资源。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有PanGenie无法检测稀有变异且受限于单倍型数量，需开发可扩展且感知稀有变异的方法。
method: 引入基于样本特异性k-mers的单倍型采样减少计算量，再通过polishing流程利用低覆盖ONT数据修正错误并纳入稀有突变。
result: 在3202个样本中实现中位QV 46，提供1934个polished单倍型序列。
conclusion: 该方法实现了大规模、稀有变异感知的基因组推断，为群体遗传学研究提供高质量资源。
---

## 摘要
由单倍型解析的从头组装构建的泛基因组图能够准确分析遗传变异。基于短读段的工具PanGenie能够高效地对大规模队列中发现的变异进行基因分型，并在结构变异（SV）上优于线性参考方法。然而，它无法检测图中不存在的新变异，遗漏了许多罕见SV（等位基因频率<1%），且仅适用于包含254个单倍型的图。首先，我们引入了单倍型采样步骤，在基因分型前使用样本特异性k-mer减少单倍型数量，在30x覆盖度下将运行时间降低12倍，内存使用降低1.4倍。其次，我们提出了一个校正流程，用于纠正从PanGenie基因型推断的单倍型中的残留错误，并整合罕见和私有突变。我们对来自1000 Genomes Project的3,202个样本进行基因分型，并使用低覆盖度ONT数据（967个样本）进行校正。我们实现了46的中位QV值，并提供了1,934个校正后的单倍型序列作为社区资源。

## Abstract
Pangenome graphs built from haplotype-resolved de novo assemblies enable accurate analysis of genetic variation. The short-read-based tool PanGenie efficiently genotypes variants discovered in a pangenome across large cohorts and outperforms linear reference-based methods for structural variants (SVs). However, it cannot detect novel variants absent from the graph, missing many rare SVs (allele frequency <1%) and was limited to graphs with 254 haplotypes. First, we introduce a haplotype sampling step that reduces the number of haplotypes using sample-specific k-mers before genotyping, decreasing runtime twelvefold and memory usage 1.4-fold at 30x coverage. Second, we present a polishing workflow that corrects residual errors in haplotypes inferred from PanGenie genotypes and incorporates rare and private mutations. We genotype 3,202 samples from the 1000 Genomes Project and use low-coverage ONT data (967 samples) for polishing. We achieve a median QV of 46 and provide the 1,934 polished haplotype sequences as a community resource.