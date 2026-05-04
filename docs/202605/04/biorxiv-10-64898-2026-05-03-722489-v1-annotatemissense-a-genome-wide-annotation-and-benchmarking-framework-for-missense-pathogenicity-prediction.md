---
title: "AnnotateMissense: a genome-wide annotation and benchmarking framework for missense pathogenicity prediction"
title_zh: AnnotateMissense：一个用于错义突变致病性预测的全基因组注释与基准测试框架
authors: "Muneeb, M., Ascher, D. B."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.03.722489v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 错义变异的全基因组注释和致病性预测
tldr: 错义变异致病性预测因证据异质性而具有挑战性。本研究开发了 AnnotateMissense 框架，整合了进化保守性、蛋白质语言模型特征及群体频率等 303 个特征。通过对 13 万余个 ClinVar 变异进行基准测试，XGBoost 模型表现最优（MCC 0.9411）。该框架已应用于全基因组 9000 万个错义变异，为临床解释提供了高精度的预测工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 错义变异的致病性解释依赖于多种异质性证据，亟需一个整合多维特征的标准化注释与预测框架。
method: 整合了 dbNSFP、AlphaMissense、ESM 衍生特征及群体频率等 303 个特征，并利用 XGBoost 等机器学习模型在 ClinVar 数据集上进行训练与基准测试。
result: 全特征 XGBoost 模型在交叉验证中达到 0.9411 的 MCC 和 0.9950 的 ROC-AUC，并在时间验证集上表现稳健。
conclusion: AnnotateMissense 提供了一个可扩展的基因组范围预测框架，其生成的致病性评分和标签有助于提升临床变异解读的准确性。
---

## 摘要
错义变异解读仍然具有挑战性，因为其致病性取决于来自人群频率、进化保守性、转录本上下文、氨基酸替换严重程度、先验致病性预测因子以及蛋白质语言模型衍生特征的异质证据。我们提出了 AnnotateMissense，这是一个用于错义变异解读的可扩展注释、基准测试和全基因组预测框架。AnnotateMissense 整合了源自 dbNSFP v5.1 的 hg38 错义变异，以及 ANNOVAR 注释、dbNSFP 转录本/蛋白质描述符、AlphaMissense 评分、ESM 衍生特征、保守性指标、人群频率变量、已建立的致病性预测因子以及工程化的氨基酸/密码子上下文特征。利用 132,714 个 ClinVar 标记的错义变异，我们在受控特征配置下对机器学习和深度学习模型进行了基准测试。包含 303 个特征的全量基准测试集在 XGBoost 模型上表现最强，在分层五折交叉验证中达到了平均 MCC = 0.9411 和 ROC-AUC = 0.9950。受限的朴素特征集和面向位置的特征集分别仅达到了 0.4989 和 0.5113 的较低最佳 MCC 值。循环控制消融实验表明，移除先验预测因子、人群频率和临床重叠证据会降低性能，而仅排除 AlphaMissense 和 ESM 衍生特征的影响微乎其微。在针对新观察到的致病/良性变异的时间 ClinVar 验证中，达到了 MCC = 0.7613、准确率 = 0.8798 和 F1 分数 = 0.8750。最终模型被应用于 90,643,830 个 hg38 错义变异，生成了 AnnotateMissense 致病性评分和二元预测标签。代码和输出可在 https://github.com/MuhammadMuneeb007/CAGI7_Annotate_All_Missense 和 https://doi.org/10.5281/zenodo.19981867 获取。

## Abstract
Missense variant interpretation remains challenging because pathogenicity depends on heterogeneous evidence from population frequency, evolutionary conservation, transcript context, amino acid substitution severity, prior pathogenicity predictors and protein-language-model-derived features. We present AnnotateMissense, a scalable annotation, benchmarking and genome-wide prediction framework for missense variant interpretation. AnnotateMissense integrates hg38 missense variants derived from dbNSFP v5.1 with ANNOVAR annotations, dbNSFP transcript/protein descriptors, AlphaMissense scores, ESM-derived features, conservation metrics, population-frequency variables, established pathogenicity predictors and engineered amino acid/codon-context features. Using 132,714 ClinVar-labelled missense variants, we benchmarked machine-learning and deep-learning models under controlled feature configurations. The full 303-feature benchmark set achieved the strongest performance with XGBoost, reaching mean MCC = 0.9411 and ROC-AUC = 0.9950 across stratified five-fold cross-validation. Restricted naive and location-oriented feature sets achieved lower best MCC values of 0.4989 and 0.5113, respectively. Circularity-controlled ablations showed that removing prior-predictor, population-frequency and clinically overlapping evidence reduced performance, whereas excluding AlphaMissense and ESM-derived features alone had minimal effect. Temporal ClinVar validation on newly observed pathogenic/benign variants achieved MCC = 0.7613, accuracy = 0.8798 and F1-score = 0.8750. The final model was applied to 90,643,830 hg38 missense variants to generate AnnotateMissense pathogenicity scores and binary prediction labels. Code and outputs are available at https://github.com/MuhammadMuneeb007/CAGI7_Annotate_All_Missense and https://doi.org/10.5281/zenodo.19981867.