---
title: "scVIP: personalized modeling of single-cell transcriptomes for developmental and disease phenotypes"
title_zh: scVIP：用于发育和疾病表型的单细胞转录组个性化建模
authors: "Lai, H.-Y., Yoo, Y., Tjaernberg, A., Li, R., He, Z., Travaglini, K. J., Qiao, Q., Agrawal, A., Kana, O., van Velthoven, C., Carroll, J. B., Gillespie, M., Mukherjee, S., Fardo, D. W., Li, X.-j., Lein, E., Gabitto, M. I."
date: 2026-06-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.20.717759v2.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 单细胞转录组生成模型，实现个性化表型预测，与虚拟细胞模型生成相关
tldr: 单细胞转录组能够解析细胞异质性，但缺乏连接分子状态与个体表型的统一框架。为此，提出scVIP生成模型，通过细胞类型感知的多实例学习架构联合建模基因表达、细胞组成和表型，学习供体嵌入并定位表型相关信号。在发育年龄预测（r=0.95）、亨廷顿病进展（CCC=0.90）、阿尔茨海默病整合及类风湿关节炎区分等四个场景中均取得准确预测，并识别出疾病相关细胞程序。scVIP为理解细胞状态如何共同塑造个体表型提供了可解释的分析框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 单细胞转录组数据缺乏连接细胞异质性与个体表型的概率框架。
method: 提出scVIP，采用细胞类型感知的多实例学习，联合建模基因表达、细胞组成和表型。
result: 在发育、神经退行性疾病和自身免疫病四个数据集中准确预测表型，如皮层年龄r=0.95，鉴定疾病相关细胞程序。
conclusion: scVIP实现了从单细胞状态到个体表型的可解释分析，适用于发育和疾病研究。
---

## 摘要
单细胞转录组学解析了个体内细胞的异质性，但将分子状态与个体水平表型联系起来需要能够明确桥接这些尺度的框架。我们提出了scVIP，这是一个生成模型，它将基因表达、细胞类型组成和表型测量整合到一个单一的概率模型中，从而实现准确的表型预测和可解释的轨迹推断。一种细胞类型感知的多实例学习架构可以学习捕获进展的供体嵌入，同时将表型相关信号定位到特定的细胞群体。在四个应用场景中，scVIP准确预测了皮层发育年龄（Pearson r = 0.95），刻画了亨廷顿病进展（一致性相关系数 = 0.90），整合了两个阿尔茨海默病队列，恢复了与疾病相关的小胶质细胞和星形胶质细胞程序，并区分了健康个体与ACPA阳性个体以及非进展者与早期RA个体，鉴定出与疾病相关的炎症性T细胞程序。scVIP实现了对细胞状态如何共同塑造发育和疾病过程中个体水平表型的原理性分析。

## Abstract
Single-cell transcriptomics resolves cellular heterogeneity within individuals, but connecting molecular states to individual-level phenotypes requires frameworks that explicitly bridge these scales. We present scVIP, a generative model that links gene expression, cell-type composition, and phenotypic measurements within a single probabilistic model, which enables accurate phenotype prediction and interpretable trajectory inference. A cell-type-aware multi-instance learning architecture learns donor embeddings that capture progression while localizing phenotype-associated signals to specific cell populations. Applied across four settings, scVIP accurately predicts cortical developmental age (Pearson r = 0.95), characterizes Huntingtons disease progression (concordance correlation coefficient = 0.90), integrates two Alzheimers disease cohorts recovering disease-relevant microglial and astrocytic programs, and distinguishes healthy from ACPA-positive individuals and non-progressors from early RA individuals, identifying inflammatory T cell programs associated with disease. scVIP enables principled analysis of how cellular states collectively shape organism-level phenotypes across development and disease.