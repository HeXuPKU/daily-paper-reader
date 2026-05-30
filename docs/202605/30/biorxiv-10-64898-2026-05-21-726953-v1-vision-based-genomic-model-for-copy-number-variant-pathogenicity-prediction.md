---
title: Vision-Based Genomic Model for Copy Number Variant Pathogenicity Prediction
title_zh: 基于视觉的基因组模型用于拷贝数变异致病性预测
authors: "Buralkin, I., Botas, J., Chang, K.-L., Deng, Y., Papastathopoulos-Katsaros, A., Liu, Z., Park, J."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.21.726953v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 用于CNV致病性预测的深度学习基因组模型，可应用于GWAS分析
tldr: 现有拷贝数变体（CNV）致病性预测方法将CNV简化为区域级数值特征，丢失了位置结构和跨轨道模式。本文提出TESSERACT模型，将CNV表示为碱基对分辨率的多轨道图像，保留空间依赖。在ClinVar数据集上，模型AUROC比最优基线提升0.10，在独立DECIPHER队列上保持最高AUROC和F1。模型能定位致病信号至临床相关子区域，提供可解释性证据。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有CNV致病性预测方法丢弃位置结构和跨轨道模式，限制了预测准确性。
method: 将CNV表示为碱基对分辨率的多轨道图像，使用视觉模型学习空间基因组模式。
result: 在ClinVar上AUROC提升0.10，在DECIPHER上保持最高AUROC和F1分数。
conclusion: 模型可定位致病信号至临床子区域，支持可解释的临床解读。
---

## 摘要
拷贝数变异（CNVs）是导致罕见疾病（包括神经发育迟缓和智力障碍）的主要结构性基因组改变类型，然而预测其致病性仍然具有挑战性。现有方法将CNV简化为区域级数值特征，丢弃了专家临床审查员用于解释基因组证据的位置结构和跨轨道模式。为了解决这一问题，我们引入了用于CNV的TO_SCPLOWESSERACTC_SCPLOW，这是一种基于轨道的空间表示方法，用于CNV致病性预测，它将每个变异表示为碱基对分辨率的多轨道图像，并在保留位置结构和跨轨道依赖性的同时，跨注释轨道建模空间基因组模式。在ClinVar数据集上以染色体级别留出分割进行训练，TO_SCPLOWESSERACTC_SCPLOW在留出和精选的非编码基准上优于先前方法，相比最先进的基线，AUROC提高了高达0.10。在独立的DECIPHER队列中，该模型通过在所有基线中保持最高的AUROC和最高的F1分数，展现了泛化能力。此外，我们的模型将致病信号定位到具有临床意义的基因组子区域，提供了支持实际临床解释的轨道注释证据。

## Abstract
Copy number variants (CNVs) are a major class of structural genomic alterations underlying rare disease, including neurodevelopmental delay and intellectual disability, yet predicting their pathogenicity remains challenging. Existing methods reduce CNVs to region-level numerical features, discarding the positional structure and cross-track patterns that expert clinical reviewers use to interpret genomic evidence. To address this, we introduce TO_SCPLOWESSERACTC_SCPLOW for CNV, a track-based spatial representation for CNV pathogenicity prediction, which represents each variant as a base-pair-resolution multi-track image and models spatial genomic patterns across annotation tracks while preserving positional structure and cross-track dependencies. Trained on a chromosome-level hold-out split of the ClinVar dataset, TO_SCPLOWESSERACTC_SCPLOW outperforms prior methods on held-out and curated noncoding benchmarks, improving AUROC by up to 0.10 over the state-of-the-art baseline. On the independent DECIPHER cohort, the model demonstrates generalizability by maintaining the highest AUROC and the highest F1 score across baselines. Furthermore, our model localizes pathogenic signals to clinically meaningful genomic subregions, providing track-annotated evidence that supports practical clinical interpretation.