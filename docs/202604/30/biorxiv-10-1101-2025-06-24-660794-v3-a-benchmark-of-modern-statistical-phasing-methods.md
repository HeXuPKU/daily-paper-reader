---
title: A Benchmark of Modern Statistical Phasing Methods
title_zh: 现代统计相位估计方法的基准测试
authors: "Beck, A. T., Kang, H. M., Zoellner, S."
date: 2026-04-23
pdf: "https://www.biorxiv.org/content/10.1101/2025.06.24.660794v3.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 现代统计相位推断方法的基准测试
tldr: 本研究利用男性X染色体序列生成的合成二倍体，对Beagle 5.4、SHAPEIT 4和Eagle v2.4.1三种主流统计相位推断方法进行了基准测试。研究发现各方法的错误率高度相关，但错误类型存在差异：Eagle v2.4.1的转换错误较多，而SHAPEIT 4的翻转错误比例更高。此外，CpG位点和稀有变异位点的错误率显著增加。该研究为评估和选择基因组相位推断工具提供了重要参考。
source: biorxiv
selection_source: fresh_fetch
motivation: 由于严谨评估相位推断准确性存在挑战，本研究旨在通过新方法对主流统计相位推断工具进行基准测试。
method: 利用男性X染色体序列构建合成二倍体，对比评估了Beagle 5.4、SHAPEIT 4和Eagle v2.4.1的性能。
result: 研究发现Eagle v2.4.1的转换错误率较高，而SHAPEIT 4的翻转错误率较高，且错误在CpG和稀有变异位点富集。
conclusion: 该基准测试揭示了不同相位推断方法的误差模式差异，为基因组研究中工具的选择和误差分析提供了依据。
---

## 摘要
现代统计相位估计（phasing）方法能够高效且准确地推断大规模基因组样本中的单倍型相位，其性能对于下游分析至关重要。然而，严格评估相位估计的准确性仍然具有挑战性。在本文中，我们展示了利用男性 X 染色体序列生成的合成二倍体，对三种常用的相位估计方法（Beagle 5.4、SHAPEIT 4 和 Eagle v2.4.1）进行基准测试和比较。我们的评估显示，所有方法的错误率高度相关，尽管我们在不同错误类型中观察到各方法之间存在明显的差异。具体而言，Eagle v2.4.1 的特点是转换错误（switch errors）频率较高，而 SHAPEIT 4 则表现出较高的翻转错误（flip errors，即双转换错误）率。这些模式在不同人群中是一致的。此外，我们观察到错误在 CpG 位点和罕见变异位点均有富集，尤其是翻转错误。在常染色体三人家庭（trio）数据中验证这些结果时，我们观察到各方法与错误模式之间存在类似的趋势，尽管翻转错误率有所增加，这种差异可能受到基因型错误的影响。

## Abstract
Modern statistical phasing methods efficiently and accurately infer haplotype phase in large genomic samples, and their performance is critical for downstream analyses. However, rigorously evaluating phasing accuracy remains challenging. Here we demonstrate the use of synthetic diploids generated from male X chromosome sequences to benchmark and compare three commonly-used phasing methods: Beagle 5.4, SHAPEIT 4, and Eagle v2.4.1. Our evaluation reveals highly correlated error rates across all methods, although we observe distinct variation among methods within error types. Specifically, Eagle v2.4.1 is characterized by a higher frequency of switch errors, whereas SHAPEIT 4 displays a higher rate of flip (double-switch) errors. These patterns are consistent across diverse populations. Additionally, we observe an enrichment of errors at both CpG sites and rare variant sites, particularly for flip errors. Validating these results in autosomal trio data, we observe similar trends between the methods and error patterns, though with an increased flip error rate, a discrepancy that may be biased by genotype error.