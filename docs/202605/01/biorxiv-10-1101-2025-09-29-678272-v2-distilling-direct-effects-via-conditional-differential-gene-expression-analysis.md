---
title: Distilling Direct Effects via Conditional Differential Gene Expression Analysis
title_zh: 通过条件差异基因表达分析提取直接效应
authors: "Gu, J., Skelton, A., Staley, J., Popson, P. O., Peng, L., Song, X., Knowles, J. K., He, Z."
date: 2026-04-30
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.29.678272v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 在 RNA-seq 中区分直接生物效应与共表达相关的框架
tldr: 传统的差异基因表达（DGE）分析常混淆直接生物学效应与基因共表达产生的相关性。本研究发现大部分差异表达基因仅是“乘客”基因。为此，作者提出了条件差异基因表达（CDGE）分析框架，利用GhostKnockoff和Lasso回归识别与性状有直接关联的基因。CDGE能有效控制错误发现率，且识别出的基因在生物学功能富集上表现更优，为功能验证和药物研发提供了更精准的候选基因。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的差异表达分析无法区分直接生物学效应与由基因共表达引起的间接关联，导致研究者可能过度解读结果。
method: 提出CDGE框架，通过GhostKnockoff程序和Lasso回归对基因与性状的条件关联进行检验，并兼容现有DGE流程的统计量。
result: CDGE识别出的基因介导了大多数其他差异基因的效应，且在蛋白质相互作用和生物通路富集方面显著优于传统DGE。
conclusion: 区分直接效应与介导效应对于筛选功能性基因和治疗靶点至关重要，CDGE为转录组数据分析提供了更可靠的工具。
---

## 摘要
差异基因表达 (DGE) 分析是解释 RNA 测序数据的基础，但它将直接生物学效应与通过基因共表达传播的相关性混为一谈。在三个 RNA 测序数据集（包括一个全基因组规模的 perturb-seq 实验）中，我们发现只有一小部分差异表达基因对感兴趣的性状具有直接效应，而大多数是无向的或“乘客”基因，其关联是通过其他基因介导的。为了区分直接效应基因，我们引入了条件差异基因表达 (CDGE) 分析，这是一个测试每个基因与感兴趣性状之间的条件关联而非边际关联的框架。CDGE 通过带有 lasso 回归的 GhostKnockoff 程序实现，可提供错误发现率控制，在现有 DGE 流程的汇总统计量上运行，并能处理批次效应。CDGE 识别的基因介导了大多数其他差异表达基因的效应，并且与 DGE 识别的基因相比，在已知蛋白质-蛋白质相互作用和生物学通路中表现出更强的富集。这些结果表明，该领域一直在系统性地过度解读 DGE 输出，而区分直接效应与介导效应对于确定功能性后续研究和治疗开发的基因优先级至关重要。

## Abstract
Differential gene expression (DGE) analysis is foundational for interpreting RNA sequencing data, but it conflates direct biological effects with correlations propagated through gene co-expression. Across three RNA sequencing datasets (including a genome-scale perturb-seq experiment), we find that only a small fraction of differentially expressed genes have direct effects on the trait of interest, while the majority are undirected or passengers whose associations are mediated through other genes. To distinguish direct effect genes, we introduce conditional differential gene expression (CDGE) analysis, a framework that tests for conditional rather than marginal association between each gene and the trait of interest. Implemented via the GhostKnockoff procedure with lasso regression, CDGE delivers false discovery rate control, operates on summary statistics from existing DGE pipelines, and accommodates batch effects. The genes identified by CDGE mediate the effects of most other differentially expressed genes and show stronger enrichment for known protein-protein interactions and biological pathways than DGE-identified genes. These results suggest that the field has been systematically over-interpreting DGE outputs, and that distinguishing direct from mediated effects is essential for prioritizing genes for functional follow-up and therapeutic development.