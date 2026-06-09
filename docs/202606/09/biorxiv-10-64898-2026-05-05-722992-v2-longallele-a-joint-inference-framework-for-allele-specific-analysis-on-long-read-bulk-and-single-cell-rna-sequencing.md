---
title: "LongAllele: a joint inference framework for allele-specific analysis on long-read bulk and single-cell RNA sequencing"
title_zh: "LongAllele: 一种用于长读长批量及单细胞RNA测序等位基因特异性分析的联合推断框架"
authors: "Xu, Z., Wang, K."
date: 2026-06-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.05.722992v2.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 等位基因特异性分析的联合推断框架，改进单倍型推断和检验，可用于因果变异识别
tldr: 现有等位基因分析方法在单倍型推断和检验中存在缺陷，如分步流程未充分利用SNV连锁信息、忽视不可定相读段导致假阳性。LongAllele采用EM算法联合推断变异、单倍型与读段分配，引入定相感知检验，支持基因、转录本和局部事件水平的等位基因分析。在GTEx、PBMC、海马体及阿尔茨海默病皮层数据中，LongAllele揭示了表达水平比isoform水平更强的组织依赖性，并发现稀有剪接位点变异。该框架提升了等位基因分析的准确性和完整性，提供了跨尺度的cis调控视图。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法在单倍型推断和等位基因检验中分离步骤，未充分利用长读段连接信息，且忽略不可定相读段导致假阳性。
method: 提出LongAllele框架，使用EM算法联合推断杂合变异、单倍型结构和读段-单倍型分配，并引入定相感知检验处理不可定相读段。
result: 在多组织、单细胞和疾病数据中，LongAllele揭示表达水平等位基因调控的组织依赖性更强，并检测到被遗漏的罕见剪接位点变异。
conclusion: LongAllele提供了全面、准确的等位基因分析，减少假阳性，支持多尺度cis调控研究。
---

## 摘要
基于RNA测序的等位基因特异性分析是表征顺式调控效应的有力方法。然而，现有方法在单倍型推断和等位基因检验方面仍然存在局限。其单倍型推断工作流将变异检测、单倍型分型和读段-单倍型分配分为连续步骤，未能充分利用读段内的单核苷酸变异（SNV）连锁信息，并将错误传播到下游的等位基因分析中。在检验阶段，它们忽略了缺少杂合SNV的不可分型读段，导致结果偏倚并增加假阳性，且在基因、转录本和局部事件水平的变异效应分析上仍不完整。在此，我们提出LongAllele，一个统计框架，采用期望最大化算法从长读长批量及单细胞RNA测序中联合推断杂合变异、单倍型结构和读段-单倍型分配。LongAllele进一步引入了分型感知的检验方法，明确考虑了不可分型读段，避免了在单倍型信息不完整时假阳性结果增多的问题。它还支持全面的等位基因检验，涵盖基因水平的等位基因特异性表达（ASE）、转录本水平的等位基因特异性转录本使用（ASTU），以及局部事件水平的单倍型相关外显子和剪接连接使用（HAEU和HAJU），从而在生物学背景下提供顺式调控的多尺度视图。我们将LongAllele应用于长读长RNA测序数据集，涵盖GTEx（多组织批量）、外周血单核细胞（单细胞）、人类海马体（单细胞核）以及来自两个阿尔茨海默病（AD）病例-对照队列的人类皮层（批量，Oxford Nanopore和PacBio）。LongAllele一致地揭示了表达水平比转录本水平的等位基因调控具有更大的上下文依赖性，涉及组织、细胞类型和疾病状态，并精确指出了高影响调控变异，包括单独的变异检测工具遗漏的罕见剪接位点突变。它还进一步表明，纯化选择在基因和转录本水平上约束了等位基因不平衡，并在不同长读长平台上解析了个体转录组中与AD相关的变异效应。

## Abstract
Allele-specific analysis from RNA-seq is a powerful approach to characterize cis-regulatory effects. However, existing methods remain limited in both haplotype inference and allelic testing. Their haplotype-inference workflows separate variant calling, haplotype phasing, and read-haplotype assignment into sequential steps, failing to fully exploit within-read single-nucleotide variant (SNV) linkage information and propagating errors into downstream allelic analysis. At the testing stage, they ignore non-phasable reads lacking heterozygous SNVs, biasing calls and inflating false positives, and remain incomplete across gene-, isoform-, and local-event-level variant effects. Here, we present LongAllele, a statistical framework that employs an expectation-maximization algorithm to jointly infer heterozygous variants, haplotype structure, and read-haplotype assignments from long-read bulk and single-cell RNA sequencing. LongAllele further introduces phasability-aware testing that explicitly accounts for non-phasable reads, avoiding inflated false-positive calls when haplotype information is incomplete. It also enables comprehensive allelic testing across gene-level allele-specific expression (ASE), isoform-level allele-specific transcript usage (ASTU), and local-event-level haplotype-associated exon and junction usage (HAEU and HAJU), providing a multi-scale view of cis-regulation across biological contexts. We applied LongAllele to long-read RNA-seq datasets spanning GTEx (multi-tissue bulk), peripheral blood mononuclear cells (single-cell), human hippocampus (single-nucleus), and human cortex from two Alzheimer's disease (AD) case-control cohorts (bulk, Oxford Nanopore and PacBio). LongAllele consistently revealed greater context dependence in expression-level than isoform-level allelic regulation across tissues, cell types, and disease states, and pinpointed high-impact regulatory variants including rare splice-site mutations missed by standalone variant callers. It further showed that purifying selection constrains allelic imbalance at both gene and isoform levels and resolved AD-associated variant effects in individual transcriptomes across long-read platforms.