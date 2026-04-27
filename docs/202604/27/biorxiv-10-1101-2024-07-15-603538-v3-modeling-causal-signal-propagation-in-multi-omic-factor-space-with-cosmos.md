---
title: Modeling causal signal propagation in multi-omic factor space with COSMOS
title_zh: 利用 COSMOS 在多组学因子空间中建模因果信号传导
authors: "Dugourd, A., Lafrenz, P., Mananes, D., Paton, V., Fallegger, R., Bai, Y., Kroger, A.-C., Turei, D., Li, Y., Trogdon, M., Nager, D., Deng, S., Shen, C., Lapek, J. D., Shtylla, B., Saez-Rodriguez, J."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.1101/2024.07.15.603538v3.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 整合机械知识的多组学空间因果导向搜索
tldr: 本研究针对多组学分析中数据驱动方法缺乏机制解释的问题，提出了COSMOS+框架。该方法将因子分析与生物学先验知识相结合，通过估算转录因子、激酶活性及配体-受体相互作用，构建连接失调分子特征的因果网络。在乳腺癌耐药模型和患者队列中的应用证明，该框架能有效识别耐药驱动因素并提供可解释的生物学见解。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的多组学分析方法虽能识别分子特征与表型的关联，但难以整合机制性先验知识以提供具有指导意义的因果见解。
method: 开发了COSMOS+框架，利用因子分析输出估算分子活性，并结合网络水平的先验知识生成连接失调特征的因果假设路径。
result: 在乳腺癌耐药细胞系和患者队列数据上，该方法成功识别了耐药驱动因素并生成了具有解释性的机制假设。
conclusion: COSMOS+为高维多组学数据提供了一个可解释的分析框架，能够从复杂数据中提取具有生物学意义的因果机制。
---

## 摘要
理解复杂疾病需要能够联合分析跨多个生物层级（包括信号传导、基因调节和代谢）的组学数据的方法。现有的数据驱动型多组学分析方法，如多组学因子分析（MOFA），可以识别分子特征与表型之间的关联，但它们并非旨在整合现有的机制性分子知识，而这些知识可以提供进一步的可操作见解。我们介绍了一种利用 COSMOS+（多组学空间因果导向搜索）将多组学数据的数据驱动分析与机制先验知识的系统整合相结合的方法。我们展示了如何利用因子分析的输出来估计转录因子和激酶的活性以及配体-受体相互作用，进而将这些结果与网络层级的先验知识整合，以生成关于连接失调分子特征路径的机制假设。我们将该方法应用于乳腺癌耐药细胞系模型的新型多组学数据集，以评估此类机制假设在识别耐药驱动因素方面的能力，并应用于乳腺癌患者队列。我们的方法提供了一个可解释的框架，从多组学数据中生成可操作的见解，特别适用于高维数据集。

## Abstract
Understanding complex diseases requires approaches that jointly analyze omics data across multiple biological layers, including signaling, gene regulation, and metabolism. Existing data-driven multi-omics analysis methods, such as multi-omics factor analysis (MOFA), can identify associations between molecular features and phenotypes, but they are not designed to integrate existing mechanistic molecular knowledge, which can provide further actionable insights. We introduce an approach that connects data-driven analysis of multi-omics data with systematic integration of mechanistic prior knowledge using COSMOS+ (Causal Oriented Search of Multi-Omics Space). We show how factor analysis output can be used to estimate activities of transcription factors and kinases as well as ligand-receptor interactions, which in turn are integrated with network-level prior-knowledge to generate mechanistic hypotheses about paths connecting deregulated molecular features. We apply this approach on a novel multi-omics dataset of cell line models of breast cancer resistance to evaluate the ability of such mechanistic hypotheses to identify resistance drivers, as well as a breast cancer patient cohort. Our approach offers an interpretable framework to generate actionable insights from multi-omic data particularly suited for high dimensional datasets.