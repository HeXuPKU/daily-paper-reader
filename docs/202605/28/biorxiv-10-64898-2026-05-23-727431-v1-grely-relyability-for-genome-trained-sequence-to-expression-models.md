---
title: "gRely: Relyability for genome trained sequence-to-expression models"
title_zh: gRely：基因组训练的序列到表达模型的可靠性
authors: "Rafi, A. M., Eraslan, G., Fletez-Brant, K."
date: 2026-05-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.23.727431v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 评估序列-功能模型变异效应预测可靠性的方法，促进功能基因组学与GWAS精细定位的整合
tldr: "序列到功能模型在变体效应预测中可靠性不均，粗放阈值法丢弃大量潜在有用预测。gRely框架通过1121个特征构建元模型，估计Borzoi预测eQTL方向的置信度，在保留组织上平均精度达0.885，在低幅度区域以76%准确率识别可靠预测。这是首个为S2F模型VEP提供逐预测置信度的方法，实现基于可靠性的过滤，促进模型在基因研究和临床中的可信应用。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有S2F模型预测可靠性差异大，亟需量化每个变体效应预测的置信度。
method: 基于1121个特征（变体、基因、模型输出）的元模型，估计Borzoi VEP正确预测eQTL方向的概率。
result: "保留组织平均精度0.885，低幅度区域准确率76%（基线58%），恢复被阈值过滤的可靠预测。"
conclusion: 首个为S2F模型VEP提供置信度分数的框架，泛化到不同架构，实现基于可靠性的筛选。
---

## 摘要
序列到功能（S2F）模型根据DNA序列预测分子表型，并越来越多地应用于变异效应预测（VEP），其目标是量化遗传变异如何改变基因表达。然而，S2F模型的预测并非均匀可靠：不同变异、基因和组织之间的准确性差异很大，当前实践依赖于粗略的幅度阈值来筛选可信预测，这丢弃了S2F模型仍可能提供信号的大部分变异。我们开发了gRely，一个元建模框架，利用来自目标变异、基因和模型输出的1,121个特征，估计给定Borzoi VEP正确预测eQTL方向的概率。在保留的组织上，gRely的平均准确率达到了0.885（随机基线为0.744）。关键的是，在阈值完全失效的低幅度区域，gRely识别出一个高置信子集，准确率为76%，而基线为58%，恢复了幅度过滤会丢弃的可靠预测。通过SHAP解释显示，在这一低幅度区域，基因表达水平和跨重复信号浓度取代VEP幅度成为可靠性的主要判别因素。gRely是首个为S2F模型VEP提供逐预测置信度分数的框架，并且可跨架构泛化，在AlphaGenome预测上产生一致的改进。通过使可靠性可量化，gRely实现了有原则的过滤而非一刀切的阈值化，并标志着向基因组研究和临床应用中S2F模型的可信部署迈出了一步。

## Abstract
Sequence-to-function (S2F) models predict molecular phenotypes from DNA sequence and are increasingly applied to variant effect prediction (VEP), where the goal is to quantify how genetic variants alter gene expression. However, S2F model predictions are not uniformly reliable: accuracy varies substantially across variants, genes, and tissues, and current practice relies on crude magnitude thresholding to enrich for trustworthy predictions, which discards the majority of variants where S2F models could still provide signal. We developed gRely, a meta-modeling framework that estimates the probability that a given Borzoi VEP correctly predicts eQTL direction, using 1,121 features derived from the target variant, gene, and model outputs. On held-out tissues, gRely achieves a mean average precision of 0.885 (random baseline 0.744). Critically, within the low-magnitude regime where thresholding fails entirely, gRely identifies a high-confidence subset with 76% accuracy compared to a 58% baseline, recovering reliable predictions that magnitude filtering would discard. Interpretation via SHAP reveals that in this low-magnitude regime, gene expression level and cross-replicate signal concentration replace VEP magnitude as the primary discriminators of reliability. gRely is the first framework to provide per-prediction confidence scores for S2F model VEPs, and generalizes across architectures, producing consistent improvements on AlphaGenome predictions. By making reliability quantifiable, gRely enables principled filtering rather than blanket thresholding, and marks a step toward trustworthy deployment of S2F models in genomic research and clinical applications.