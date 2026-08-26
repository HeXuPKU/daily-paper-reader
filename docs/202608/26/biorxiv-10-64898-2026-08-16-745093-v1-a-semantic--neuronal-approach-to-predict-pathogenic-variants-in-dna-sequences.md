---
title: A Semantic + Neuronal Approach to Predict Pathogenic Variants in DNA Sequences
title_zh: 一种语义+神经元方法预测DNA序列中的致病性变异
authors: "Motta, J. A., Motta, M. d. M., Fernandez, C."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.16.745093v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 深度学习和NLP预测致病变异，可用于GWAS变异的功能注释
tldr: 致病性DNA变异识别对基因组医学至关重要。本文从ClinVar数据库提取序列，将DNA翻译为肽段并借助语法规则进行词性标注，结合CRF与BiLSTM构建预测模型。在105个基因约2.7万变异上训练，性能超越五种现有方法，达到该领域最新水平。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有致病性变异预测方法准确率有限，需要更有效的特征表示与序列建模手段。
method: 将DNA序列按遗传密码转为肽段，用词性标注表示语义，结合CRF序列标注与BiLSTM上下文捕获构建混合模型。
result: 在ClinVar数据上，精确率、PR/ROC曲线、AUC及混淆矩阵结果均优于五种对比方法，达到最新水平。
conclusion: 所提语义加神经方法能精准预测致病性DNA变异，具备临床应用潜力。
---

## 摘要
在这项工作中，我们提出了一种用于识别致病性DNA变异的机器学习模型。该模型通过学习从ClinVar数据库（由NCBI支持）中提取的正常和致病性序列分析而得。该分析基于DNA序列的概念语义模型，该模型将DNA序列转换为受良好定义语法约束的肽序列（氨基酸序列），这使我们能够应用NLP技术，特别是词性标注（POS标注）。我们的预测模型通过结合两种技术构建：CRF（来自马尔可夫模型家族），用于执行序列标注，以及BiLSTM（一种深度学习模型），用于捕获序列的过去和未来内容。训练空间由与约27,000个致病性变异相关的105个基因的序列创建。使用精确率、P-R曲线和ROC曲线、AUC以及混淆矩阵等指标对模型进行了评估。其性能还与五种已知的致病性变异预测方法进行了比较。结果显示，该方法的卓越性能超出了预期，使其在预测致病性DNA序列方面达到了最先进水平。

## Abstract
In this work, we present a machine learning model for identifying pathogenic DNA variants. The model was learned from the analysis of normal and pathogenic sequences extracted from the ClinVar database (supported by NCBI). This analysis was based on a conceptual semantic model of DNA sequences converted to peptide sequences (amino acid sequences) governed by a well-defined grammar, which allowed us to apply NLP techniques, specifically Part of Speech tagging (POS tagging). Our predictive model was built by combining two techniques: CRF (from the Markov model family), which performs the sequencing, and BiLSTM (a deep learning model) which captures the past and future content of the sequences. The training space was created with the sequences of 105 genes associated with approximately 27,000 pathogenic variants. The model was evaluated using the metrics precision, P-R and ROC curves, AUC, and confusion matrices. Its performance was also compared against five known methods for predicting pathogenic variants. The results show exceptional performance that exceeds expectations and places this new method at the state of the art for predicting pathogenic DNA sequences.