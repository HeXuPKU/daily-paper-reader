---
title: "GLOF: A large-scale expert-curated benchmark dataset of gain-of-function and loss-of-function missense variants"
title_zh: GLOF：大规模专家筛选的错义变异功能获得与功能丧失基准数据集
authors: "Maricato, V., Schlesinger, D., de Souza Moura, P. N."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.729843v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 大规模功能错义变异基准数据集，有助于GWAS变异的功能解释
tldr: "区分错义变异的功能获得（GOF）与功能丧失（LOF）对理解疾病机制至关重要，但缺乏大规模专家精选基准。本文构建GLOF数据集，包含112,399个错义变异，由临床遗传学家按ACMG指南分类为LOF、GOF或中性。数据源包括ClinVar和gnomAD，覆盖2,809个基因，其中97个基因含双向机制变异。该资源为预测变异功能机制的方法开发和评估提供了标准化基准。"
source: biorxiv
selection_source: fresh_fetch
motivation: 缺乏区分错义变异LOF和GOF功能机制的大规模专家精选基准数据集。
method: 从ClinVar和gnomAD收集变异，由临床遗传学家依据ACMG指南及功能研究注释分类为LOF、GOF或中性。
result: "构建了含112,399个错义变异、覆盖2,809个基因的GLOF数据集，包含97个双向机制基因。"
conclusion: GLOF作为标准化资源，可用于开发和评估预测错义变异功能机制的计算方法。
---

## 摘要
区分错义变异的功能丧失（LOF）与功能获得（GOF）效应对于理解疾病机制和指导治疗策略至关重要，然而目前尚无公开的大规模专家筛选基准数据集用于此任务。本文提出GLOF（功能获得与功能丧失）数据集，包含2,809个人类基因上的112,399个错义变异，经委员会认证的临床遗传学家根据ACMG指南将其分类为LOF、GOF或中性。致病性变异来源于ClinVar，并根据已发表的功能研究、表型相关性及已建立的基因-疾病关系注释其功能机制。中性变异来自gnomAD v3.1，并使用严格的群体频率过滤器在v4.1中验证。该数据集涵盖多种蛋白质家族，包括97个具有双向机制（同时包含LOF和GOF变异）的基因，并已针对文献中特征明确的变异进行验证。GLOF已在Kaggle（https://www.kaggle.com/datasets/maricatovictor/loss-and-gain-of-function-variants）和Hugging Face（https://huggingface.co/datasets/victormaricato/glof）上公开，为开发和评估预测变异功能机制的计算方法提供了标准化资源。

## Abstract
Distinguishing loss-of-function (LOF) from gain-of-function (GOF) effects of missense variants is fundamental to understanding disease mechanisms and guiding therapeutic strategy, yet no large-scale, expert-curated benchmark has been publicly available for this task. Here we present GLOF (Gain and Loss Of Function), a dataset of 112,399 missense variants across 2,809 human genes, each classified as LOF, GOF, or neutral by board-certified clinical geneticists following ACMG guidelines. Pathogenic variants were sourced from ClinVar and annotated with their functional mechanism based on published functional studies, phenotype correlations, and established gene-disease relationships. Neutral variants were drawn from gnomAD v3.1 and validated against v4.1 using stringent population frequency filters. The dataset spans diverse protein families, includes 97 genes with bidirectional mechanisms (containing both LOF and GOF variants), and has been validated against well-characterized variants in the literature. GLOF is publicly available on Kaggle (https://www.kaggle.com/datasets/maricatovictor/loss-and-gain-of-function-variants) and Hugging Face (https://huggingface.co/datasets/victormaricato/glof), and provides a standardized resource for developing and benchmarking computational methods that predict variant functional mechanisms.