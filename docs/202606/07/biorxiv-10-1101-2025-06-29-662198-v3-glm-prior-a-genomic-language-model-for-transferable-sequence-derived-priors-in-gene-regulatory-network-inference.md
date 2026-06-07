---
title: "GLM-Prior: a genomic language model for transferable sequence-derived priors in gene regulatory network inference"
title_zh: GLM-Prior：用于基因调控网络推断中可迁移序列先验的基因组语言模型
authors: "Gibbs, C. S., Chen, A., Bonneau, R., Cho, K."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.1101/2025.06.29.662198v3.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 基因组语言模型提供序列衍生的转录因子-靶标先验知识，可用于功能基因组整合
tldr: 基因调控网络推断依赖高质量先验知识，但现有先验在不同物种和细胞类型中常不完整或缺失。本文提出GLM-Prior，一个微调的基因组语言模型，从核苷酸序列预测转录因子-靶基因互作，并集成为先验矩阵。与概率矩阵分解模型PMF-GRN结合形成双阶段流程，在六个人、小鼠和酵母细胞系中测试，性能随训练数据中阳性标签和TF覆盖度提升，在哺乳动物中优于基于可及性的先验。结果表明先验质量限制GRN推断性能，GLM-Prior为缺乏实验数据的场景提供可迁移的序列派生先验。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基因调控网络推断缺乏跨物种和细胞类型的高质量先验知识，需要可迁移的序列派生先验方法。
method: 微调基因组语言模型GLM-Prior预测TF-靶基因互作，构建先验矩阵，并与PMF-GRN整合实现双阶段GRN推断。
result: 在六个细胞系中，GLM-Prior性能随训练数据质量提升，在哺乳动物中优于基于可及性的先验，跨物种迁移有效。
conclusion: GLM-Prior为缺少实验数据的生物系统提供了可迁移的序列派生先验构建流程，先验质量是GRN推断的关键瓶颈。
---

## 摘要
基因调控网络推断依赖于高质量的先验知识，然而，在不同物种和细胞类型中，精心整理的先验知识往往不完整或不可用。我们提出了GLM-Prior，这是一个经过微调的基因组语言模型，用于从核苷酸序列预测转录因子-靶基因相互作用，并将其作为构建TF-基因先验矩阵的序列推导策略进行基准测试。我们将GLM-Prior与概率矩阵分解模型PMF-GRN相结合，创建了一个双阶段流程，该流程将序列推导的先验与单细胞基因表达数据相结合，用于先验条件下的基因调控网络推断。在六种人类、小鼠和酵母细胞系背景下，GLM-Prior的性能随着训练数据中正标签丰度和转录因子覆盖度的增加而提升，并在注释良好的哺乳动物背景下与独立参考网络表现出一致性。我们评估了单物种、物种迁移和多物种训练范式，发现GLM-Prior可以在相关哺乳动物物种中构建信息丰富的先验，而向酵母的迁移仍接近随机水平。与基于可及性的先验在多种基因调控网络推断方法中的比较显示，GLM-Prior在五个哺乳动物细胞系中的四个中实现了最高的先验性能。在这些基准测试下，先验质量在很大程度上限制了可实现的基因调控网络推断性能，而基于表达的推断提供了依赖于先验的优化。综合来看，这些结果将GLM-Prior定位为在无法获得匹配实验数据的系统中，用于可迁移、序列推导的先验构建的基准工作流程。

## Abstract
Gene regulatory network (GRN) inference depends on high-quality prior knowledge, yet curated priors are often incomplete or unavailable across species and cell types. We present GLM-Prior, a genomic language model fine-tuned to predict transcription factor (TF)-target gene interactions from nucleotide sequence, and benchmark it as a sequence-derived strategy for constructing TF-gene prior matrices. We integrate GLM-Prior with PMF-GRN, a probabilistic matrix factorization model, to create a dual-stage pipeline that combines sequence-derived priors with single-cell gene expression data for prior-conditioned GRN inference. Across six human, mouse, and yeast cell-line contexts, GLM-Prior performance scales with positive label abundance and TF coverage in training data, and shows abovechance agreement with independent reference networks in well-annotated mammalian contexts. We evaluate single-species, species-transfer, and multi-species training paradigms, finding that GLM-Prior can construct informative priors across related mammalian species, while transfer to yeast remains near chance. Comparisons with accessibility-based priors across multiple GRN inference methods show that GLM-Prior achieves the highest prior performance in four of five mammalian cell lines. Under these benchmarks, prior quality largely constrains achievable GRN inference performance, with expression-based inference providing prior-dependent refinement. Together, these results position GLM-Prior as a benchmarked workflow for transferable, sequence-derived prior construction in systems where matched experimental assays are unavailable.