---
title: Data Representation Bias and Conditional Distribution Shift Drive Predictive Performance Disparities in Multi-Population Machine Learning
title_zh: 数据表示偏差与条件分布偏移驱动多群体机器学习中的预测性能差异
authors: "Kumar, S., Cui, Y."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.1101/2025.06.18.658431v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 针对跨群体多基因预测的性能差异问题
tldr: 机器学习在处理多群体分层数据时，常因数据表示偏差和分布偏移导致性能不均。本研究以多祖先群体的多基因预测为例，通过合成基因型-表型数据集，系统比较了混合学习、独立学习和迁移学习三种策略。结果发现，条件分布偏移与数据表示偏差的共同作用显著影响模型性能及迁移学习的缓解效果，而边际分布偏移影响有限。这些发现为开发公平有效的多群体机器学习模型提供了关键指导。
source: biorxiv
selection_source: fresh_fetch
motivation: 多群体机器学习中，数据表示偏差和分布偏移导致跨群体性能不均，需系统理解其影响机制以开发公平模型。
method: 基于五个大陆群体的合成基因型-表型数据，评估混合学习、独立学习和迁移学习三种多群体学习策略。
result: 条件分布偏移与数据表示偏差显著影响群体性能和迁移学习有效性，边际分布偏移影响有限，且不同策略下联合效应模式不同。
conclusion: 多群体机器学习需关注条件分布偏移与表示偏差的联合作用，迁移学习可作为缓解差异的有效手段。
---

## 摘要
机器学习在应用于群体分层数据集时经常遇到挑战，其中数据表示偏差和数据分布偏移显著影响模型在不同群体间的性能与泛化能力。这些挑战在多祖先群体的多基因预测中体现得尤为明显，其潜在机制广泛适用于跨领域群体分层数据的机器学习。利用代表五个大陆人群的合成基因型-表型数据集，我们评估了三种利用群体分层数据的方法：混合学习、独立学习和迁移学习，以系统研究数据表示偏差和分布偏移如何影响多群体机器学习。结果表明，条件分布偏移与数据表示偏差相结合，显著影响机器学习在不同群体中的性能以及迁移学习作为差异缓解策略的有效性，而边际分布偏移的影响有限。数据表示偏差和分布偏移的联合效应在不同的多群体机器学习方法下表现出不同的模式，为开发针对群体分层数据有效且公平的机器学习模型提供了关键见解。

## Abstract
Machine learning frequently encounters challenges when applied to population-stratified datasets, where data representation bias and data distribution shifts substantially impact model performance and generalizability across different population groups. These challenges are well illustrated in the context of polygenic prediction for diverse ancestry groups, and the underlying mechanisms are broadly applicable to machine learning with population-stratified data across domains. Using synthetic genotype-phenotype datasets representing five continental populations, we evaluate three approaches for utilizing population-stratified data, mixture learning, independent learning, and transfer learning, to systematically investigate how data representation bias and distribution shifts influence multi-population machine learning. Our results show that conditional distribution shifts, in combination with data representation bias, significantly influence machine learning performance across diverse populations and the effectiveness of transfer learning as a disparity mitigation strategy, while the effect of marginal distribution shifts is limited. The joint effects of data representation bias and distribution shifts demonstrate distinct patterns under different multi-population machine learning approaches, providing critical insights for the development of effective and equitable machine learning models for population-stratified data.