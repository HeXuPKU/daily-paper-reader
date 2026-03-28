---
title: Identifying genes associated with phenotypes using machine and deep learning
title_zh: 利用机器学习和深度学习识别与表型相关的基因
authors: "Muneeb, M., Ascher, D."
date: 2026-03-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.05.709665v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 使用基因型数据识别表型相关基因的机器学习和深度学习流水线
tldr: 本研究旨在利用机器学习和深度学习技术识别与特定表型相关的基因。研究团队开发了一套包含病例分类和特征重要性评估的流水线，并在openSNP数据集的30种表型上测试了21种机器学习和80种深度学习算法。结果显示，该方法在识别与GWAS目录一致的SNP方面表现优异，平均基因识别率达0.84。这一成果证明了利用分类模型性能来优先排序候选基因的可行性，为精准医疗和疾病机制研究提供了有力工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-05-709665-v1/fig-001.webp\", \"caption\": \"\", \"page\": 3, \"index\": 1, \"width\": 5958, \"height\": 8250}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-05-709665-v1/fig-002.webp\", \"caption\": \"\", \"page\": 4, \"index\": 2, \"width\": 4111, \"height\": 1458}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-05-709665-v1/fig-003.webp\", \"caption\": \"\", \"page\": 5, \"index\": 3, \"width\": 8092, \"height\": 9999}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-05-709665-v1/fig-004.webp\", \"caption\": \"\", \"page\": 6, \"index\": 4, \"width\": 10000, \"height\": 10000}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-05-709665-v1/fig-005.webp\", \"caption\": \"\", \"page\": 10, \"index\": 5, \"width\": 5214, \"height\": 4538}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-05-709665-v1/fig-006.webp\", \"caption\": \"\", \"page\": 11, \"index\": 6, \"width\": 5162, \"height\": 4582}]"
motivation: 识别疾病相关基因对精准医疗至关重要，但传统GWAS等方法在处理复杂基因组数据时仍需更高效的补充手段。
method: 提出一种集成21种机器学习和80种深度学习算法的流水线，通过分类任务和特征重要性分析来识别关键SNP。
result: 在对30种表型的分析中，该方法与GWAS目录对比的平均基因识别率（GIR）达到了0.84。
conclusion: 通过最大化分类性能筛选出的SNP能有效辅助识别表型相关基因，为下游疾病机制研究和治疗靶点发现提供支持。
---

## 摘要
识别疾病相关基因有助于精准医学的发展和对生物过程的理解。全基因组关联研究 (GWAS)、基因表达数据、生物通路分析和蛋白质网络分析是用于识别致病基因的常用技术。我们提出了一种机器学习 (ML) 和深度学习 (DL) 流水线，用于识别与表型相关的基因。该流水线由两个相互关联的过程组成：第一个是根据基因型数据将人群分类为病例组/对照组；第二个是计算特征重要性，以识别与特定表型相关的基因。我们分析了来自 openSNP 数据的 30 种表型，涉及 21 种 ML 算法以及 80 种 DL 算法及其变体。通过曲线下面积 (AUC)、F1 分数和马修斯相关系数 (MCC) 评估性能最佳的 ML 和 DL 模型，并将其用于识别重要的单核苷酸多态性 (SNPs)，随后将识别出的 SNPs 与来自 GWAS Catalog 的表型相关 SNPs 进行比较。每个表型的平均基因识别率 (GIR) 为 0.84。这些结果表明，通过最大化分类性能的 ML/DL 算法筛选出的 SNPs 有助于优先排序表型相关的 SNPs 和基因，从而可能为旨在理解疾病机制和识别候选治疗靶点的下游研究提供支持。

## Abstract
Identifying disease-associated genes enables the development of precision medicine and the understanding of biological processes. Genome-wide association studies (GWAS), gene expression data, biological pathway analysis, and protein network analysis are among the techniques used to identify causal genes. We propose a machine-learning (ML) and deep-learning (DL) pipeline to identify genes associated with a phenotype. The proposed pipeline consists of two interrelated processes. The first is classifying people into case/control based on the genotype data. The second is calculating feature importance to identify genes associated with a particular phenotype. We considered 30 phenotypes from the openSNP data for analysis, 21 ML algorithms, and 80 DL algorithms and variants. The best-performing ML and DL models, evaluated by the area under the curve (AUC), F1 score, and Matthews correlation coefficient (MCC), were used to identify important single-nucleotide polymorphisms (SNPs), and the identified SNPs were compared with the phenotype-associated SNPs from the GWAS Catalog. The mean per-phenotype gene identification ratio (GIR) was 0.84. These results suggest that SNPs selected by ML/DL algorithms that maximize classification performance can help prioritise phenotype-associated SNPs and genes, potentially supporting downstream studies aimed at understanding disease mechanisms and identifying candidate therapeutic targets.