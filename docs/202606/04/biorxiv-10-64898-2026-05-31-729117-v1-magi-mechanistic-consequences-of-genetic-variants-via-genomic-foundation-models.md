---
title: "MAGI: Mechanistic Consequences of Genetic Variants via Genomic Foundation Models"
title_zh: MAGI：通过基因组基础模型解析遗传变异的机制后果
authors: "Ofer, D., Zok, S., Linial, M."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.31.729117v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 使用基因组基础模型（transformer）量化变异效应，属于GWAS分析的机器学习方法
tldr: 临床变异解读缺乏机制性证据，现有方法多为黑盒。MAGI利用基因组Transformer模型量化变异在3623个功能轨道上的效应，通过确定性逻辑层映射到分子后果。在ClinVar基准测试中，MAGI与临床诊断高度一致，并能重现起始密码子丢失等经典机制。该方法还可应用于非人类基因组，为意义未明变异提供可实验验证的假设。
source: biorxiv
selection_source: fresh_fetch
motivation: 临床变异解读需要机制性证据，但现有预测器和基因组基础模型缺乏可解释性，仅提供致病性标签而无机制洞见。
method: MAGI通过基因组Transformer量化变异对3623个功能轨道的影响，整合多组学数据和分子注释，利用确定性逻辑层映射出显式的分子后果。
result: 在ClinVar基准测试中，MAGI导出的后果与临床诊断高度一致，能准确重现经典致病机制，并在冲突案例中提出可验证的替代解释。
conclusion: MAGI建立了可泛化的框架，从黑盒致病性预测走向机制性解读，为功能基因组学中的变异发现提供可检验的假设。
---

## 摘要
临床变异解读需要机制层面的证据来指导诊断并阐明突变的生物学后果。然而，现有的计算预测工具和基因组基础模型很大程度上仍是黑箱，提供致病性标签时缺乏机制洞察或临床可操作性。在此，我们提出MAGI（基因组影响的机制注释），一种通过将临床相关变异解读与机制基因组分析相结合来弥合这一可解释性差距的新方法。MAGI流程利用基因组变压器模型量化DNA变异在3,623个功能轨道上的效应，涵盖调控特征、多组学数据集（包括组织特异性和染色质状态），以及基因和转录本的21个额外分子注释。这些信号通过一个确定性逻辑层整合，将单核苷酸变异和插入缺失映射到明确的分子后果。我们针对从ClinVar整理出的临床理由对MAGI推导的后果进行基准测试，观察到随着功能破坏程度的增大而增强的高度一致性。MAGI准确重现了典型的致病机制，包括起始密码子丢失、剪接位点破坏和调控元件扰动，与ClinVar注释一致。我们进一步展示了解读冲突或不完整机制解释以及需要复杂推理的变异案例研究。值得注意的是，MAGI也适用于非人类基因组，并在多物种OMIA致病性变异上进行了评估。总体而言，MAGI建立了一个可推广的框架，超越临床诊断，能够实现功能基因组学中的机制发现，为意义不明确的变异（VUS）和临床解读不一致的变异生成基于机制、可检验的假设。在多个案例中，MAGI提出了挑战现有注释的替代解释，提供了透明的理由和实验上可处理的预测。

## Abstract
Clinical variant interpretation requires mechanism-aware evidence to guide diagnosis and clarify the biological consequences of mutations. However, existing computational predictors and genomic foundation models largely function as black boxes, providing pathogenicity labels with limited mechanistic insight or clinical actionability. Here, we present MAGI (Mechanistic Annotation of Genomic Impacts), a novel method that bridges this interpretability gap by unifying clinically relevant variant interpretation with mechanistic genomic analysis. MAGI pipeline leverages a genomic transformer model to quantify the effects of DNA variants across 3,623 functional tracks, encompassing regulatory features, multi-omics datasets, including tissue specificity and chromatin states, and 21 additional molecular annotations of genes and transcripts. These signals are integrated through a deterministic logic layer that maps single-nucleotide variants and indels to explicit molecular consequences. We benchmark MAGI-derived consequences against clinical rationales curated from ClinVar and observe strong concordance that scales with the magnitude of functional disruption. MAGI accurately recapitulates canonical pathogenic mechanisms, including start codon loss, splice site disruption, and regulatory element perturbation, consistent with ClinVar annotations. We further present case studies addressing conflicting or incomplete mechanistic interpretations, as well as variants requiring complex inference. Notably, MAGI is also applicable to non-human genomes and was evaluated on multispecies OMIA pathogenic variants. Collectively, MAGI establishes a generalizable framework that extends beyond clinical diagnostics to enable mechanistic discovery in functional genomics, generating mechanistically grounded, testable hypotheses for variants of uncertain significance (VUS) and variants with discordant clinical interpretations. In several cases, MAGI proposes alternative explanations that challenge existing annotations, providing transparent rationales and experimentally tractable predictions.