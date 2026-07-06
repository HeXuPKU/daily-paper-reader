---
title: Impacts of batch effects on the performance of machine learning classifiers across multiple studies
title_zh: 批次效应对跨研究机器学习分类器性能的影响
authors: "Raab, P., Johnson, W. E., Piccolo, S. R."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.24.734352v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 批次效应影响汇总组学数据的机器学习模型，对GWAS/PRS预测有参考价值
tldr: 精准医学需整合多研究数据以增强统计效力，但批次效应（系统技术伪影）会使机器学习模型学习预测实验批次而非真实生物学信号，导致在新批次数据上性能显著下降。本研究评估了批次效应对分类器的影响，并比较了多种统计调整方法（如ComBat、limma等）。结果表明，未经调整的模型泛化能力差，而适当调整可恢复性能，但需通过外部独立队列验证确保调整有效性。该工作为跨研究数据整合提供了批次效应处理指南。
source: biorxiv
selection_source: fresh_fetch
motivation: 跨研究数据整合是精准医学的基础，但批次效应会误导模型学习批次信号而非生物变量，损害其泛化能力。
method: 比较ComBat、limma等批次效应调整方法，并通过外部独立队列验证调整后模型在新批次上的分类性能。
result: 批次效应显著降低模型跨批次泛化性能，而适当的统计调整可有效恢复准确率，但调整方法选择需谨慎。
conclusion: 批次效应调整对多研究数据整合至关重要，必须使用外部验证以确保模型真正泛化到新数据。
---

## 摘要
精准医疗依赖于对跨人类多样性谱系患者的准确且可泛化的预测。由于捕捉生物异质性需要大样本量，研究人员通常必须聚合来自多个实验批次或独立研究的数据。这种整合比单一研究能提供更大的统计功效和多样性，同时避免了生成大规模新组学数据集的成本。在这些聚合数据上训练的预测模型理论上能更好地检测出可泛化到新数据的细微模式。然而，这种潜力常被“批次效应”——系统的技术伪影——所破坏，这些伪影会偏倚模型训练以预测实验批次，并掩盖有意义的生物条件。在具有批次效应的数据上训练的模型，当应用于新批次的数据时，性能可能显著下降。统计调整方法可以在保留生物信号的同时减轻这些伪影。为确保这些调整确实促进泛化，我们强调使用外部独立队列进行严格验证。本章探讨批次效应如何影响预测，并比较各种调整方法。

## Abstract
Precision medicine relies on accurate and generalizable predictions for patients across the spectrum of human diversity. Because capturing biological heterogeneity requires large sample sizes, researchers must often aggregate data from several experimental batches or independent studies. This integration allows for greater statistical power and diversity than a single study could provide, while avoiding the costs of generating massive new -omics datasets. Predictive models trained on these aggregated data are theoretically better equipped to detect subtle patterns that generalize to new data. However, this potential is frequently undermined by "batch effects"--systematic technical artifacts that can bias model training to predict experimental batches and shadow meaningful biological conditions. Models trained on data with batch effects can exhibit substantially degraded performance when applied to data from new batches. Statistical adjustment methods can mitigate these artifacts while preserving biological signals. To ensure these adjustments actually facilitate generalization, we emphasize the use of external, independent cohorts for rigorous validation. This chapter examines how batch effects impact predictions and compares various adjustment methods.