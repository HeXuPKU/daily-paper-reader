---
title: "eQTM (expression quantitative trait methylation) Atlas: a comprehensive resource of over 11 million DNA methylation-gene expression associations through across 11 tissues and 4 diseases"
title_zh: eQTM（表达数量性状甲基化）图谱：涵盖11种组织与4种疾病的超过1100万个DNA甲基化-基因表达关联的综合资源
authors: "Sriram, A., Kim, S., Caldino Bohn, R., Chen, W., Liu, T., Yue, M., Jain, N., Pierce, B., Joehanes, R., Levy, D., Patin, E., Quintana-Murci, L., Park, H. J., Celedon, J. C."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.07.730721v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: eQTM资源连接DNA甲基化与基因表达，可用于整合功能基因组学与GWAS
tldr: 表观基因组关联研究（EWAS）发现大量疾病相关DNA甲基化位点，但常仅基于基因组邻近性注释到基因，功能解读困难。我们构建了eQTM Atlas，通过整合8个队列数据，系统评估跨11种组织和4种疾病的DNA甲基化与基因表达关联（超过1100万对）。该资源涵盖17万余CpG探针和2万余基因，提供基因或CpG搜索、可视化及下载功能。将疾病相关甲基化位点与统计关联的基因连接，替代单纯邻近性注释，支持EWAS发现的功能解析和疾病特异性调控假说生成。
source: biorxiv
selection_source: fresh_fetch
motivation: 缺乏整合多组织疾病eQTM的综合性资源，导致EWAS结果功能解读困难。
method: 手动筛选8个队列数据，构建包含1100万DNA甲基化-基因表达关联的数据库，覆盖11组织4疾病。
result: 资源涵盖173886个CpG探针和20231个基因，支持多种搜索与可视化功能。
conclusion: 整合eQTM与EWAS资源，提供疾病相关CpG到基因的统计关联，超越邻近性注释。
---

## 摘要
动机：表观基因组关联研究（EWAS）已识别出许多与复杂性状和疾病相关的DNA甲基化（DNAm）CpG位点，但解释这些CpG位点仍具挑战性，因为在EWAS中，CpG通常仅基于基因组邻近性与附近基因关联。表达数量性状甲基化（eQTM）分析将DNAm CpG与统计上相关的基因表达水平联系起来。然而，缺乏一个整合不同组织和疾病背景下eQTMs的全面、可搜索的资源。结果：我们开发了eQTM图谱，这是一个基于网络的资源，手动整理了来自八个队列的超过1100万个DNAm-基因表达关联，涵盖11种组织类型、四个广泛的疾病背景、173,886个独特CpG探针和20,231个独特基因。该图谱支持按组织或疾病类型进行基因或CpG搜索，发现相关CpG或基因，通过基因组浏览器、跨不同组织的热图界面可视化顺式和反式eQTMs，以及队列级数据下载。通过将eQTM结果与EWAS资源整合，eQTM图谱使用户能够将疾病或性状相关的CpG与统计相关的基因联系起来，而不仅仅是依赖于基于邻近性的基因注释，从而支持EWAS发现的功能解释和疾病特异性调控假设的生成。可用性和实现：eQTM图谱在https://shiny.crc.pitt.edu/eqtm_browser/上免费提供。网络界面使用R Shiny实现，并由匹兹堡大学研究计算中心（CRC）托管。源代码可在https://github.com/ads303/eQTM-Atlas获取。

## Abstract
Motivation: Epigenome-wide association studies (EWAS) have identified numerous DNA methylation (DNAm) CpG sites associated with complex traits and diseases, but interpretation of those CpG sites remains challenging because in EWAS, CpGs are mostly linked to nearby genes based only on genomic proximity. Expression quantitative trait methylation (eQTM) analyses connect DNAm CpGs with statistically associated gene expression levels. However, a comprehensive, searchable resource integrating eQTMs across diverse tissues and disease contexts has been lacking. Results: We developed the eQTM Atlas, a web-based resource that manually curates more than 11 million DNAm-gene expression associations from eight cohorts, covering 11 tissue types, four broad disease contexts, 173,886 unique CpG probes and 20,231 unique genes. The Atlas supports gene- or CpG- searches by tissue or disease type and finding associated CpG or genes, visualization of cis- and trans-eQTMs through genome browser, heatmap interfaces across various tissues, and cohort-level data downloads. By integrating eQTM results with EWAS resources, the eQTM Atlas enables users to connect disease- or trait-associated CpGs to statistically associated genes rather than relying solely on proximity-based gene annotation, supporting functional interpretation of EWAS findings and generation of disease-specific regulatory hypotheses. Availability and implementation: The eQTM Atlas is freely available at https://shiny.crc.pitt.edu/eqtm_browser/. The web interface is implemented in R Shiny and hosted through the University of Pittsburgh Center for Research Computing (CRC). Source code is available at https://github.com/ads303/eQTM-Atlas.