---
title: "scDeepVariant: A population-informed deep learning framework for germline variant calling in scRNA-seq"
title_zh: scDeepVariant：一种用于scRNA-seq胚系变异识别的群体信息深度学习框架
authors: "Buralkin, I., Chen, H., Park, J., Liu, Z."
date: 2026-05-21
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.31.696877v2.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 基于深度学习的scRNA-seq变异调用框架，可应用于GWAS分析
tldr: 单细胞RNA测序可揭示种系遗传变异，但面临稀疏覆盖和等位基因不平衡挑战。现有方法灵敏度低或依赖连锁不平衡先验，难以检测稀有变异。本文提出scDeepVariant，将DeepVariant适配于单细胞数据，并创新性地融入群体等位频率信息，显著提升变异检出性能。在基准测试中，scDV在10倍覆盖以上优于Monopogen，尤其在稀有变异检测中表现突出，为单细胞转录组变异发现提供了鲁棒方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有单细胞变异检测方法在灵敏度和稀有变异检测上存在局限，亟需不依赖LD先验的深度学习框架。
method: 基于DeepVariant，在配对WGS和snRNA-seq数据上训练，并嵌入gnomAD等群体等位基因频率通道。
result: 融入等位基因频率的scDV在精度和召回率上超越标准配置，高覆盖时胜过Monopogen，稀有变异检测优势显著。
conclusion: scDV为单细胞RNA-seq种系变异调用提供了鲁棒替代方案，证明了整合群体信息对深度学习框架的价值。
---

## 摘要
单细胞RNA测序（scRNA-seq）在捕捉细胞异质性的同时，也能提供胚系遗传变异的信息，但准确的变异识别仍然受到稀疏覆盖、等位基因失衡和RNA特异性伪影的限制。现有的单细胞方法，包括cellSNP、scAllele和Monopogen，解决了部分挑战，但要么灵敏度与精度较低，要么依赖于限制罕见变异性能的连锁不平衡（LD）先验。在此，我们提出scDeepVariant（scDV），这是一个基于深度学习的框架，改编自DeepVariant，并在配对的全基因组测序（WGS）和单核RNA测序（snRNA-seq）数据上进行了训练。我们表明，scDV可以在稀疏的单细胞数据上有效训练，并且利用gnomAD或1000 Genomes Project的等位基因频率信息增强模型可以持续提升性能。在基准测试中，带有等位基因频率通道的scDV比标准的六通道配置实现了更高的精度和召回率，在覆盖深度超过10x时优于Monopogen，并在LD优化最受限的罕见变异检测中展现出显著优势。这些结果确立了scDV作为从scRNA-seq中发现胚系变异的稳健替代方案，并突显了将群体规模信息整合到用于转录组变异识别的深度学习框架中的更广泛价值。

## Abstract
Single-cell RNA sequencing (scRNA-seq) provides unprecedented resolution of cellular heterogeneity while also capturing information on germline genetic variation, but accurate variant calling remains limited by sparse coverage, allelic imbalance, and RNA-specific artifacts. Existing single-cell methods, including cellSNP, scAllele, and Monopogen, address some of these challenges, yet either suffer from low sensitivity and precision or rely on linkage disequilibrium (LD) priors that restrict performance on rare variants. Here, we introduce scDeepVariant (scDV), a deep learning-based framework adapted from DeepVariant and trained on paired whole-genome sequencing (WGS) and single-nucleus RNA sequencing (snRNA-seq) data. We show that scDV can be effectively trained on sparse single-cell data and that augmenting models with allele frequency information from gnomAD or the 1000 Genomes Project consistently improves performance. Across benchmarks, scDV with allele frequency channels achieved higher precision and recall than standard six-channel configurations, surpassing Monopogen at coverage depths above 10x and demonstrating a pronounced advantage in rare variant detection, where LD-based refinement is most limited. These results establish scDV as a robust alternative for germline variant discovery from scRNA-seq and highlight the broader value of integrating population-scale information into deep learning frameworks for transcriptomic variant calling.