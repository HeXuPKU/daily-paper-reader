---
title: Saturation-seq integrates single-cell saturation genome editing and RNA-seq to quantify NFE2L2 (NRF2) variant effects
title_zh: Saturation-seq整合单细胞饱和基因组编辑与RNA-seq以量化NFE2L2（NRF2）变异效应
authors: "Strauss, M. E., Waters, A. J., Roberston, H., Brendler-Spaeth, T., Gontarczyk, A., Gupta, P., Kataria, S., Gitterman, D., Ntereke, T., Wells, L., Billington, J., Bassett, A., Cooper, S., Adams, D. J."
date: 2026-07-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.30.735631v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 通过饱和基因组编辑整合功能基因组学与GWAS的方法框架
tldr: "解读变异功能是基因组学难题，现有方法多依赖细胞生长等一维代理。Saturation-seq结合饱和基因组编辑与单细胞DNA/RNA测序，在条形码单倍体细胞中安装数百个变异，直接测量其转录影响。对NRF2 230个变异进行表征，基于靶基因失调的破坏分数以>90%准确率区分致病/良性变异，并成功解释患者肿瘤和发育综合征数据。该平台提供多维表型的高通量变异解读，具有广泛应用前景。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有变异功能解读方法依赖一维代理（如细胞生长），无法充分捕捉变异的多维表型影响，尤其对于功能获得/新形态变异。
method: 利用CRISPR在条形码单倍体细胞系中同时安装数百个变异，结合单细胞扩增子和转录组测序直接关联编辑与转录变化。
result: "对NRF2 230个变异分析，基于靶标失调的破坏分数以>90%准确率区分致病/良性变异，并揭示了TCGA/TRACERx肿瘤数据和发育综合征种系变异。"
conclusion: Saturation-seq建立了可广泛应用的、高分辨率单细胞变异-功能平台，提供丰富的转录表型读出来量化变异效应。
---

## 摘要
解读变异的功能后果仍然是基因组学和临床遗传学中未解决的核心问题之一。更为复杂的是，现有的大多数方法依赖于简化的、一维的替代指标（如细胞生长）来评估变异效应，而这对理解变异如何改变生物学所需的多维表型来说，是一个糟糕的替代。对于已知通过功能获得/新形态机制起作用的变异尤其如此。我们开发了Saturation-seq，这是一个高通量平台，结合了饱和基因组编辑与单细胞DNA和RNA分析，以系统性地绘制变异效应。利用基于CRISPR的编辑，我们在条码化的单倍体细胞系中将数百个变异直接引入内源基因组位点，进行多重测试并保留天然编码和调控环境。单细胞扩增子和转录组测序能够将每个基因组编辑直接与其转录影响联系起来。我们应用Saturation-seq全面表征了NFE2L2（NRF2）频繁突变的N端区域的230个变异，NRF2是氧化应激的主要调节因子，也是肺癌中突变的癌基因。我们通过单细胞转录组中已知NRF2靶标的失调计算得到的破坏分数来定义变异功能；这些分数以超过90%的准确度区分致病/良性真集变异，并能够解读TCGA和TRACERx患者肿瘤数据，以及与发育综合征相关的罕见NFE2L2种系变异。因此，我们建立了一个广泛适用的高分辨率单细胞变异到功能平台，具有丰富的表型读数。

## Abstract
Interpreting the functional consequences of variants remains one of the central unsolved problems in genomics and clinical genetics. Compounding this, most existing approaches rely on reductive, one-dimensional proxies such as cell growth to score variant effects, which can be a poor substitute for the rich, multidimensional phenotyping that is ultimately needed to understand how variants alter biology. This is especially true for variants known to act through gain-of-function/neomorphic mechanisms. We developed Saturation-seq, a high-throughput platform that combines saturation genome editing with single-cell DNA and RNA profiling to systematically map variant effects. Using CRISPR-based editing in a barcoded haploid cell line, we install hundreds of variants directly into endogenous genomic loci, testing them in multiplex and preserving the native coding and regulatory context. Single-cell amplicon and transcriptome sequencing enables direct linkage of each genomic edit to its transcriptional impact. We apply Saturation-seq to comprehensively characterize 230 variants in the recurrently mutated N-terminal region of NFE2L2 (NRF2), a master regulator of oxidative stress and an oncogene mutated in lung cancer. We define variant function with disruption scores computed from misregulation of known NRF2 targets in single-cell transcriptomes; scores separate pathogenic/benign truthset variants with >90% accuracy and enabled interpretation of TCGA and TRACERx patient tumor data, as well as a rare NFE2L2 germline variant linked to a developmental syndrome. Thus, we establish a broadly applicable high-resolution single-cell variant-to-function platform with a rich phenotypic readout.