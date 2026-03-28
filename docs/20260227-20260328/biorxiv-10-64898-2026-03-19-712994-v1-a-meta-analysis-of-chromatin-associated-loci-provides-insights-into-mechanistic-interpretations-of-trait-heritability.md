---
title: A meta-analysis of chromatin-associated loci provides insights into mechanistic interpretations of trait heritability
title_zh: 染色质相关位点的荟萃分析为性状遗传力的机制解释提供了见解
authors: "Dudek, M. F., Wenz, B. M., Voight, B. F., Almasy, L., Grant, S. F. A."
date: 2026-03-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.19.712994v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 研究可通过染色质开放性QTL（caQTL）检测到的弱效应变异的作用
tldr: 本研究针对GWAS位点与eQTL匹配率低的问题，通过对10项研究、3457个样本的染色质可及性定量性状位点（caQTL）进行荟萃分析，探讨了远端调控元件对性状遗传力的贡献。研究发现，相比eQTL，caQTL在功能重要基因和远端区域更为富集，能更灵敏地捕捉GWAS位点的分子效应。这一发现为理解非编码变异如何通过微弱或特定背景下的调控作用影响复杂疾病提供了新的机制见解。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712994-v1/fig-001.webp\", \"caption\": \"Table 1). We ran linkage-disequilibrium (LD) clumping to identify independent lead caQTLs, then 77 removed any SNPs in strong LD (r2>0.8) with protein-altering SNPs. In order to compare caQTLs 78 to GTEx eQTLs, we also removed SNPs further than 1 Mb from a transcription start site (TSS), in 79 line with what was not tested by GTEx for eQTLs; this resulted in a list of 104,024 caQTLs. We 80 then ran this catalog of caQTLs through the computational pipeline utilized by Mostafavi et al., 81 allowing us to compare eQTLs, caQTLs, and GWAS hits directly (Methods). Briefly, we computed 82 average values for a range of SNP and gene properties in each list of caQTLs, eQTLs, and GWAS 83 hits. For gene properties, we first assigned every SNP to its nearest gene (creating lists of “GWAS 84 genes”, “eQTL genes”, and “caQTL genes”, Fig. 1B), and considered the properties of that gene. 85 To account for potential confounding effects due to differences between caQTLs, eQTLs, and 86 GWAS hits, we also ran this analysis on lists of control SNPs for caQTLs, eQTLs, and GWAS hits, 87 matched for minor allele frequency (MAF), LD score, and gene density (Fig 1C). See Methods 88 for full details. 89\", \"page\": 5, \"index\": 1, \"width\": 1039, \"height\": 303}]"
motivation: 旨在解决GWAS关联位点在功能重要基因和远端调控区缺乏eQTL解释的难题。
method: 整合并分析了来自不同组织和细胞类型的10项研究中超过10万个caQTL位点。
result: 证明了caQTL在识别受选择约束基因的调控变异方面比eQTL更有效，且能更灵敏地捕捉远端元件的微弱调控效应。
conclusion: caQTL是捕捉GWAS位点分子后果的敏感工具，为解析疾病相关位点的功能机制提供了与eQTL互补的关键信息。
---

## 摘要
通过全基因组关联研究 (GWAS) 发现的绝大多数性状相关位点位于非编码区，但其中大多数在统计学上与已发现的表达定量性状位点 (eQTLs) 缺乏一致性。特别是，eQTLs 在基因远端区域和“功能重要”基因（即具有强选择约束和复杂调控格局的基因）中出现频率较低，这可能是由于高效应变异的选择性耗竭所致。在本研究中，我们探讨了通过远端调控元件传递的、对表达影响较弱的变异的作用，这些变异可作为染色质可及性 QTLs (caQTLs) 被检测到。我们汇总了来自 10 项研究的 caQTL 数据，涵盖了不同的组织、细胞类型和细胞系，代表了 3,457 个样本中的 104,024 个先导 caQTLs。我们发现，在各种基因属性中，在功能重要基因处发现 caQTLs 的频率高于 eQTLs。这些观察结果与一个模型一致，即许多 eQTLs 和 GWAS 命中位点是通过对调控元件的遗传效应介导的，而这些效应对基因表达的影响可能较弱或具有背景依赖性。我们的结果表明，在捕捉 GWAS 命中位点的分子后果方面，caQTL 的发现比 eQTL 更敏感，并且可以通过揭示额外疾病相关位点的功能机制，为 eQTL 提供补充信息。

## Abstract
The vast majority of trait-associated loci discovered through genome-wide association studies (GWAS) are non-coding, yet most lack statistical alignment with any discovered expression quantitative trait loci (eQTLs). In particular, eQTLs are depleted at gene-distal regions and at "functionally important" genes - those with strong selective constraint and complex regulatory landscapes - likely due to selective depletion of high-effect variants. Here, we investigate the role of variants with weaker effects on expression transmitted through distal regulatory elements, which are detectable as chromatin accessibility QTLs (caQTLs). We aggregated caQTL data from ten studies derived across different tissues, cell-types and lines, representing 104,024 lead caQTLs across 3,457 samples. We found that, across a range of gene properties, caQTLs are discovered at functionally important genes more often than eQTLs. These observations are consistent with a model in which many eQTLs and GWAS hits are mediated through genetic effects on regulatory elements, which may have weak or context-dependent effects on gene expression. Our results suggest that caQTL discovery is more sensitive than eQTL discovery in capturing the molecular consequences of GWAS hits, and can provide complimentary information to eQTLs by implicating functional mechanisms of additional disease-associated loci.