---
title: Empirical estimation of multiple-testing burden for population-based HLA association studies using sequencing-derived HLA alleles across genetic ancestries
title_zh: 使用测序得到的HLA等位基因跨遗传祖先对基于人群的HLA关联研究中多重检验负担的经验估计
authors: "Taliun, D., Gagliano Taliun, S. A."
date: 2026-07-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.12.738059v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: HLA关联研究的多重检验负担估计，扩展GWAS统计方法
tldr: "针对HLA等位基因关联分析缺乏多重检验校正指南的问题，本研究利用跨祖先测序数据、分析推导和模拟，系统评估了有效独立检验数。结果发现检验负担取决于遗传祖先、等位基因频率和表型模型，但稳定在测试等位基因总数的60-70%，高分辨率下成比例缩放。这支持使用Bonferroni校正作为简单稳健的近似方法。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-12-738059-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1696, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-12-738059-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1678, \"height\": 902, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-12-738059-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1709, \"height\": 552, \"label\": \"Table\"}]"
motivation: HLA关联研究缺乏多重检验负担的通用控制指导，需基于跨祖先数据系统评估有效独立检验数。
method: 利用不同遗传祖先的测序数据，通过分析推导和模拟，评估HLA等位基因有效独立检验数及其影响因素。
result: "有效检验数约为测试等位基因总数的60-70%，在现实疾病模型下可超90%，且高分辨率分型成比例缩放。"
conclusion: 基于测试HLA等位基因总数的Bonferroni校正是简单稳健的近似，适用于置换法不可行时。
---

## 摘要
随着人群规模的全基因组测序数据集不断扩大，它们使得遗传关联研究能够超越单核苷酸变异，扩展到更复杂的遗传变异形式，包括经典的人类白细胞抗原（HLA）等位基因。HLA区域包含九个高度多态的经典HLA基因，它们处于广泛的连锁不平衡中，并与众多自身免疫性和感染性疾病相关。然而，与单核苷酸变异全基因组关联研究不同，在HLA等位基因关联分析中，对于控制多重检验负担尚无通用指导。本文利用来自不同遗传祖先的测序数据、分析推导和模拟，系统评估了独立HLA等位基因检验的有效数量。我们表明，多重检验负担取决于遗传祖先、等位基因频率和表型模型，但在不同的小等位基因计数阈值下保持显著稳定，相当于被测HLA等位基因总数的约60-70%。模拟进一步表明，在现实疾病模型下，有效检验数量可超过90%。对来自长读长测序的4字段HLA等位基因的分析显示，更高的分型分辨率增加了等位基因数量，但保留了潜在的关联结构，并按比例缩放独立检验的有效数量。我们的结果为HLA关联研究提供了实用指导，并支持在基于置换的方法不可行时，将被测HLA等位基因总数作为简单稳健的近似进行邦费罗尼校正。

## Abstract
As population-scale whole-genome sequencing datasets continue to expand, they enable genetic association studies beyond single-nucleotide variants to more complex forms of genetic variation, including classical human leukocyte antigen (HLA) alleles. The HLA region comprises nine highly polymorphic classical HLA genes in extensive linkage disequilibrium that are associated with numerous autoimmune and infectious diseases. However, unlike genome-wide association studies of single-nucleotide variants, there is no general guidance for controlling the multiple-testing burden in HLA allele association analyses. Here, we systematically evaluated the effective number of independent HLA allele tests using sequencing data from diverse genetic ancestries, analytical derivation and simulations. We show that the multiple-testing burden depends on genetic ancestry, allele frequency, and the phenotype model, but remains remarkably stable across minor allele count thresholds, corresponding to approximately 60-70% of the total number of tested HLA alleles. Simulations further demonstrate that the effective number of tests can exceed 90% under realistic disease models. Analyses of 4-field HLA alleles from long-read sequencing showed that higher typing resolution increases the number of alleles but preserves the underlying correlation structure and scales the effective number of independent tests proportionally. Our results provide practical guidance for HLA association studies and support Bonferroni correction based on the total number of tested HLA alleles as a simple and robust approximation when permutation-based approaches are impractical.