---
title: "DCS Tools: A high-performance, resource-efficient and scalable computing suite for population-scale genomic analysis and data compression"
title_zh: DCS Tools：一套用于群体规模基因组分析和数据压缩的高性能、资源高效且可扩展的计算套件
authors: "Gong, C., Yuan, D., Zhao, Z., Li, X., Chen, Y., Yang, Q., Wan, R., Li, S., Zhang, Y."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.13.711253v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 用于大规模人群基因组分析的高性能计算套件
tldr: 针对大规模基因组分析面临的计算瓶颈和存储压力，本研究开发了DCS Tools，这是一套专为标准CPU架构优化的高性能计算套件。该套件在无需特殊硬件的情况下，将30X全基因组测序分析速度提升了16倍，并集成了高效的联合变异检测与数据压缩工具，显著降低了存储成本，为PB级基因组分析提供了低成本、可扩展的解决方案。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711253-v2/fig-001.webp\", \"caption\": \"Figure 1. WGS Variant Calling Accuracy\", \"page\": 8, \"index\": 1, \"width\": 875, \"height\": 412}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711253-v2/fig-002.webp\", \"caption\": \"Table 1. Modules in DCS Tools\", \"page\": 8, \"index\": 2, \"width\": 891, \"height\": 418}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711253-v2/fig-003.webp\", \"caption\": \"Table 2. Performance benchmarks of DCS Tools on WGS data (32 threads)\", \"page\": 8, \"index\": 3, \"width\": 891, \"height\": 281}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711253-v2/fig-004.webp\", \"caption\": \"Table 4. Joint Calling Performance Across Different Cohort Sizes\", \"page\": 9, \"index\": 4, \"width\": 868, \"height\": 305}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711253-v2/fig-005.webp\", \"caption\": \"Table 7. Compression Performance on Population-Scale VCF Files with VarArc\", \"page\": 9, \"index\": 5, \"width\": 750, \"height\": 311}]"
motivation: 传统基因组分析流程资源消耗大且依赖昂贵的专用硬件，难以满足大规模人群基因组研究的计算与存储需求。
method: 开发了基于标准CPU优化的高性能套件DCS Tools，包含加速分析流程、百万级联合检测工具DPGT以及高效压缩工具SeqArc和VarArc。
result: "在32线程环境下，处理30X WGS样本仅需1.79小时，提速16倍，且FASTQ和VCF存储空间分别减少了80%和66%。"
conclusion: DCS Tools为大规模基因组学研究提供了一个高效、低成本且不依赖特定硬件的计算与存储优化方案。
---

## 摘要
群体规模基因组学的出现给计算基础设施和存储带来了巨大的瓶颈。传统的 BWA-GATK 最佳实践（Best Practices）需要海量资源，而大多数现有的加速方案依赖于 GPU 或 FPGA 等专用硬件，这增加了成本并限制了部署。为了解决这一问题，我们开发了 DCS Tools，这是一个针对标准 CPU 架构优化的计算套件。在 32 线程实例上，DCS Tools 仅需 1.79 小时即可完成 30X WGS 样本从原始 FASTQ 到变异检测的处理，与传统流水线相比，在无需额外硬件的情况下实现了 16 倍的加速。该套件集成了用于百万级联合分型（joint calling）的 DPGT，并引入了 SeqArc 和 VarArc，与 GZIP 相比，它们分别可减少高达 80%（FASTQ）和 66%（VCF）的存储占用。DCS Tools 为 PB 级基因组分析提供了一种高性价比、硬件无关的解决方案。

## Abstract
The advent of population-scale genomics has created significant bottlenecks in computational infrastructure and storage. Traditional BWA-GATK Best Practices require massive resources, while most existing acceleration solutions depend on specialized hardware like GPUs or FPGAs, increasing costs and limiting deployment. To address this, we developed DCS Tools, a high-performance suite optimized for standard CPU architectures. DCS Tools processes a 30X WGS sample from raw FASTQ to variant calls in just 1.79 hours on a 32-thread instance, a 16-fold speedup over traditional pipelines without additional hardware. The suite integrates DPGT for million-scale joint calling and introduces SeqArc and VarArc, which reduce storage footprints by up to 80% (FASTQ) and 66% (VCF) compared to GZIP. DCS Tools offers a cost-effective, hardware-agnostic solution for petabyte-scale genomic analysis.