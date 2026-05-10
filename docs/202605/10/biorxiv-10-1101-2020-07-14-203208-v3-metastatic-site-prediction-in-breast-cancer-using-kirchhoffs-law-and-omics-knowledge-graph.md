---
title: "Metastatic Site Prediction in Breast Cancer using Kirchhoff's Law and Omics Knowledge Graph"
title_zh: 基于基尔霍夫定律和组学知识图谱的乳腺癌转移部位预测
authors: "Jha, A., Khan, Y., Sahay, R., d'Aquin, M."
date: 2026-05-07
pdf: "https://www.biorxiv.org/content/10.1101/2020.07.14.203208v3.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 用于癌症预测的多组学知识图谱
tldr: 本研究针对乳腺癌转移预测中多组学数据异质性及机制结构缺失的问题，提出了一种基于基尔霍夫定律的知识图谱框架（K-KG）。该框架整合了36个多组学数据集，引入电路理论中的电压和电流定律来规范图谱中的信息流，并通过拓扑基元挖掘和图卷积神经网络实现位点特异性转移的连续百分比预测。实验表明，该方法在多个独立队列中显著优于传统机器学习模型，为理解癌症转移机制提供了新视角。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的乳腺癌转移预测方法往往忽略了驱动转移趋向性的复杂多组学机制结构和异质性。
method: 提出K-KG框架，将基尔霍夫定律应用于多层癌症决策网络，结合拓扑基元挖掘与图卷积神经网络进行预测。
result: 在多个测试队列中，该模型在脑转移预测上达到0.87的AUC，性能优于传统基准模型8-20个百分点。
conclusion: 该研究首次将经典物理定律应用于图机器学习，实现了高精度的乳腺癌位点特异性转移预测及贡献度分析。
---

## 摘要
从原发肿瘤预测转移的解剖部位仍然是乳腺癌（BRCA）及更广泛的转移性疾病中一个尚未解决的问题。其难点在于结构性：转移生物学具有多部位（骨、肺、肝、脑）、多组学（基因组学、蛋白质组学、甲基化组学、药物反应）和多模态（CNV、基因表达、DNA 甲基化、通路、临床关联）的特点。现有的分类器要么将这种异质性压缩为单一特征向量，要么依赖单一组学层，这两者都丢弃了驱动转移趋向性的机制结构。我们引入了基尔霍夫知识图谱（K-KG），这是一个将电路理论的守恒定律引入知识图谱推理的框架。我们的贡献包括：（1）一个分层的 RDF 癌症决策网络，整合了涵盖突变、通路、药物、疾病和反应的 36 个多组学数据集；（2）两条新颖的守恒定律——知识图谱电压定律（KGVL）和知识图谱电流定律（KGCL），用于管理遍历过程中的信息流，并提供图完整性的原则性度量；（3）在守恒图上进行拓扑基元挖掘，通过识别其重连标志着转移转变的三角形子结构，取代了基于表达的特征选择；（4）一种图卷积神经网络，其隐藏层即为组学层本身，将特定部位的转移预测为连续百分比而非二元标签。在 TCGA-BRCA 训练集以及来自 GEO 的一个验证集和四个独立测试集上，K-KG 在复发预测方面达到了 83.8% 的 AUC，在脑部特定部位预测方面达到了高达 0.87 的 AUC 和 0.91 的 F1 分数，优于随机森林、神经网络和 SVM 基准模型 8-20 个 AUC 点。据我们所知，这是基尔霍夫定律（1845, 1847）首次应用于基于图的机器学习，也是第一个返回每个部位贡献概况而非单一标签的转移预测器。

## Abstract
Predicting the anatomical site of metastasis from a primary tumour remains an unsolved problem in breast cancer (BRCA) and metastatic disease more broadly. The difficulty is structural: metastatic biology is multi-site (bone, lung, liver, brain), multi-omics (genomics, proteomics, methylomics, drug response), and multi-modal (CNV, gene expression, DNA methylation, pathways, clinical associations). Existing classifiers either collapse this heterogeneity into a single feature vector or rely on a single omics layer, both of which discard the mechanistic structure that drives metastatic tropism. We introduce Kirchhoff Knowledge Graphs (K-KG), a framework that imports the conservation laws of electrical-circuit theory into knowledge graph reasoning. Our contributions are: (1) a layered RDF Cancer Decision Network integrating 36 polyomics datasets across mutations, pathways, drugs, diseases, and reactions; (2) two novel conservation laws - the Knowledge-Graph Voltage Law (KGVL) and Knowledge-Graph Current Law (KGCL) - that govern information flow during traversal and yield a principled measure of graph completeness; (3) topological motif mining on the conserved graph, replacing expression-based feature selection by identifying triangular sub-structures whose rewiring marks metastatic transition; (4) a Graph Convolutional Neural Network whose hidden layers are the omics layers themselves, predicting site-specific metastasis as a continuous percentage rather than a binary label. On TCGA-BRCA training plus one validation and four independent test cohorts from GEO, K-KG achieves 83.8% AUC for relapse prediction and up to 0.87 AUC / 0.91 F1 for brain-site-specific prediction, outperforming Random Forest, Neural Network, and SVM baselines by 8-20 AUC points. To our knowledge this is the first application of Kirchhoff's laws (1845, 1847) to graph-based machine learning, and the first metastasis predictor that returns a per-site contribution profile rather than a single label.