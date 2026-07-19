---
title: "A conundrum of pleiotropy: GWAS-derived pleiotropy is weakly negatively associated with co-expression network centrality in Arabidopsis thaliana"
title_zh: 多效性的一个难题：拟南芥中GWAS衍生的多效性与共表达网络中心性呈弱负相关
authors: "Gill, C., Yeaman, S."
date: 2026-07-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.15.738774v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 直接使用GWAS量化多效性并与网络中心性关联
tldr: 基因多效性难以在基因组尺度量化。本研究利用拟南芥GWAS数据，采用Hill数度量基因多效性，并与共表达网络中心性比较。结果发现两者呈弱负相关，多效性高的基因在网络中处于外围位置。该发现表明GWAS多效性和共表达网络中心性反映不同的基因功能方面，为理解多效性提供了新视角。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738774-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1665, \"height\": 1664, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-15-738774-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1369, \"height\": 1763, \"label\": \"Table\"}]"
motivation: 量化基因多效性并探究其与共表达网络中心性的关系，澄清两者是否反映同一基因重要性。
method: 从拟南芥GWAS目录计算Hill数q=1作为多效性指标，并与共表达网络的度、强度等中心性指标进行关联分析。
result: GWAS多效性呈右偏分布，与网络中心性弱负相关，GWAS关联基因在网络中富集且组织表达广泛。
conclusion: GWAS多效性与共表达网络中心性代表不同的基因功能维度，提示多效性高的基因在功能网络中处于边缘位置。
---

## 摘要
多效性，即单个基因影响多个表型性状，是遗传系统的基本特征，但在全基因组尺度上仍然难以量化。全基因组关联研究（GWAS）通过多性状遗传关联提供了一种表征多效性的途径，而基因共表达网络等功能基因组学方法则基于网络中心性统计提供对基因重要性和多效性潜力的间接预测。然而，GWAS衍生的多效性与基于网络的基因重要性度量之间的关系仍不清楚。这里，我们使用AraGWAS目录和AraPheno数据库中的基因-性状关联量化了拟南芥中基因水平的多效性，并将其与先前基于基因共表达网络的多效性估计进行比较。GWAS多效性使用q=1阶希尔数测量，这是一种从生态多样性理论改编的基于熵的度量。在2,179个基因中，多效性呈右偏分布，大多数基因影响相对较少的性状，而一小部分基因表现出广泛的多性状效应。与预期相反，多效性与共表达网络中心性的多个度量（包括度、强度、紧密度和介数）呈弱负相关。进一步分析表明，GWAS关联基因在共表达网络中富集，在组织间表达更广泛，并在保守的BUSCO基因中适度富集。总之，这些发现揭示了一个难题：尽管GWAS鉴定的基因广泛表达并整合到功能网络中，但最具多效性的基因在这些网络中占据相对外围的位置。这种出乎意料的模式表明，GWAS衍生的多效性捕捉了与共表达网络中心性不同的基因功能方面。

## Abstract
Pleiotropy, the influence of a single gene on multiple phenotypic traits, is a fundamental feature of genetic systems but remains difficult to quantify at genome-wide scales. Genome-wide association studies (GWAS) provide one avenue to characterize pleiotropy through multi-trait genetic associations, while functional genomic approaches such as gene co-expression networks offer indirect predictions of gene importance and pleiotropic potential based on network centrality statistics. However, the relationship between GWAS-derived pleiotropy and network-based measures of gene importance remains unclear. Here, we quantified gene-level pleiotropy in Arabidopsis thaliana using gene-trait associations from the AraGWAS Catalog and AraPheno databases and compared them to previous estimates of pleiotropy based on gene co-expression networks. GWAS pleiotropy was measured using the Hill number of order q=1, an entropy-based metric adapted from ecological diversity theory. Across 2,179 genes, pleiotropy exhibited a right-skewed distribution, with most genes influencing relatively few traits and a smaller subset exhibiting broad multi-trait effects. Contrary to expectations, pleiotropy was weakly negatively correlated with multiple measures of co-expression network centrality, including degree, strength, closeness, and betweenness. Additional analyses showed that GWAS-associated genes were enriched within the co-expression network, exhibited broader expression across tissues, and were modestly enriched among conserved BUSCO genes. Together, these findings reveal a conundrum: although genes identified by GWAS are broadly expressed and integrated into functional networks, the most pleiotropic genes occupy relatively peripheral positions within those networks. This unexpected pattern suggests that GWAS-derived pleiotropy captures a distinct aspect of gene function than co-expression network centrality.