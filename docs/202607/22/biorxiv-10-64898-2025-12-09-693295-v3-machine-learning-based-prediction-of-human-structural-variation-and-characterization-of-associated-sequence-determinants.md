---
title: Machine learning-based prediction of human structural variation and characterization of associated sequence determinants
title_zh: 基于机器学习的人类结构变异预测及相关序列决定因素的表征
authors: "Lim, D., Lou, R. N., Ioannidis, N. M., Sudmant, P. H."
date: 2026-07-15
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.09.693295v3.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 用于预测人类全基因组结构变异的机器学习模型
tldr: "结构变异(SV)是遗传多样性和疾病的重要因素，但其形成受局部序列背景影响的程度尚不明确。本研究开发了基于序列的卷积神经网络(CNN)和随机森林模型，用于预测基因组中SV的发生，集成后AUROC超过90%。模型可解释性显示微同源序列、非规范DNA结构及SV热点是关键决定因素，且不同SV类别具有独特特征。预测的SV概率与等位基因频率和基因功能约束相关，表明该模型可用于识别不稳定区域并量化SV易感性和变异效应。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-09-693295-v3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1527, \"height\": 1500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-09-693295-v3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1407, \"height\": 1484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-09-693295-v3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1224, \"height\": 1330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-09-693295-v3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1244, \"height\": 2045, \"label\": \"Figure\"}]"
motivation: 量化局部序列上下文对结构变异形成的影响，以揭示不稳定基因组区域的特征。
method: 构建序列CNN和随机森林模型，集成后预测SV发生概率，并利用可解释性技术分析关键特征。
result: "模型AUROC>90%，揭示微同源等序列基序及SV热点贡献，不同SV类别呈现独特序列决定因素。"
conclusion: 机器学习可从局部序列特征推断SV易感区域，为个性化基因组学中变异效应预测提供框架。
---

## 摘要
结构变异（SV）是遗传多样性的主要来源，并在人类疾病和进化中发挥关键作用。然而，局部序列背景如何影响结构变异发生的可能性仍缺乏量化。在此，我们开发了机器学习模型来预测人类基因组中结构变异的发生，并表征与其形成相关的基因组决定因素。我们开发了基于序列的卷积神经网络（CNN）模型以及整合多种基因组注释的随机森林方法。两个模型均能独立实现高预测性能（AUROC>90%），并且通过集成可进一步提升。这些模型的预测能力表明，能够从序列背景中准确推断出易发生结构变异的区域。模型可解释性技术揭示了结构变异的关键基因组贡献因素，包括微同源性和非经典DNA结构等序列基序的影响，以及结构变异热点的存在。我们发现不同类别的结构变异表现出不同的序列决定因素，其中转座元件和倒位显示出尤为独特的特征。此外，预测的结构变异概率与等位基因频率和基因功能约束相关，表明该模型在变异效应预测中的潜在应用价值。这些发现证明，基于局部序列特征训练的机器学习模型能够识别不稳定的基因组区域，并为个性化基因组学中结构变异易感性和结构变异效应的量化提供框架。

## Abstract
Structural variants (SVs) represent a major source of genetic diversity and play key roles in human disease and evolution. Yet, the extent to which local sequence context shapes the likelihood of structural variant formation remains poorly quantified. Here, we develop machine learning models to predict the occurrence of SVs across the human genome and characterize genomic determinants associated with their formation. We developed both a sequence only-based convolutional neural network (CNN) model as well as a random forest approach integrating diverse genomic annotations. Both models achieve high predictive performance individually (>90% AUROC) which can be further improved in an ensemble. The predictive ability of these models demonstrates that SV-prone regions can be accurately inferred from sequence context. Model interpretability techniques reveal key genomic contributors to SVs, including effects of sequence motifs such as microhomology and non-canonical DNA structures, as well as the presence of SV hotspots. We find that different classes of SVs exhibit distinct sequence determinants, with transposable elements and inversions displaying particularly unique signatures. Moreover, predicted SV probability correlates with allele frequency and gene functional constraint, indicating the potential utility of the model for variant effect prediction. These findings demonstrate that machine learning models trained on local sequence features can identify unstable genomic regions and provide a framework for quantifying SV susceptibility and SV variant effects in personalized genomics.