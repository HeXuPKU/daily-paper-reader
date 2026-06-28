---
title: eRNAformer enables genome-wide de novo mapping of enhancer-derived RNA loci
title_zh: eRNAformer实现全基因组从头映射增强子衍生RNA位点
authors: "Yu, H., Li, W., Liu, Y., Chen, Y., Zhang, X., He, S., Chen, Z., Wang, H., Ni, J., Gao, T., Li, F., Lu, L."
date: 2026-06-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.24.734403v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 深度学习定位增强子RNA位点并富集遗传风险因子
tldr: 增强子RNA(eRNA)是基因转录的关键调控因子，但其全基因组注释仍具挑战。eRNAformer多模态深度学习框架结合CNN和Transformer，从DNA序列和RNA-seq数据中从头映射eRNA位点，在ENCODE数据上表现出高灵敏度和特异性。新发现的eRNA位点富集进化保守变异和疾病风险因子，尤其在血液恶性肿瘤中鉴定出14219至56451个eRNA位点。实验验证了位于FOXO1上游约120kb的FOXO1e eRNA簇在t(8;21) AML前白血病程序中的驱动作用，为eRNA功能研究提供了重要工具和资源。
source: biorxiv
selection_source: fresh_fetch
motivation: 增强子RNA(eRNA)对基因调控至关重要，但现有方法难以实现全基因组从头注释。
method: 提出eRNAformer多模态深度学习框架，集成CNN和Transformer，利用DNA序列和常规RNA-seq数据从头检测eRNA位点。
result: ENCODE测试中高灵敏度和特异性；新发现位点富集进化保守变异与疾病风险因子；在多种血液恶性肿瘤中鉴定数万个eRNA位点，并验证FOXO1e eRNA簇在AML中的功能。
conclusion: eRNAformer是一种有效的全基因组eRNA注释工具，为血液癌症eRNA研究提供资源，并揭示eRNA在AML发病机制中的重要性。
---

## 摘要
增强子衍生RNA（eRNAs）是基因转录的关键调控因子，但其全基因组注释仍具挑战性。本文提出eRNAformer，一种多模态深度学习框架，它结合了卷积神经网络与Transformer，专门设计用于捕获与双向转录相关的长程遗传特征。该方法利用DNA序列和聚合的常规RNA-seq数据实现eRNA位点的从头映射。在ENCODE数据集上的评估显示，eRNAformer在区分已知eRNA位点与非eRNA位点时表现出高灵敏度和特异性。值得注意的是，新发现的eRNA位点富集了进化保守的变异和复杂疾病的遗传风险因素，并显示出与癌症治疗的潜在相关性。应用于GEO数据集时，eRNAformer在多种血液恶性肿瘤中识别出14,219至56,451个eRNA位点，促进了血癌综合eRNA数据库的构建。我们进一步鉴定并实验验证了FOXO1e，一个位于已知致癌基因FOXO1上游约120 kb处的eRNA簇，该基因驱动t(8;21)急性髓系白血病（AML）的白血病前期程序。综上，这些发现将eRNAformer确立为全基因组eRNA注释的强大工具，为血液系统癌症中的eRNA研究提供了宝贵资源，并强调了eRNA在AML发病机制中的功能重要性。

## Abstract
Enhancer-derived RNAs (eRNAs) are critical regulators of gene transcription, yet their genome-wide annotation remains challenging. Here, we present eRNAformer, a multi-modal deep learning framework that integrates convolutional neural networks with transformers, specifically designed to capture long-range genetic features associated with bidirectional transcription. This approach enables de novo mapping of eRNA loci using DNA sequence and aggregated conventional RNA-seq data. When evaluated on ENCODE datasets, eRNAformer demonstrated high sensitivity and specificity in discriminating known eRNA loci from non-eRNA loci. Notably, the newly identified eRNA loci were enriched with evolutionarily constrained variants and genetic risk factors for complex diseases, and exhibit potential relevance for cancer therapy. Applied to GEO datasets, eRNAformer identified a range from 14,219 to 56,451 eRNA loci across multiple hematologic malignancies, facilitating the construction of a comprehensive eRNA database for blood cancers. We further identified and experimentally validated FOXO1e, a cluster of eRNAs located approximately 120 kb upstream of FOXO1, a known oncogene that drives t(8;21) acute myeloid leukemia (AML) preleukemic program. Together, these findings establish eRNAformer as a powerful tool for genome-wide eRNA annotation, provide a valuable resource for eRNA studies in hematologic cancers, and underscore the functional importance of eRNAs in AML pathogenesis.