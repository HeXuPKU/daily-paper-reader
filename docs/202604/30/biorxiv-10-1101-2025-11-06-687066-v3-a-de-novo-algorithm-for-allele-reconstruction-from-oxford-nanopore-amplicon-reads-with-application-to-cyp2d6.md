---
title: "A De Novo Algorithm for Allele Reconstruction from Oxford Nanopore Amplicon Reads, with Application to CYP2D6"
title_zh: 一种用于 Oxford Nanopore 扩增子读取序列等位基因重建的从头算法及其在 CYP2D6 中的应用
authors: "Brown, S. D., Dreolini, L., Minor, A., Mozel, M., Wong, N., Mar, S., Lieu, A., Khan, M., Carlson, A., Hrynchak, M., Holt, R. A., Missirlis, P. I."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.06.687066v3.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 用于药物基因组学（CYP2D6）长读长等位基因重建的算法
tldr: 针对牛津纳米孔（ONT）长读长测序在基因分型中的挑战，本研究提出了一种通用的从头（de novo）等位基因重建算法。该方法采用“序列优先”策略，无需预设目标基因即可从扩增子读段中高精度重建等位基因序列，并能有效识别复杂基因（如CYP2D6）的二倍体型、拷贝数变异及新变异，为床旁基因组学提供了强有力的分析工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的长读长测序分析通常需要针对特定基因进行定制，难以直接且准确地从高错误率的读段中识别复杂的等位基因和结构变异。
method: 提出一种“序列优先”的通用算法，通过对扩增子读段进行无偏见的从头重建生成高置信度等位基因序列，再将其与参考基因组比对以推断二倍体型。
result: 在CYP2D6基因的多个数据集上验证了准确性，成功识别了20个样本的二倍体型和拷贝数变异，并展示了在HLA等其他基因组区域的适用性。
conclusion: 该算法不依赖于特定基因或等位基因数量，能够高效、准确地处理复杂基因组区域的测序数据，具有广泛的临床应用潜力。
---

## 摘要
Oxford Nanopore Technologies 测序平台为床旁基因组学提供了一条路径，其产生的长读段可以完全覆盖目标基因，从而检测该基因包含的任何已知或新变异。然而，分析这些长读段以识别可操作的基因型仍然具有挑战性，且通常需要根据目标基因进行定制。在本文中，我们描述了一种通用算法，用于准确重建源自基因组扩增子长读段的等位基因序列。我们的方法并非直接从这些长读段中调用变异，而是采用“序列优先”的方法，对底层扩增子序列进行无偏重建，以生成高置信度的重建等位基因序列。这一过程无需用户输入预期的目标基因，从而允许重建任何来源的扩增子。随后，将这些高置信度的重建等位基因序列与基因的基因组参考序列进行比较，以推断样本中存在的特定双倍型（diplotype）。该方法对存在的基因和等位基因数量不敏感，并且可以轻松检测到新变异。我们使用 CYP2D6 的三个独立数据集演示了我们的方法，CYP2D6 是一个多样且复杂的基因，拥有超过 175 个具有临床意义且影响药物剂量的已知等位基因。我们展示了该方法如何从 20 个 Coriell 样本中准确恢复经过验证的 CYP2D6 双倍型，这些样本使用不同的引物组、在不同的 Oxford Nanopore Technologies 流式细胞术版本上以及以不同的深度进行测序。这包括从每个等位基因的相对丰度中推断拷贝数变异的发生，这是将功能效应归因于双倍型的关键因素。此外，我们还证明了该方法在包括 HLA 在内的其他基因组区域的实用性。

## Abstract
The Oxford Nanopore Technologies sequencing platform offers a path towards bedside genomics, producing long reads that can completely cover a gene of interest, and thus detect any known or novel variant the gene contains. However, the analysis of these long reads to identify actionable genotypes remains challenging and typically requires customization depending on the target gene. Here, we describe a generic algorithm to accurately reconstruct allele sequences derived from long-reads of genomic-amplicon origin. Rather than calling variants directly from these long-reads, our method takes a "sequence-first" approach, performing an unbiased reconstruction of the underlying amplicon sequences to generate high-confidence reconstructed allele sequences. This is done without user input of the expected target gene, allowing for any source amplicon to be reconstructed. These high-confidence reconstructed allele sequences are then compared to the genomic reference sequence of the gene to infer the specific diplotype present in the sample. This approach is agnostic towards the number of genes and alleles present and readily detects novel variants. We demonstrate our approach using three independent data sets for CYP2D6, a diverse and complex gene with over 175 known alleles of clinical significance affecting drug dosing. We show how our approach can accurately recover validated CYP2D6 diplotypes from 20 Coriell samples sequenced using different primer sets, on different Oxford Nanopore Technologies flow cell versions, and to different depths. This includes inferring occurrences of copy number variation from relative abundances of each allele, a critical factor for ascribing functional effects to a diplotype. Further, we demonstrate our approachs utility for other genomic regions, including HLA.