---
title: Scalable and rare-variant aware genome inference across the 1kGP cohort
title_zh: 跨1kGP队列的可扩展及罕见变异感知基因组推断
authors: "Ebler, J., Prodanov, T., Blair, A., Lee, S. K., Ebert, P., Human Pangenome Reference Consortium,, Paten, B., Marschall, T."
date: 2026-07-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735275v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 可扩展的稀有变异感知基因组推断方法，涉及GWAS统计方法
tldr: 基于短读的PanGenie工具可高效基因分型但无法检测新变异且受限于二百五十四单倍型。我们引入单倍型采样利用样本特异性k-mer将单倍型减少十二倍内存降一点四倍；再通过抛光流程纠正推断错误并整合稀有及私有突变。在千基因组项目三千两百零二样本上基因分型，用低覆盖ONT数据对九百六十七样本抛光，获得中位碱基质量值四十六，并发布一千九百三十四个抛光单倍型序列作为社区资源。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有PanGenie无法检测新变异且单倍型规模仅二百五十四，运行效率低，难以应用于大型队列的稀有变异发现。
method: 引入单倍型采样步骤，利用样本特异性k-mer减少单倍型十二倍；再通过抛光流程纠正推断错误并纳入稀有和私有突变。
result: 在千基因组项目三千二百零二样本上基因分型，运行时间降十二倍，中位QV达四十六，发布一千九百三十四个抛光单倍型。
conclusion: 本研究实现了可扩展的稀有变异感知全基因组推断，性能优异，并提供了大规模抛光单倍型序列作为社区资源。
---

## 摘要
基于单倍型解析的从头组装构建的泛基因组图能够准确分析遗传变异。基于短读段的工具PanGenie可高效地对大型队列中泛基因组发现的变异进行基因分型，并且在结构变异（SV）方面优于基于线性参考的方法。然而，它无法检测图中不存在的新变异，遗漏了许多罕见SV（等位基因频率<1%），并且仅限于包含254个单倍型的图。首先，我们引入了一个单倍型采样步骤，该步骤在基因分型前使用样本特异性k-mer减少单倍型数量，在30x覆盖度下将运行时间降低12倍，内存使用降低1.4倍。其次，我们提出了一种抛光流程，用于校正从PanGenie基因分型推断出的单倍型中的残留错误，并纳入罕见和私有突变。我们对来自千人基因组计划的3,202个样本进行基因分型，并使用低覆盖度ONT数据（967个样本）进行抛光。我们实现了中位数QV为46，并提供了1,934条抛光后的单倍型序列作为社区资源。

## Abstract
Pangenome graphs built from haplotype-resolved de novo assemblies enable accurate analysis of genetic variation. The short-read-based tool PanGenie efficiently genotypes variants discovered in a pangenome across large cohorts and outperforms linear reference-based methods for structural variants (SVs). However, it cannot detect novel variants absent from the graph, missing many rare SVs (allele frequency <1%) and was limited to graphs with 254 haplotypes. First, we introduce a haplotype sampling step that reduces the number of haplotypes using sample-specific k-mers before genotyping, decreasing runtime twelvefold and memory usage 1.4-fold at 30x coverage. Second, we present a polishing workflow that corrects residual errors in haplotypes inferred from PanGenie genotypes and incorporates rare and private mutations. We genotype 3,202 samples from the 1000 Genomes Project and use low-coverage ONT data (967 samples) for polishing. We achieve a median QV of 46 and provide the 1,934 polished haplotype sequences as a community resource.