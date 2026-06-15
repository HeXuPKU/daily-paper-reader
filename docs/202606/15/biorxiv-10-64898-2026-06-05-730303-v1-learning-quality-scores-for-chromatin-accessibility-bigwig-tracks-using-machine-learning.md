---
title: Learning quality scores for chromatin accessibility bigWig tracks using Machine Learning
title_zh: 利用机器学习学习染色质可及性bigWig轨迹的质量评分
authors: "Sanders, E., Riva, S. G., Hughes, J. R."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730303v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 基于机器学习的染色质可及性数据质控框架，为与GWAS整合奠定基础
tldr: 高通量染色质可及性实验产生大量bigWig信号文件，但缺乏直接针对信号轨道的系统性质控框架。本文提出基于机器学习的质控方法，利用LanceOtron峰调用器提取信号结构和信噪比特征，并以恒定启动子和CTCF区域恢复作为生物控制。对502个样本的XGBoost模型预测准确率R²=0.97，SHAP分析显示决策基于生物相关信号属性。该框架提供可解释的连续质量评分，支持更可靠的数据整合和下游应用。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有染色质可及性bigWig文件缺乏直接基于信号轨道的系统性质控框架，限制了数据可靠性评估和稳健的下游分析。
method: 利用LanceOtron机器学习峰调用器提取信号结构与信噪比特征，定义恒定启动子和CTCF区域作为内部生物对照，训练XGBoost模型预测这些区域的恢复程度。
result: 在502个人类样本上，模型预测准确率达R²=0.97，SHAP分析表明特征源于生物相关信号属性，质量评分分位层与可视化定性差异一致。
conclusion: 该工作为染色质可及性bigWig文件提供了可扩展的质控框架，有助于更可靠的数据整合和下游机器学习应用。
---

## 摘要
高通量染色质可及性分析，如批量及单细胞ATAC-seq，已产生了大量以bigWig格式存储的加工信号轨迹，这些轨迹广泛用于可视化、数据整合以及基于机器学习（ML）的分析。尽管它们发挥着核心作用，但直接在bigWig信号轨迹层面进行系统质量控制的框架仍不成熟。这一空白限制了评估数据可靠性的能力，并阻碍了稳健的下游分析。

在此，我们提出一个基于生物学原理的染色质可及性bigWig文件质量控制框架，该框架整合了峰值水平信息、背景噪声估计以及稳定基因组参考特征的恢复。利用基于ML的峰值识别器（LanceOtron），我们推导出捕获信号结构和信噪特性的互补质量度量。我们进一步将恒定启动子和CTCF区域定义为内部生物学对照，并表明它们的恢复在不同细胞背景下提供了数据质量的敏感度量。

我们将此框架应用于涵盖多种组织和细胞类型的502个人类染色质可及性bigWig轨迹集合。所提出的度量捕获了信号质量相关但非冗余的方面，并促使将恒定启动子和CTCF恢复作为具有生物学意义的目标。基于LanceOtron衍生特征训练的XGBoost模型在保留数据上准确预测了这些稳定基因组元件的恢复（R² = 0.97），生成连续且可解释的质量评分。使用SHAP值的特征重要性分析表明，模型决策由生物学相关的信号属性驱动，而非任意启发式规则。基于分位数的质量评分分层进一步得到了基因组浏览器可视化中清晰的定性差异的支持。

总之，这项工作为评估染色质可及性bigWig轨迹的质量提供了一个有原则且可扩展的框架，从而实现更可靠的数据整合，并支持调控基因组学中的下游ML应用。

## Abstract
High-throughput chromatin accessibility assays such as bulk and single-cell ATAC-seq have generated large collections of processed signal tracks in bigWig format, which are widely used for visualisation, data integration, and Machine Learning (ML)-based analyses. Despite their central role, systematic quality control (QC) frameworks operating directly at the level of bigWig signal tracks remain underdeveloped. This gap limits the ability to assess data reliability and hampers robust downstream analyses.

Here, we present a biologically grounded QC framework for chromatin accessibility bigWig files that integrates peak-level information, background noise estimation, and recovery of stable genomic reference features. Using an ML-based peak caller (LanceOtron), we derive complementary quality metrics capturing signal structure and signal-to-noise properties. We further define constant promoter and CTCF regions as internal biological controls and show that their recovery provides a sensitive measure of data quality across diverse cellular contexts.

We apply this framework to a collection of 502 human chromatin accessibility bigWig tracks spanning a wide range of tissues and cell types. The proposed metrics capture related but non-redundant aspects of signal quality and motivate the use of constant promoter and CTCF recovery as biologically meaningful targets. An XGBoost model trained on LanceOtron-derived features accurately predicts recovery of these stable genomic elements on held-out data (R2 = 0.97), yielding a continuous and interpretable quality score. Feature importance analysis using SHAP values highlights that model decisions are driven by biologically relevant signal properties rather than arbitrary heuristics. Quantile-based stratification of the quality score is further supported by clear qualitative differences in genome browser visualisations.

Together, this work provides a principled and extensible frame-work for assessing the quality of chromatin accessibility bigWig tracks, enabling more reliable data integration and supporting downstream ML applications in regulatory genomics.