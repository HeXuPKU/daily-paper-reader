---
title: "cuBayes: GPU accelerated FreeBayes that achieves 1-minute whole-genome SNV calling while maintaining algorithmic semantics"
title_zh: "cuBayes: GPU加速的FreeBayes，实现一分钟全基因组SNV检测并保持算法语义"
authors: "Pitman, A., Yang, C., Qiao, Y."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.731910v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: GPU加速的变异检测器实现快速全基因组SNV检测，是GWAS计算算法关键
tldr: "下一代测序可在数小时内产出全基因组数据，但变异调用仍需数小时甚至数天，成为临床应用的瓶颈。FreeBayes作为广泛使用的单线程变异调用器，虽算法适合并行化，却缺乏GPU加速实现。cuBayes采用CUDA和原子/分子架构，将全基因组SNV调用缩短至1分钟，且与CPU版本一致率达99.97%。该工作不仅加速了FreeBayes，还提供了可复用的加速框架，有助于推动其他序列分析算法的GPU移植。"
source: biorxiv
selection_source: fresh_fetch
motivation: 变异调用是测序流程中的时间瓶颈，FreeBayes单线程实现无法充分利用并行性，急需GPU加速以支持临床场景。
method: 基于CUDA实现FreeBayes的胚系SNV调用，采用原子/分子架构分离可重用单元与算法特定逻辑，实现高效并行。
result: "在单个RTX 6000 Ada GPU上，1分钟内完成60x全基因组分析，与CPU结果一致率达99.97%。"
conclusion: cuBayes显著加速FreeBayes，并提供了可复用的并行化架构，为其他序列分析算法的GPU移植奠定基础。
---

## 摘要
下一代测序现在可以在几小时内产生全基因组数据，但下游变异检测仍然需要数小时到数天，成为将基因组分析排除在时间关键的临床环境中的瓶颈。GPU加速提供了一条自然的路径——变异检测在基因组位置上固有地可并行化——然而，将现有算法移植到GPU硬件的开源基础设施仍然有限，使得许多广泛使用的工具缺乏加速实现。FreeBayes，一种基于单倍型的变异检测工具，是1000基因组计划和多样本肿瘤进化分析的核心，体现了这一差距：尽管其算法适合并行化，但原生是单线程的。我们提出了cuBayes，一个FreeBayes生殖系SNV检测的CUDA实现，在单个NVIDIA RTX 6000 Ada GPU上在一分钟内完成HG002和HG004的2x250bp Illumina 60x全基因组分析（相比之下，基于手动区域CPU并行化需要数小时甚至数天），同时产生与CPU参考99.97%一致性的变异检测结果。cuBayes围绕原子/分子架构构建，其中可重用的功能单元（BAM解压、位置堆叠、批次协调）与算法特定逻辑清晰分离，提供了一个旨在支持加速其他序列分析算法而无需重复底层工程的基础。

## Abstract
Next-generation sequencing now produces whole-genome data in hours, but downstream variant calling remains a multi-hour to multi-day bottleneck that excludes genomic analysis from time-critical clinical settings. GPU acceleration offers a natural path forward -- variant calling is inherently parallelizable across genomic positions -- yet open-source infrastructure for porting existing algorithms to GPU hardware remains limited, leaving many widely-used tools without accelerated implementations. FreeBayes, a haplotype-based variant caller central to the 1000 Genomes Project and to multi-sample tumor evolution analyses, exemplifies this gap: it is natively single-threaded despite its algorithmic suitability for parallelization. We present cuBayes, a CUDA implementation of FreeBayes germline SNV calling that completes HG002 and HG004 2x250bp Illumina 60x whole-genome analysis in one minute (as opposed to hours if not days with manual region-based CPU parallelization) on a single NVIDIA RTX 6000 Ada GPU, while producing variant calls with 99.97% concordance to the CPU reference. cuBayes is structured around an atom/molecule architecture in which reusable functional units (BAM decompression, position-wise pileup, batch coordination) are cleanly separated from algorithm-specific logic, providing a foundation intended to support acceleration of additional sequence analysis algorithms without redundant low-level engineering.