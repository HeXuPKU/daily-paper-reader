---
title: Distinct cellular DNA methylation mechanisms underlie common and rare genetic risk for brain disorders
title_zh: 不同的细胞DNA甲基化机制构成了脑部疾病常见和罕见遗传风险的基础
authors: "Zhou, J., Liu, C., Liu, X., Zhang, Y., Wei, Y., Shin, J. H., Maher, B., LIU, C., Luo, C., Wang, K., Weinberger, D., Han, S."
date: 2026-03-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.09.710649v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 通过序列预测DNA甲基化以分析遗传风险的深度学习框架
tldr: 本研究开发了一个深度学习框架，利用46个脑区的单核DNA甲基化数据，预测了186种脑细胞亚型中mCG和mCH的变异效应。研究揭示了常见遗传变异主要通过影响兴奋性神经元的mCG增加脑疾病风险，而自闭症相关的罕见从头突变则优先干扰保守神经调节区域的mCH。这一发现表明常见和罕见非编码变异通过不同的DNA甲基化机制影响脑部疾病。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-09-710649-v1/fig-001.webp\", \"caption\": \"\", \"page\": 34, \"index\": 1, \"width\": 1920, \"height\": 1080}]"
motivation: 旨在阐明非编码遗传变异如何通过特定脑细胞类型的DNA甲基化（mCG和mCH）机制影响脑部疾病风险。
method: 开发了一种深度学习框架，基于46个脑区的单核DNA甲基化谱，预测186种脑细胞亚型中序列对mCG和mCH的影响。
result: 发现常见变异主要通过兴奋性神经元的mCG富集遗传力，而自闭症的罕见从头突变则显著影响保守区域的mCH。
conclusion: 研究证明了常见和罕见非编码变异通过截然不同的DNA甲基化机制（mCG与mCH）贡献于脑部疾病的遗传风险。
---

## 摘要
非编码遗传变异与脑部疾病风险相关，但其在特定脑细胞类型中发挥作用的机制尚不明确。DNA甲基化（DNAm）是大脑中一种具有高度细胞类型特异性的调控层，可能介导非编码遗传风险，然而CG位点甲基化（mCG）和神经元富集的非CG位点甲基化（mCH）是否对该风险有不同的贡献仍是未知的。本研究开发了一个深度学习框架，利用来自46个脑区的单核DNAm图谱，从DNA序列预测DNAm，并评估了186个脑细胞亚型中mCG和mCH的变异效应。模型揭示了两种甲基化背景下存在不同的转录因子（TF）程序，其中与mCH相关的TF表现出更强的进化约束。预测的变异效应在方向和幅度上均与细胞类型匹配的甲基化定量性状位点（mQTL）高度一致。与影响mCH的变异相比，预测影响mCG（特别是在兴奋性神经元中）的常见变异在脑相关性状的遗传力富集方面显著更高。相比之下，自闭症中的非编码新生突变优先扰动保守神经元调控区域的mCH，而非mCG。这一模式在两个独立队列（共计5,782名先证者和4,053名未受影响的同胞）中得到了验证。总之，这些发现表明，常见和罕见的非编码变异通过不同的DNA甲基化机制导致脑部疾病。

## Abstract
Noncoding genetic variation contributes to brain disorder risk, but the mechanisms through which it acts in specific brain cell types remain unclear. DNA methylation (DNAm), a highly cell type-specific regulatory layer in the brain, may mediate noncoding genetic risk, yet whether methylation at CG (mCG) and neuron-enriched non-CG (mCH) dinucleotides contribute differently to that risk remains unknown. Here we develop a deep learning framework that predicts DNAm from DNA sequence and estimates variant effects across 186 brain cell subtypes in both mCG and mCH, leveraging single-nucleus DNAm profiles from 46 brain regions. The models reveal distinct transcription factor (TF) programs underlying the two methylation contexts, with mCH-associated TFs showing stronger evolutionary constraint. Predicted variant effects agree closely with cell type-matched mQTLs in both direction and magnitude. Common variants predicted to affect mCG, particularly in excitatory neurons, show substantially greater heritability enrichment for brain-related traits than variants affecting mCH. By contrast, noncoding de novo mutations in autism preferentially perturb mCH, but not mCG, at conserved neuronal regulatory regions. This pattern is replicated across two independent cohorts totaling 5,782 probands and 4,053 unaffected siblings. Together, these findings indicate that common and rare noncoding variants contribute to brain disorders through distinct DNA methylation mechanisms.