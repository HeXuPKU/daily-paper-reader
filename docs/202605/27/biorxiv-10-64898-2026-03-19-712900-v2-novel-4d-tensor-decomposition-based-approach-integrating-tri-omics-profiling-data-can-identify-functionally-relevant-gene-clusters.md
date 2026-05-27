---
title: Novel 4D tensor decomposition-based approach integrating tri-omics profiling data can identify functionally relevant gene clusters
title_zh: 基于新型四维张量分解整合三组学谱数据的方法可识别功能相关基因簇
authors: "Taguchi, Y.-h., Turki, T."
date: 2026-05-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.19.712900v2.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 整合转录组、翻译组和蛋白质组的功能基因组学方法，与需求9的整合功能基因组与GWAS相关
tldr: 基因表达调控涉及多个层面，但整合转录组、翻译组和蛋白质组三组学数据的无监督框架尚未成熟。本文提出四维张量分解方法，对分支链氨基酸饥饿下的三组学数据进行高阶奇异值分解，成功捕获与核糖体堆积和翻译缓冲相关的成分。筛选出1781个核糖体堆积相关基因和227个翻译缓冲相关基因，富集分析显示它们分别参与翻译、细胞周期等和剪接体、免疫等通路。与MOFA+等方法对比，本方法更有效地提取出生物学可解释的基因簇，证明张量分解在整合多组学数据中的价值。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以无监督地整合转录组、翻译组和蛋白质组三组学数据以揭示功能相关的基因模块。
method: 利用高阶奇异值分解对三组学数据进行四维张量分解，基于奇异值向量选择基因并识别核糖体堆积和翻译缓冲成分。
result: 识别出1781个核糖体堆积相关基因和227个翻译缓冲相关基因，富集于翻译、细胞周期、免疫等通路，且比MOFA+等方法更有效。
conclusion: 四维张量分解能有效整合三组学数据并识别具有生物学功能的基因簇，为多组学分析提供新工具。
---

## 摘要
理解基因表达需要整合多个调控层面，因为转录本丰度不一定对应于翻译活性或蛋白质丰度。核糖体图谱和蛋白质组学有助于区分翻译增强与核糖体堆积或翻译缓冲，但目前尚无无监督整合转录组、翻译组和蛋白质组谱的实际标准框架。在此，我们提出一种基于四维张量分解的无监督特征提取方法用于三组学整合。我们将高阶奇异值分解应用于支链氨基酸饥饿条件下测量的转录组、Ribo-seq和蛋白质组谱。得到的奇异值向量捕捉了三个组学层之间的关系，包括一个与核糖体堆积一致的成分（其中转录组和翻译组信号增强而蛋白质组信号减弱），以及另一个与翻译缓冲一致的成分（尽管转录组和翻译组发生变化，但蛋白质组变异受到抑制）。基因选择识别出1,781个与核糖体堆积相关的基因和227个与翻译缓冲相关的基因。富集分析将前者关联到翻译、翻译后蛋白质修饰、RNA聚合酶II转录、细胞周期调控、内质网蛋白质加工、泛素介导的蛋白水解和应激相关通路，将后者关联到核糖体、翻译延伸和终止、剪接体、免疫和应激相关通路以及核糖体病变相关疾病。鲁棒性分析表明，结果不受重复蛋白质组复制或缺失值处理的显著影响。与MOFA+和mixOmics的比较表明，我们的方法更有效地提取了可解释为核糖体堆积和翻译缓冲的成分。这些结果证明，基于张量分解的无监督特征提取对于从三组学数据中识别功能相关基因簇是有用的。

## Abstract
Understanding gene expression requires integrating multiple regulatory layers, because transcript abundance does not necessarily correspond to translational activity or protein abundance. Ribosome profiling and proteomics help distinguish increased translation from ribosome stacking or translational buffering, but no de facto standard framework exists for unsupervised integration of transcriptome, translatome, and proteome profiles. Here, we propose a four-dimensional tensor decomposition-based unsupervised feature extraction approach for tri-omics integration. We applied higher-order singular value decomposition to transcriptome, Ribo-seq, and proteome profiles measured under branched-chain amino acid starvation. The resulting singular value vectors captured relationships among the three omics layers, including a component consistent with ribosome stacking, where transcriptome and translatome signals increased while proteome signals decreased, and another consistent with translational buffering, where proteome variation was suppressed despite transcriptome and translatome changes. Gene selection identified 1,781 genes associated with ribosome stacking and 227 genes associated with translational buffering. Enrichment analyses linked the former to translation, post-translational protein modification, RNA polymerase II transcription, cell cycle regulation, endoplasmic reticulum protein processing, ubiquitin-mediated proteolysis, and stress-related pathways, and the latter to ribosome, translation elongation and termination, spliceosome, immune- and stress-related pathways, and ribosomopathy-associated diseases. Robustness analyses indicated that the results were not substantially affected by the duplicated proteome replicate or missing-value handling. Comparison with MOFA+ and mixOmics suggested that our approach more effectively extracted components interpretable as ribosome stacking and translational buffering. These results demonstrate that tensor decomposition-based unsupervised feature extraction is useful for identifying functionally relevant gene clusters from tri-omics data.