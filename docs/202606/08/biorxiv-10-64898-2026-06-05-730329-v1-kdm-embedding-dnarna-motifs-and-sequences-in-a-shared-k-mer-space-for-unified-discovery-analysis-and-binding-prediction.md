---
title: "KDM: embedding DNA/RNA motifs and sequences in a shared k-mer space for unified discovery, analysis and binding prediction"
title_zh: KDM：在共享k-mer空间中对DNA/RNA基序和序列进行嵌入，实现统一发现、分析与结合预测
authors: "Fumagalli, L., Becchi, T., Cereda, M., Pozzoli, U."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730329v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 提供k-mer嵌入框架，可用于GWAS变异的功能注释
tldr: "DNA/RNA基序发现与结合预测中，可解释的PWM与高性能黑箱模型存在分裂。KDM框架将基序和序列表示为共享k-mer字典上的概率分布，通过Hellinger变换统一嵌入，利用Bhattacharyya系数实现打分、匹配、发现和预测。在千余实验上，KDMMap匹配CentriMo的84%基序排名，KDM-LRLM媲美或超越八种深度学习方法。该框架提供单一可解释表示，覆盖完整基序分析工作流。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基序分析方法在可解释性和性能之间分裂，缺乏统一表示。
method: 将基序和序列嵌入共享k-mer概率空间，通过Hellinger变换和Bhattacharyya系数构建统一几何。
result: "在TF和RBP实验中，KDMMap匹配CentriMo的84%和79%排名；KDM-LRLM在多数数据集上匹敌深度学习方法。"
conclusion: KDM以单一可解释表示统一了基序发现、比对和结合预测全流程。
---

## 摘要
在DNA和RNA序列中，基序发现和结合位点预测是调控基因组学的核心任务，然而方法论领域目前分裂为可解释但僵化的位置权重矩阵（PWMs）与高性能但 opaque 的机器学习模型。我们提出KDM，一个统一框架，其中基序和序列均被表示为共享k-mer字典上的概率分布，并通过Hellinger变换嵌入。这种共同的几何结构使得利用单一原语——Bhattacharyya系数，即可实现基序-序列评分、基序-基序比较、从头发现和结合预测。我们基于该表示实例化了四个工具：KDMMap用于位置富集分析，KDMMatch用于信息内容感知的基序匹配，KDMFind通过投影非负矩阵分解进行无监督基序发现，以及KDM-LRLM用于基于Lasso正则化逻辑回归的结合预测。在1,324个转录因子ChIP-seq和161个RBP eCLIP实验中，KDMMap在84%的TF和79%的RBP实验中匹配了CentriMo的基序排名；KDMMatch与Tomtom在74.5%的TF基序注释上一致。在涵盖2,475个实验的四个数据集的结合预测中，KDM-LRLM匹配或超越了八个深度学习模型和三个基于k-mer的竞争者。值得注意的是，AI方法仅在训练集大小的前四分之一中超越了k-mer方法，这表明是数据规模而非架构驱动了近期深度模型的主导地位。KDM在整个基序分析工作流程中提供了一个单一的可解释表示。

## Abstract
Motif discovery and binding-site prediction in DNA and RNA sequences are central tasks in regulatory genomics, yet the methodological landscape is split between interpretable but rigid position weight matrices (PWMs) and high-performing but opaque machine-learning models. We present KDM, a unifying framework in which both motifs and sequences are represented as probability distributions over a shared k-mer dictionary, embedded via the Hellinger transformation. This common geometry enables motif-sequence scoring, motif-motif comparison, de novo discovery, and binding prediction with a single primitive, the Bhattacharyya coefficient. We instantiate four tools on this representation: KDMMap for positional enrichment analysis, KDMMatch for information-content-aware motif matching, KDMFind for unsupervised motif discovery via projective non-negative matrix factorization, and KDM-LRLM for binding prediction with Lasso-regularized logistic regression. Across 1,324 transcription-factor ChIP-seq and 161 RBP eCLIP experiments, KDMMap matches CentriMo's motif rankings in 84% of TF and 79% of RBP experiments, and KDMMatch agrees with Tomtom on motif annotation in 74.5% of TFs. On binding prediction across four datasets covering 2,475 experiments, KDM-LRLM matches or exceeds eight deep-learning and three k-mer-based competitors. Notably, AI methods overtake k-mer methods only in the top quartile of training-set size, indicating that data scale, not architecture, drives the recent dominance of deep models. KDM provides a single interpretable representation across the full motif-analysis workflow.