---
title: eRNAformer enables genome-wide de novo mapping of enhancer-derived RNA loci
title_zh: eRNAformer实现增强子衍生RNA位点全基因组从头定位
authors: "Yu, H., Li, W., Liu, Y., Chen, Y., Zhang, X., He, S., Chen, Z., Wang, H., Ni, J., Gao, T., Li, F., Lu, L."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.24.734403v2.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 增强子RNA定位的深度学习方法，为GWAS精细定位提供功能注释
tldr: 增强子来源RNA（eRNA）是全基因转录关键调控因子，但全基因组注释困难。本文提出eRNAformer，整合CNN与Transformer的多模态深度学习框架，利用DNA序列和RNA-seq数据实现从头映射eRNA位点。在ENCODE上验证高灵敏度和特异性，新识别位点富含进化保守变异和复杂疾病遗传风险因子。应用于血液恶性肿瘤鉴定大量eRNA并构建数据库，实验验证FOXO1e在AML中的功能。该工作为eRNA全基因组注释提供强大工具，并为癌症eRNA研究提供宝贵资源。
source: biorxiv
selection_source: fresh_fetch
motivation: eRNA全基因组从头注释仍具挑战，缺乏高灵敏度和特异性的方法。
method: 提出eRNAformer，整合CNN和Transformer捕获双向转录长程特征，基于DNA序列和RNA-seq数据。
result: "在ENCODE上高灵敏度和特异性识别eRNA；在血液癌症中鉴定14,219-56,451个eRNA并构建数据库，实验验证FOXO1e功能。"
conclusion: eRNAformer是全基因组eRNA注释的有效工具，为血癌研究提供资源，并强调eRNA在AML发病中的功能重要性。
---

## 摘要
增强子衍生RNA（eRNAs）是基因转录的关键调控因子，然而其全基因组注释仍具挑战性。本文提出eRNAformer，一种多模态深度学习框架，融合卷积神经网络与Transformer，专门设计用于捕获与双向转录相关的长程遗传特征。该方法利用DNA序列和聚合的传统RNA-seq数据实现eRNA位点的从头定位。在ENCODE数据集上评估时，eRNAformer在区分已知eRNA位点与非eRNA位点方面表现出高灵敏度和特异性。值得注意的是，新鉴定的eRNA位点富含进化保守变异和复杂疾病的遗传风险因子，并显示与癌症治疗的潜在相关性。应用于GEO数据集，eRNAformer在多种血液系统恶性肿瘤中鉴定出14,219至56,451个eRNA位点，有助于构建血癌综合eRNA数据库。我们进一步鉴定并实验验证了FOXO1e，这是一组位于FOXO1上游约120 kb的eRNA簇，FOXO1是一种已知驱动t(8;21)急性髓系白血病（AML）白血病前期程序的癌基因。综上所述，这些发现确立了eRNAformer作为全基因组eRNA注释的强大工具，为血液癌症中的eRNA研究提供了宝贵资源，并强调了eRNA在AML发病机制中的功能性重要性。

## Abstract
Enhancer-derived RNAs (eRNAs) are critical regulators of gene transcription, yet their genome-wide annotation remains challenging. Here, we present eRNAformer, a multi-modal deep learning framework that integrates convolutional neural networks with transformers, specifically designed to capture long-range genetic features associated with bidirectional transcription. This approach enables de novo mapping of eRNA loci using DNA sequence and aggregated conventional RNA-seq data. When evaluated on ENCODE datasets, eRNAformer demonstrated high sensitivity and specificity in discriminating known eRNA loci from non-eRNA loci. Notably, the newly identified eRNA loci were enriched with evolutionarily constrained variants and genetic risk factors for complex diseases, and exhibit potential relevance for cancer therapy. Applied to GEO datasets, eRNAformer identified a range from 14,219 to 56,451 eRNA loci across multiple hematologic malignancies, facilitating the construction of a comprehensive eRNA database for blood cancers. We further identified and experimentally validated FOXO1e, a cluster of eRNAs located approximately 120 kb upstream of FOXO1, a known oncogene that drives t(8;21) acute myeloid leukemia (AML) preleukemic program. Together, these findings establish eRNAformer as a powerful tool for genome-wide eRNA annotation, provide a valuable resource for eRNA studies in hematologic cancers, and underscore the functional importance of eRNAs in AML pathogenesis.