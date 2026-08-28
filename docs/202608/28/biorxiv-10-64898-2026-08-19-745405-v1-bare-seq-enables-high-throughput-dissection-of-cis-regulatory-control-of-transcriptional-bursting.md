---
title: BARe-seq enables high-throughput dissection of cis-regulatory control of transcriptional bursting
title_zh: BARe-seq 实现对转录爆发顺式调控的高通量解析
authors: "Lorbeer, F. K., Rosales Alvarez, R. E., Bergauer, K., Grün, D., Stark, A."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.19.745405v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 用于顺式调控元件的高通量功能基因组学方法，支持GWAS变异优先级排序
tldr: 转录爆发参数如何由顺式调控元件编码尚不清楚。BARe-seq将等位基因分辨与批量报告基因分析结合，可在混合文库中推断爆发大小和频率。对启动子和增强子文库的分析显示，启动子效应由爆发大小和频率共同驱动，而增强子主要调节爆发频率。该方法实现了顺式调控编码爆发动力学的规模化解析。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法无法在可扩展序列扰动下推断等位基因分辨的转录爆发参数。
method: 开发BARe-seq，结合等位基因分辨与批量报告基因测序，从混合文库推断爆发参数。
result: 启动子通过爆发大小和频率调控表达，TATA和DPE分别偏向大小和频率；增强子主要影响频率。
conclusion: BARe-seq实现了顺式调控元件对转录爆发控制的规模化解析，拓展了等位基因分辨测量。
---

## 摘要
转录爆发通过两个动力学参数决定 RNA 输出：爆发大小和爆发频率。顺式调控 DNA 如何编码这些动力学参数仍不清楚，部分原因在于现有方法无法将可扩展的序列扰动与等位基因分辨的爆发推断相结合。在此，我们开发了 Bulk 等位基因分辨测序（BARe-seq），一种等位基因分辨的大规模平行报告基因分析，能够从批量测序中推断转录爆发参数。将 BARe-seq 应用于果蝇 S2 细胞中 1000 个启动子和 1000 个增强子的文库，揭示了启动子和增强子不同的动力学特性。启动子依赖的平均表达由爆发大小和爆发频率共同驱动：TATA-box 启动子表现出更大的爆发，而 DPE 启动子表现出更高的爆发频率。相比之下，增强子强度主要由爆发频率驱动，尽管特定转录因子基序也与爆发大小相关。因此，BARe-seq 解析了转录爆发的顺式调控控制，并将等位基因分辨的测量扩展到批量测序实验中的混合报告基因分析。

## Abstract
Transcriptional bursts determine RNA output through two kinetic parameters: burst size and burst frequency. How cis-regulatory DNA encodes these kinetic parameters remains unclear, in part because existing approaches do not combine scalable sequence perturbation with allele-resolved burst inference. Here, we developed Bulk Allele Resolution Sequencing (BARe-seq), an allele-resolved massively parallel reporter assay that enables inference of transcriptional burst parameters from bulk sequencing. Applying BARe-seq to libraries of 1000 promoters and 1000 enhancers in Drosophila S2 cells revealed distinct kinetic properties of promoters and enhancers. Promoter-dependent mean expression was driven by both burst size and burst frequency: TATA-box promoters showed larger bursts, whereas DPE promoters showed higher burst frequency. In contrast, enhancer strength was primarily driven by burst frequency, although specific transcription factor motifs were also associated with burst size. Thus, BARe-seq dissects cis-regulatory control of transcriptional bursting and extends allele-resolved measurements to pooled reporter assays in bulk sequencing experiments.