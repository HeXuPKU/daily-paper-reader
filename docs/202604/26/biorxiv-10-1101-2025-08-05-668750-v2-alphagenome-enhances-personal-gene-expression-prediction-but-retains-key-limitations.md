---
title: AlphaGenome Enhances Personal Gene Expression Prediction but Retains Key Limitations
title_zh: AlphaGenome 增强了个体基因表达预测，但仍保留了关键局限性
authors: "Shen, L."
date: 2026-04-18
pdf: "https://www.biorxiv.org/content/10.1101/2025.08.05.668750v2.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 从DNA序列预测个体特异性基因表达的基因组AI模型
tldr: 本研究评估了最先进的基因组AI模型AlphaGenome在预测个体特异性基因表达方面的表现。通过GTEx数据测试，AlphaGenome在预测准确性和方向性上显著优于前代模型Enformer，优势比达3.0，并能有效处理非线性序列-表达关系。尽管取得了重大进展，但研究也指出该模型仍存在局限性，且其预测机制与传统的树类模型有所不同，为理解DNA序列与基因表达的关系提供了新视角。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-08-05-668750-v2/fig-001.webp\", \"caption\": \"Fig. 1 Accuracy of personal gene expression prediction for four comparing methods. a Violin plots of Pearson correlations of the four methods across all gene-tissue pairs. b-d Scatter plots of AlphaGenome vs. Elastic Net, Random Forest and Enformer. Red triangles represent gene-tissue pairs that AlphaGenome is significantly better, while green squares represent gene-tissue pairs that other methods are significantly better. The statistical significance is determined from 1000 bootstrap samples. e Dumbbell plots of the top 15 genes from AlphaGenome and Enformer based on the difference of Pearson correlation.\", \"page\": 4, \"index\": 1, \"width\": 777, \"height\": 398}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-08-05-668750-v2/fig-002.webp\", \"caption\": \"Fig. 2 AlphaGenome vs. Random Forest and Elastic Net in nonlinearity-filtered gene-tissue pairs. a Scatter plot of Random Forest vs. Elastic Net to identify nonlinear gene-tissue pairs. b Scatter plots of AlphaGenome vs. Elastic Net and Random Forest for top 300 nonlinear genes. c Scatter plots of the comparing model’s predictions vs. observation. d Marginal effects of genetic mutations for Random Forest and AlphaGenome in a 20 Kb region around the transcriptional start site of ABI3.\", \"page\": 5, \"index\": 2, \"width\": 775, \"height\": 484}]"
motivation: 旨在评估当前最先进的基因组AI模型AlphaGenome是否能解决以往模型在预测个体特异性基因表达时准确性不足的问题。
method: 利用GTEx数据集，对比评估了AlphaGenome与前代模型Enformer在预测个人基因表达水平方面的性能差异。
result: AlphaGenome在预测表达方向上显著优于Enformer（优势比达3.0），并能将部分负相关预测转为正相关，且在处理非线性关系上表现更佳。
conclusion: AlphaGenome显著提升了个体基因表达预测的性能，但仍存在局限性，且其揭示的生物学机制与传统机器学习模型有所不同。
---

## 摘要
近年来，已经开发了许多基因组人工智能模型来阐明 DNA 序列与基因表达之间的关系。然而，这些模型因在预测个体特异性基因表达方面的准确性有限而受到批评。AlphaGenome 是目前基因组人工智能领域的先进模型，在各种基于序列的预测任务中表现卓越，但其在个体表达预测方面的效用尚未得到评估。在本研究中，我们评估了 AlphaGenome 预测个体基因表达的能力，并发现其表现显著优于其前身。利用 GTEx 数据，AlphaGenome 在预测表达方向上比 Enformer 有所改进，优势比（odds ratio）达到了 3.0。在某些情况下，它甚至将先前观察到的负相关转变为正相关。此外，AlphaGenome 在具有已知非线性序列-表达关系的基因上表现出更好的性能，尽管它揭示的机制与基于树的模型所识别的机制不同。

## Abstract
In recent years, numerous genome AI models have been developed to elucidate the relationship between DNA sequence and gene expression. However, these models have faced criticism for their limited accuracy in predicting individual-specific gene expression. AlphaGenome, the current state-of-the-art in genome AI, achieves exceptional performance across a range of sequence-based predictive tasks, but its utility for personal expression prediction has not yet been assessed. In this study, we evaluate AlphaGenomes ability to predict personal gene expression and find that it significantly outperforms its predecessor. Using GTEx data, AlphaGenome improves the prediction of expression direction over Enformer, achieving an odds ratio of 3.0. In some cases, it even reverses previously observed negative correlations into positive ones. Moreover, AlphaGenome demonstrates improved performance for genes with known nonlinear sequence-expression relationships, though it uncovers mechanisms distinct from those identified by tree-based models.