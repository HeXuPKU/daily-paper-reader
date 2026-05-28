---
title: "GAE-Δ: A Graph-Learning Framework for Gene Network Rewiring and Clinical Outcome Prediction from Multi-Omics Data"
title_zh: GAE-Δ：一种用于多组学数据中基因网络重连和临床结果预测的图学习框架
authors: "Tang, Z., Chen, Z., Chen, M., Wang, Y., Ennis, S., Niranjan, M., Ewing, R."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.21.726880v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 多组学整合框架用于表型特异性基因网络重连
tldr: 癌症进展与网络改变相关，多组学数据分析面临挑战。提出GAE-Δ框架，利用图自编码器对比两组学条件嵌入，量化基因网络角色转变，用于基因优先级和分类。在5个TCGA癌症类型中，预测性能优于MOFA+等基线，且识别出富集癌症驱动基因的转换基因（11-17倍富集）。该方法实现改进分类与生物学发现。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以捕捉多组学数据中表型相关的基因网络重构，线性方法遗漏关键生物信号。
method: 基于图自编码器，为两组学模态构建条件特异性基因图，联合训练生成共享嵌入，通过对比嵌入偏移刻画基因角色转变，并用于融合与分类。
result: 在5个TCGA数据集上，GAE-Δ在3个队列中AUC显著优于MOFA+，且发现的共识转移基因在3个队列中富集已知驱动基因（p<0.01，11-17倍）。
conclusion: GAE-Δ有效整合多组学数据，提升预测性能并捕获线性方法遗漏的生物学信息，助力机制发现。
---

## 摘要
癌症的进展和结果部分由遗传和/或环境扰动导致的分子网络变化驱动。这些网络变化体现在多个相互连接的网络层中，包括体细胞突变的积累、蛋白质-蛋白质相互作用的改变以及基因表达失调。本文描述了一种基于图自编码器的框架（Graph Autoencoder-Delta，GAE-Δ），用于表征跨多组学数据的表型特异性基因角色转换。给定分层为两个对比表型组的样本和一个先验基因相互作用网络，GAE-Δ为每个组学模态构建组特异性基因图，并为每个模态训练一个联合作用于两个组图的单一图自编码器，使得两个组条件嵌入共享一个共同潜空间。对比这些嵌入定义了每个基因的多组学嵌入移位表示，反映了其网络角色在不同表型背景下的重组。这些基因级别的移位随后用于无监督基因优先级排序、多组学后期融合和样本级分类。应用于具有生存终点的五种TCGA癌症类型，GAE-Δ与经典网络方法和多组学矩阵分解方法（MOFA+、iNMF）相比，实现了具有竞争力或更优的预测性能，在五个队列中的三个队列中AUC统计显著高于MOFA+，其余两个队列无统计差异。除了预测性能外，共识移位基因在五个队列中的三个中显著富集已知癌症驱动因子（超几何检验p < 0.01；富集倍数11-17倍），而矩阵分解基线在五个队列中的零个队列达到p < 0.05（最佳每癌症p = 0.06），表明GAE-Δ捕捉到了线性因子方法遗漏的生物信号。总之，GAE-Δ方法通过基于深度网络的疾病相关多组学数据整合，既改善了结果分类，也促进了生物学和机制性发现。

## Abstract
Cancer progression and outcomes are driven in part by changes to molecular networks that result from genetic and/or environmental perturbations. These network changes manifest across multiple interconnected network layers and include accumulation of somatic mutations, altered proteinprotein interactions and dysregulated gene-expression. Here we describe a graph autoencoder-based framework (Graph Autoencoder-Delta (GAE-{Delta})), for characterizing phenotype-specific gene role shifts across multi-omics data. Given samples stratified into two contrasting phenotypic groups and a prior gene interaction network, GAE-{Delta} constructs group-specific gene graphs for each omics modality and trains, for each modality, a single graph autoencoder jointly on both group graphs, so that the two group-conditional embeddings share a common latent space. Contrasting these embeddings defines a multi-omics embedding-shift representation for each gene that reflects how its network role reorganizes across phenotypic contexts. These gene-level shifts are subsequently used for unsupervised gene prioritization, multi-omics late fusion and sample-level classification. Applied to five TCGA cancer types with a survival endpoint, GAE-{Delta} achieves competitive or superior predictive performance compared with classical network-based methods and multi-omics matrix-factorisation methods (MOFA+, iNMF), with statistically significant AUC gains over MOFA+ in three of five cohorts and statistical ties on the remaining two. Beyond predictive performance, the consensus shift genes are significantly enriched for known cancer drivers in three of five cohorts (hypergeometric p < 0.01; 11-17x fold-enrichment), whereas matrix-factorisation baselines reach p < 0.05 in zero of five cohorts (best per-cancer p = 0.06), indicating that GAE-{Delta} captures biological signal that linear factor methods miss. In summary, the GAE-{Delta} approach provides for both improved outcome classification as well as for biological and mechanistic discovery through deep network-based integration of disease-associated multi-omics data.