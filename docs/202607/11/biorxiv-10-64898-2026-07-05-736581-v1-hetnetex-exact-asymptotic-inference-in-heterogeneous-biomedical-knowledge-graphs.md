---
title: "HetNetEX: Exact Asymptotic Inference in Heterogeneous Biomedical Knowledge Graphs"
title_zh: HetNetEX：异质生物医学知识图谱中的精确渐近推断
authors: "Ghosh, T., Gillenwater, L. A., Greene, C. S., Costello, J. C."
date: 2026-07-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.05.736581v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 异质生物医学知识图精确渐近推断
tldr: "异质生物医学知识图谱中，标准XSwap置换方法检验路径显著性存在计算昂贵、p值分辨率有限等问题。本文提出HetNetEX，基于配置模型直接从度序列解析计算零分布，时间复杂度O(Ln)。在L=1-4模拟中，与XSwap排序的Spearman ρ>0.96，速度快10000倍以上，且无p值上限。该方法解决了高精度高效推断问题，尤其适用于长路径和大规模图。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-05-736581-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1786, \"height\": 1608, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-05-736581-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-05-736581-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 853, \"height\": 388, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-05-736581-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 679, \"height\": 417, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-05-736581-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 647, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-05-736581-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 683, \"height\": 587, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-05-736581-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 782, \"height\": 266, \"label\": \"Table\"}]"
motivation: XSwap置换法在大图中计算昂贵，长路径（L≥4）不可行，且p值分辨率有限，需精确高效替代方法。
method: HetNetEX基于配置模型从度序列解析计算度加权路径计数（DWPC）的零分布，时间复杂度O(Ln)，避免置换。
result: "在L=1-4模拟中，与XSwap（P=200）的Spearman ρ>0.96，速度快10000倍以上，提供无上限的解析p值。"
conclusion: HetNetEX以解析方式替代置换，高效精确评估异质生物医学知识图谱路径显著性，适用于长路径和大规模图。
---

## 摘要
异质生物医学知识网络（hetnets）整合了来自独立来源的不同数据类型，如药物、基因、疾病和通路；Hetionet（https://het.io）是一个广泛使用的例子。评估连接显著性的标准方法是XSwap，它将hetnet置换P次，并对度加权路径计数（DWPC）拟合伽马-障碍零模型，将匹配源度和目标度的配对之间的置换值进行池化以增加有效样本量。这种置换方法在实践中非常成功，但在大型图中面临四个实际限制：（1）最小可报告p值的有限分辨率，（2）路径长度L ≥ 4或5时计算成本变得过高，（3）方差模型（Var ∝ μ²）偏离配置模型形式（1+κ）μ，以及（4）运行时间为O(P·10^m·L)。为了补充该方法，我们提出了HetNetEX（异质网络精确推断），它使用配置模型在O(L·n)时间内从度序列解析地计算零DWPC分布。在P=200、L=1-4的模拟中，HetNetEX与XSwap排名的Spearman ρ > 0.96，同时速度快10000倍以上，并提供无分辨率上限的解析p值。高度数配对比低度数配对表现出更大的XSwap抽样误差，反映了置换的有限样本性质，而解析计算避免了这一问题。

## Abstract
Heterogeneous biomedical knowledge networks (hetnets) integrate disparate data types, drugs, genes, diseases, and pathways, across independent sources; Hetionet (https://het.io) is a widely used example. A standard approach for assessing connectivity significance is XSwap, which permutes the hetnet P times and fits a gamma-hurdle null model to the degree-weighted path count (DWPC), pooling permuted values across pairs with matching source and target degrees to increase the effective sample size. This permutation approach has been highly successful in practice, but it faces four practical constraints in large graphs: (1) a finite resolution for the smallest reportable p-values, (2) computational cost that grows prohibitive at path lengths L [&ge;] 4 or 5, (3) a variance model (Var {propto} {micro}2) that departs from the configuration-model form (1 +{kappa} ){micro}, and (4) O(P 10m L) runtime. To complement this approach, we present HetNetEX (Heterogeneous Network EXact inference), which computes the null DWPC distribution analytically from degree sequences using the configuration model in O(Ln) time. In simulations at P = 200 across L = 1-4, HetNetEX achieves Spearman{rho} > 0.96 concordance with XSwap rankings while being >10,000x faster and providing analytical p-values without a resolution ceiling. High-degree pairs show larger XSwap sampling error than low-degree pairs, reflecting the finite-sample nature of permutation that analytical computation avoids.