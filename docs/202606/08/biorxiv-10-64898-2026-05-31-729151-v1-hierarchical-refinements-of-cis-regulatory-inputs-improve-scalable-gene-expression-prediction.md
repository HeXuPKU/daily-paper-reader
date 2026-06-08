---
title: Hierarchical refinements of cis-regulatory inputs improve scalable gene expression prediction
title_zh: 顺式调控输入的分层精炼提升可扩展的基因表达预测
authors: "Zhang, Q., Xing, M., Liao, Q., Li, Z., Huang, D.-S."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.31.729151v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 两阶段选择框架用于从顺式调控元件预测基因表达，适用于GWAS功能基因组学
tldr: 现有Transformer模型对数百个候选cCRE进行全局注意力，导致因果信号稀释，难以准确预测基因表达。本文提出两阶段选择性框架TSSF，先对每个cCRE进行核苷酸级掩码，再围绕目标基因进行cCRE级选择，通过信息瓶颈先验实现层级精炼。在70个人类细胞类型中，TSSF显著提升表达预测准确性和增强子-基因优先级排序，跨细胞系和细胞类型特异基准均优于强基线。该方法还通过距离衰减先验和染色质接触增强改进远程调控链接恢复，基序分析验证了可解释性，为高维调控输入的规模化建模提供了通用策略。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有Transformer模型对数百个候选cCRE进行全局注意力，导致因果信号稀释，难以准确预测基因表达。
method: 提出两阶段选择性框架TSSF，包括核苷酸级掩码和cCRE级选择，借助信息瓶颈先验和全Transformer架构。
result: 在70种人类细胞类型中，TSSF提升表达预测和增强子-基因优先级排序，跨细胞系和细胞类型特异基准均优于强基线。
conclusion: TSSF实现可扩展、可解释的基因表达预测，距离衰减先验和染色质接触增强恢复远程链接，支持调控机制分析。
---

## 摘要
解析顺式调控元件（CREs）与靶基因表达之间的关系一直是分子生物学中的挑战性问题。然而，从数百个候选顺式调控元件（cCREs）预测基因表达需要能够处理长序列、含噪声输入同时保留可解释调控结构的模型。现有的基于Transformer的方法通常关注所有核苷酸和所有周围cCREs，当数百个元件竞争有限模型容量时，会稀释因果信号。我们提出了一种两阶段选择性框架（TSSF），通过分层精炼实现：在每个cCRE内进行核苷酸级别掩码，然后在每个基因周围进行cCRE级别选择，利用信息瓶颈先验和完全基于Transformer的架构。在70个人类细胞类型和组织中，TSSF及其轻量级变体在表达预测和增强子-基因优先排序方面相对于强基线有所改进，包括在跨细胞系和细胞类型特异性基准上。预测分层分析启发了一种距离衰减先验，使注意力与长程调控几何结构对齐，而染色质接触增强改善了远端连接的恢复。高置信度预测的基序分析恢复了近端和远端调控程序，支持机制可解释性。TSSF为基因组学中高维调控输入的可扩展、可解释建模提供了通用策略。

## Abstract
Deciphering the relationships between cis-regulatory elements (CREs) and target gene expression has long been a challenging problem in molecular biology. However, predicting gene expression from hundreds of candidate cis-regulatory elements (cCREs) requires models that scale to long, noisy inputs while retaining interpretable regulatory structure. Existing Transformer-based approaches typically attend over all nucleotides and all surrounding cCREs, diluting causal signals when hundreds of elements compete for limited model capacity. Here we introduce a two-stage selective framework (TSSF) that performs hierarchical refinements: nucleotide-level masking within each cCRE, followed by cCRE-level selection around each gene, implemented with information-bottleneck priors and a fully Transformer-based architecture. Across 70 human cell types and tissues, TSSF and lightweight variants improve expression prediction and enhancer-gene prioritization relative to strong baselines, including on cross-cell-line and cell-type-specific benchmarks. Prediction-stratified analysis motivates a distance-decay prior that aligns attention with long-range regulatory geometry, and chromatin-contact augmentation improves recovery of distal links. Motif analyses of high-confidence predictions recover proximal and distal regulatory programs, supporting mechanistic interpretability. TSSF offers a general strategy for scalable, interpretable modeling of high-dimensional regulatory inputs in genomics.