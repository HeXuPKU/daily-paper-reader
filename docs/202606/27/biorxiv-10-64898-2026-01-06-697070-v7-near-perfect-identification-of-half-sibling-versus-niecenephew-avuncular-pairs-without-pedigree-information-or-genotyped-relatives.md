---
title: Near perfect identification of half sibling versus niece/nephew avuncular pairs without pedigree information or genotyped relatives
title_zh: 无需谱系信息或基因分型亲属的近完美识别半同胞与侄/甥-叔舅对
authors: "Sapin, E., Kelly, K., Keller, M. C."
date: 2026-06-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.06.697070v7.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 基于SNP的IBD方法区分亲缘关系，对GWAS群体结构控制重要
tldr: "大型基因生物库中半同胞与侄/甥-姑叔关系难以区分，现有方法误分类率高。本文提出仅用基因型数据的计算框架，通过跨染色体定相提取单倍型共享特征，并用高斯混合模型分类，实现>98%准确率。该方法无需谱系年龄信息，且可改进跨染色体同源体分配，为谱系重建和隐秘亲缘关系控制提供可扩展方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以准确区分半同胞和侄/甥-姑叔，因两者共享基因组比例相同且IBD分布重叠严重，亟需仅依赖基因型数据的可扩展方法。
method: 利用跨染色体定相获得单倍型共享特征，并用高斯混合模型对特征建模以分类半同胞和侄/甥-姑叔对。
result: "在生物库规模数据上实现>98%的分类准确率，接近完全分离两类关系。"
conclusion: 该方法为谱系重建和隐秘亲缘关系控制提供稳健可扩展方案，并可作为定相锚点提升同源体分配准确性。
---

## 摘要
动机：大规模基因组生物样本库包含数千个缺乏谱系元数据的二级亲属。准确区分半同胞（HS）与侄/甥-叔舅（N/A）对——两者共享约25%的基因组——仍然是一个重大挑战。当前基于SNP的方法依赖同源相同（IBD）片段计数和年龄差异，但显著分布重叠导致高错误分类率。亟需一种可扩展的、仅基于基因型的方法，无需观察到的谱系或大量亲属信息即可解决这些“半度”歧义。结果：我们提出了一种新颖的计算框架，仅使用基因型数据即可实现HS与N/A对的近乎完全分离。我们的方法利用跨染色体定相来推导单倍型水平的共享特征，总结IBD如何在亲本同源染色体上分布。通过使用高斯混合模型（GMM）对这些特征进行建模，我们在生物样本库规模的数据中展示了近乎完美的分类准确性（>98%）。此外，我们证明这些高置信度的关系标签可以作为长程定相锚点，提供结构约束，从而提高跨染色体同源染色体分配的准确性。该方法为大规模基因组研究中的谱系重建和隐蔽亲缘关系控制提供了稳健且可扩展的解决方案。

## Abstract
Motivation: Large-scale genomic biobanks contain thousands of second-degree relatives with missing pedigree metadata. Accurately distinguishing half-sibling (HS) from niece/nephew-avuncular (N/A) pairs--both sharing approximately 25% of the genome--remains a significant challenge. Current SNP-based methods rely on Identical-By-Descent (IBD) segment counts and age differences, but substantial distributional overlap leads to high misclassification rates. There is a critical need for a scalable, genotype-only method that can resolve these "half-degree" ambiguities without requiring observed pedigrees or extensive relative information. Results: We present a novel computational framework that achieves near-complete separation of HS and N/A pairs using only genotype data. Our approach utilizes across-chromosome phasing to derive haplotype-level sharing features that summarize how IBD is distributed across parental homologues. By modeling these features with a Gaussian mixture model (GMM), we demonstrate near-perfect classification accuracy (> 98%) in biobank-scale data. Furthermore, we show that these high-confidence relationship labels can serve as long-range phasing anchors, providing structural constraints that improve the accuracy of across-chromosome homologue assignment. This method provides a robust, scalable solution for pedigree reconstruction and the control of cryptic relatedness in large-scale genomic studies.