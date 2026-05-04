---
title: Controlling for DNA dosage with Whole Genome Sequencing improves ATAC-seq peak calling
title_zh: 利用全基因组测序控制 DNA 剂量可改进 ATAC-seq 峰值检测
authors: "Vroland, C., Salma, M., Zhigulev, A., Sahlen, P., Soler, E., Brehelin, L., Lecellier, C.-H."
date: 2026-04-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.23.720296v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 将全基因组测序与ATAC-seq整合以改进调控元件的峰值调用
tldr: ATAC-seq 峰值调用常受拷贝数变异和 DNA 复制时间导致的剂量偏差影响。本研究提出在 MACS 流程中整合全基因组测序（WGS）数据作为对照，类似于 ChIP-seq 的 input 控制。该方法显著提升了峰值检测的准确性，增加了峰的数量与宽度，并增强了其与基因表达及疾病相关变异的关联，且低深度 WGS 即可实现优化。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的 ATAC-seq 分析忽略了 DNA 拷贝数和复制时间带来的局部剂量偏差，限制了顺式作用元件识别的准确性。
method: 借鉴 ChIP-seq 的 input 对照思路，将 WGS 数据整合进 MACS 流程以校正局部 DNA 剂量效应。
result: 实验证明该方法增加了峰的数量和宽度，改善了其在 TSS 附近的分布，并显著提高了与基因表达水平的相关性。
conclusion: 整合 WGS 数据是提升 ATAC-seq 峰值调用准确性的低成本且高效的方案，对其他基于 DNA 测序的技术也具有重要借鉴意义。
---

## 摘要
转座酶嗜性染色质测序分析（ATAC-seq）是一种可扩展且灵敏的染色质可及性分析方法，能够鉴定在不同细胞背景下控制基因表达的顺式作用元件（CREs）。尽管 ATAC-seq 已常规应用于大体（bulk）和单细胞样本，但我们发现其峰值检测（peak calling）过程受到 DNA 剂量局部偏差的影响，这些偏差不仅源于拷贝数变异（CNVs），还源于 DNA 复制时序（RT）。这些偏差会扭曲 read 覆盖度并损害峰值检测的准确性。作为 FANTOM 联盟阐明基因组调控工作的一部分，我们建议通过整合全基因组测序（WGS）数据来增强 MACS 流水线，以解释局部 DNA 剂量效应，这类似于 ChIP-seq 分析中 input 对照的使用。通过整合 WGS 数据，我们证明了 ATAC 峰的数量和宽度均有所增加，且与转录起始位点（TSSs）的距离更近。经 WGS 控制的 ATAC 峰表现出经典的 CRE 表观遗传标记，并富集了与性状和疾病相关的遗传变异。此外，与未经 WGS 控制检测到的峰相比，经 WGS 控制的峰数量与基因表达水平的相关性更强。总之，这些结果表明，整合 WGS 作为对照可显著提高 ATAC-seq 峰值检测的准确性。关键的是，我们证明即使是低深度的 WGS 数据也足以提高峰值检测性能，使该方法既具有成本效益，又易于在常规分析中采用。为了确保可访问性和可重复性，我们将该方法实现为一个开源的 Nextflow 流水线。通过挑战基因组可见性均匀的假设，我们的方法对其他基于 DNA 测序的技术也具有广泛的意义。

## Abstract
The Assay for Transposase-Accessible Chromatin using sequencing (ATAC-seq) is a scalable and sensitive method for profiling chromatin accessibility, enabling the identification of cis-regulatory elements (CREs) that govern gene expression in diverse cellular contexts. Although ATAC-seq is routinely applied to both bulk and single-cell samples, we reveal that its peak calling process is compromised by local biases in DNA dosage, arising not only from copy number variations (CNVs) but also from DNA replication timing (RT). These biases can distort read coverage and compromise peak detection accuracy. As part of the FANTOM consortiums efforts to elucidate genomic regulation, we propose enhancing the MACS pipeline by integrating whole-genome sequencing (WGS) data to account for local DNA dosage effects, analogous to the use of input controls in ChIP-seq analyses. By incorporating WGS data, we demonstrate an increase in both the number and width of ATAC peaks, with improved proximity to transcription start sites (TSSs). WGS-controlled ATAC peaks exhibit canonical CRE epigenetic marks and are enriched for trait- and disease-associated genetic variants. Furthermore, the number of WGS-controlled peaks correlates more strongly with gene expression levels compared to peaks called without WGS control. Collectively, these results demonstrate that integrating WGS as a control significantly enhances the accuracy of ATAC-seq peak calling. Critically, we show that even low-depth WGS data is sufficient to improve peak calling performance, making this approach both cost-effective and readily adoptable for routine analyses. To ensure accessibility and reproducibility, we implemented this method as an open-source Nextflow pipeline. By challenging the assumption of uniform genomic visibility, our approach also holds broad implications for other DNA sequencing-based technologies.