---
title: Novel 4D tensor decomposition-based approach integrating tri-omics profiling data can identify functionally relevant gene clusters
title_zh: 基于新颖四维张量分解的三组学数据整合方法可识别功能相关基因簇
authors: "Turki, T., Taguchi, Y.-h."
date: 2026-07-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.19.712900v3.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 张量分解整合三组学数据，支持功能基因组学与GWAS整合
tldr: 整合转录组、翻译组和蛋白质组对于解析基因表达调控机制至关重要，但目前缺乏无监督整合三组学的标准框架。本文提出基于四维张量分解（高阶SVD）的无监督特征提取方法，应用于支链氨基酸饥饿数据，识别出1781个核糖体堆积基因和227个翻译缓冲基因，富集分析显示这些基因涉及翻译、蛋白质修饰、细胞周期及应激相关通路。与MOFA+和mixOmics相比，该方法能直接提取生物学可解释的成分，为三组学数据整合提供了有效途径。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法缺乏无监督整合转录组、翻译组和蛋白质组的标准框架，难以全面揭示基因表达调控机制。
method: 采用四维张量分解（高阶SVD）对三组学数据进行无监督特征提取，分解出代表核糖体堆积和翻译缓冲的成分。
result: 识别出1781个核糖体堆积基因和227个翻译缓冲基因，富集于翻译、修饰、细胞周期等通路，且结果稳健。
conclusion: 张量分解方法能直接提取生物学可解释的成分，为三组学数据整合及功能基因簇识别提供了有效工具。
---

## 摘要
理解基因表达需要整合多个调控层面，因为转录本丰度不一定对应于翻译活性或蛋白质丰度。核糖体图谱和蛋白质组学有助于区分翻译增加与核糖体堆积或翻译缓冲，但尚无事实上的标准框架用于无监督整合转录组、翻译组和蛋白质组谱。本文提出一种基于四维张量分解的无监督特征提取方法用于三组学整合。我们对支链氨基酸饥饿条件下测量的转录组、Ribo-seq和蛋白质组谱应用高阶奇异值分解。得到的奇异值向量捕获了三个组学层之间的关系，包括一个与核糖体堆积一致的成分（转录组和翻译组信号增加而蛋白质组信号减少），以及另一个与翻译缓冲一致的成分（尽管转录组和翻译组发生变化，蛋白质组变异被抑制）。基因选择识别出1,781个与核糖体堆积相关的基因和227个与翻译缓冲相关的基因。富集分析将前者与翻译、翻译后蛋白质修饰、RNA聚合酶II转录、细胞周期调控、内质网蛋白质加工、泛素介导的蛋白水解及应激相关通路联系起来，后者与核糖体、翻译延伸和终止、剪接体、免疫和应激相关通路以及核糖体病相关疾病相关。稳健性分析表明，结果未受重复蛋白质组样本或缺失值处理的显著影响。在测试条件下，与MOFA+和mixOmics的比较表明，我们的方法更直接地提取了可解释为核糖体堆积和翻译缓冲的成分。这些结果表明，基于张量分解的无监督特征提取对于从三组学数据中识别功能相关基因簇是有用的。

## Abstract
Understanding gene expression requires integrating multiple regulatory layers, because transcript abundance does not necessarily correspond to translational activity or protein abundance. Ribosome profiling and proteomics help distinguish increased translation from ribosome stacking or translational buffering, but no de facto standard framework exists for unsupervised integration of transcriptome, translatome, and proteome profiles. Here, we propose a four-dimensional tensor decomposition-based unsupervised feature extraction approach for tri-omics integration. We applied higher-order singular value decomposition to transcriptome, Ribo-seq, and proteome profiles measured under branched-chain amino acid starvation. The resulting singular value vectors captured relationships among the three omics layers, including a component consistent with ribosome stacking, where transcriptome and translatome signals increased while proteome signals decreased, and another consistent with translational buffering, where proteome variation was suppressed despite transcriptome and translatome changes. Gene selection identified 1,781 genes associated with ribosome stacking and 227 genes associated with translational buffering. Enrichment analyses linked the former to translation, post-translational protein modification, RNA polymerase II transcription, cell cycle regulation, endoplasmic reticulum protein processing, ubiquitin-mediated proteolysis, and stress-related pathways, and the latter to ribosome, translation elongation and termination, spliceosome, immune- and stress-related pathways, and ribosomopathy-associated diseases. Robustness analyses indicated that the results were not substantially affected by the duplicated proteome replicate or missing-value handling. Under the tested settings, comparison with MOFA+ and mixOmics suggested that our approach more directly extracted components interpretable as ribosome stacking and translational buffering. These results demonstrate that tensor decomposition-based unsupervised feature extraction is useful for identifying functionally relevant gene clusters from tri-omics data.