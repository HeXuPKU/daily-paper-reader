---
title: Genomic Informational Field Theory (GIFT) to identify genetic associations of a complex trait using a small sample size
title_zh: 基因组信息场理论 (GIFT)：利用小样本量识别复杂性状的遗传关联
authors: "Kyratzi, P., Gadsby, S., Knowles, E., Harris, P., Menzies-Gow, N., Elliott, J., Paldi, A., Wattis, J., Rauch, C."
date: 2026-03-19
pdf: "https://www.biorxiv.org/content/10.1101/2025.08.15.670531v2.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 增强小样本量下GWAS效能的新型数据分析方法
tldr: 针对全基因组关联分析（GWAS）通常需要大规模样本的局限性，本研究提出了一种名为基因组信息场理论（GIFT）的新型数据分析方法。该方法通过重新定义SNP间的相关性，在仅157匹矮马的小样本队列中成功识别了与“肩高”相关的遗传位点，并揭示了其与胰岛素生理及代谢综合征的联系。GIFT不仅提高了小样本研究的统计效能，还能推断基因网络结构，为复杂性状的遗传研究提供了一种高效、低成本的替代方案。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-08-15-670531-v2/fig-001.webp\", \"caption\": \"Table 2: List of significant genes detected by GIFT ordered by p-values. 652\", \"page\": 16, \"index\": 1, \"width\": 996, \"height\": 724}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-08-15-670531-v2/fig-002.webp\", \"caption\": \"Table 3: Centrality measures of central genes of isomorphic networks 658\", \"page\": 17, \"index\": 2, \"width\": 944, \"height\": 340}]"
motivation: 传统的GWAS研究通常需要庞大的样本量才能获得精确的遗传关联推断，这限制了许多小规模队列研究的开展。
method: 引入基因组信息场理论（GIFT），通过重新定义SNP间的相关性来增强小样本数据集的分析效能，并揭示潜在的基因网络结构。
result: 在仅157匹矮马的样本中，GIFT成功识别出与肩高相关的胰岛素生理遗传位点，验证了肩高与马代谢综合征之间的长期假设。
conclusion: GIFT为复杂性状的遗传架构研究提供了一种高分辨率且低成本的工具，使得在有限样本下进行稳健的基因组分析成为可能。
---

## 摘要
全基因组关联研究 (GWAS) 常用于调查复杂性状的遗传基础。然而，为了获得足够的统计效力，它们通常需要大样本量以提供精确的推断。为应对这一挑战，本文引入了 GIFT，这是一种新型数据分析方法，可增强遗传分析的效力，从而在不牺牲精度的前提下使用较小的数据集。在一个包含 157 匹矮马的小型队列中，应用 GIFT 研究了“鬐甲高”这一复杂性状，并将其性能与传统 GWAS 进行了比较。GIFT 成功识别出与胰岛素生理相关的遗传位点，进而验证了一个长期存在的假设，即马科动物的“鬐甲高”与胰岛素生理相关，并可能促进马代谢综合征 (EMS) 的发生。通过重新定义单核苷酸多态性 (SNP) 之间的相关性，GIFT 为连锁不平衡提供了新的见解，并揭示了潜在的基因网络结构。这反过来又使得区分这些网络中的核心基因和外围基因成为可能。通过在不牺牲统计稳健性的情况下减少与大规模基因型-表型映射研究相关的时间和成本，GIFT 扩大了定量遗传学研究的准入门槛，允许小规模研究以更高的分辨率调查复杂性状的遗传架构。

创新与值得关注之处：推断基因型-表型关联通常需要大样本量，这限制了许多遗传学研究。GIFT 作为一种新型数据分析工具，通过在小数据集中实现准确的关联映射克服了这一限制。我们进一步展示了 GIFT 的扩展框架如何推断连锁不平衡和基因网络，从而区分参与复杂性状的核心基因与外围基因。这一进展增强了对生物学架构的理解，并使有限队列中的高分辨率遗传研究成为可能，为传统的大规模方法提供了一种强大且具有成本效益的替代方案。

## Abstract
Genome-wide association studies (GWAS) are commonly used to investigate the genetic basis of complex traits. However, to be adequately powered they typically require large sample sizes to provide precise inferences. To address this challenge, this paper introduces GIFT, a novel data analytic method that enhances the power of genetic analyses, enabling the use of smaller datasets without compromising precision. In a small cohort of 157 ponies, GIFT was applied to examine the complex trait of "height at withers", comparing its performance to traditional GWAS. GIFT enabled the identification genetic loci linked to insulin physiology validating, in turn, a long-standing hypothesis that "height at withers" is associated with insulin physiology in equids, potentially promoting equine metabolic syndrome (EMS). By redefining correlations between single nucleotide polymorphisms (SNPs), GIFT provides new insights into linkage disequilibrium and reveals underlying gene network structures. This, in turn, enables the distinction between core and peripheral genes within these networks. By reducing the time and cost associated with large-scale genotype-phenotype mapping studies without sacrificing statistical robustness, GIFT broadens access to quantitative genetic research, allowing smaller-scale studies to investigate the genetic architecture of complex traits with greater resolution.

NEW & NOTEWORTHYInferring genotype-phenotype associations typically requires large sample sizes, limiting many genetic studies. GIFT, a novel data analytics tool, overcomes this by enabling accurate association mapping in small datasets. We further show how GIFTs extended framework infers linkage disequilibrium and gene networks, distinguishing core from peripheral genes involved in complex traits. This advancement enhances understanding of biological architecture and enables high-resolution genetic research in limited cohorts, offering a powerful, cost-effective alternative to traditional large-scale approaches.