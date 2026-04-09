---
title: A longitudinal data framework for context-specific genotype-to-phenotype mapping
title_zh: 一种用于特定背景下基因型到表型映射的纵向数据框架
authors: "Veith, T., Beck, R. J., Tagal, V., Li, T., Alahmari, S., Cole, J., Hannaby, D., Kyei, J., Yu, X., Maksin, K., Schultz, A., Lee, H., Diaz, A., Lupo, J., El Naqa, I., Eschrich, S. A., Ji, H., Andor, N."
date: 2026-04-08
pdf: "https://www.biorxiv.org/content/10.1101/2025.05.07.652202v3.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 跨纵向分子和临床记录的基因型到表型映射框架
tldr: 针对分子检测昂贵且时间稀疏，而表型观测频繁但易丢失背景信息的问题，本文提出了CLONEID框架。这是一个基于事件的纵向数据管理框架，通过整合时间戳事件、特定分析视角和协调身份，实现了克隆分辨率下的表型、分子及样本背景记录的统一组织。该框架支持跨时间的基因型到表型的映射，并在胃癌长期实验中成功关联了培养事件、生长测量与核型分析，为研究表型适应及其染色体状态提供了有力工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-05-07-652202-v3/fig-001.webp\", \"caption\": \"Figure 1: Event-based architecture of CLONEID. (A) The same data model is used across clinical, in vivo and in vitro settings. Time-stamped Events capture specimen relationships, interventions and environmental context. (B) Longitudinal phenotype measurements anchor every event. (C) Assay-specific molecular readouts are represented as Perspectives, which preserve what was measured together with the upstream data required for provenance. (D) Multiple Perspectives are reconciled into an inferred Identity across assays and time. Together, this design enables integrated, queryable and reproducible retrieval of longitudinal genotype–phenotype records.\", \"page\": 2, \"index\": 1, \"width\": 1129, \"height\": 586}]"
motivation: 现有的分子检测与表型观测在时间频率和背景保留上存在不匹配，导致难以维持长期的基因型到表型的关联解释。
method: 提出了CLONEID框架，通过结构化摄取、溯源检索和可重复导出，将时间戳事件、分析视角与克隆身份进行关联。
result: 在胃癌细胞密度选择实验中，该框架成功整合了重复培养、生长测量及后期核型分析数据，支持了对表型适应性的纵向分析。
conclusion: CLONEID为复杂生物实验提供了稳健的数据组织方案，有效促进了对克隆演化过程中基因型与表型关系的深入理解。
---

## 摘要
分子检测可以解析克隆结构，但其成本高昂且在时间分布上通常较为稀疏；相比之下，成像等表型观察虽然可以频繁采集，但往往未能保存在后续解释所需的背景信息中。我们提出了 CLONEID，这是一个基于事件的框架，用于组织克隆解析的表型、分子和标本背景记录，从而使基因型到表型的解释能够跨时间维持。CLONEID 通过结构化摄取、来源感知检索和可重复导出，将带有时间戳的事件（Events）、特定检测的视角（Perspectives）以及协调后的身份（Identities）联系起来，补充了上游的克隆识别（clone-calling）方法。在一项长期的胃癌密度选择实验中，CLONEID 在共享记录中链接了重复的培养事件、生长测量和后期的核型分析，支持了对表型适应及其底层染色体状态的纵向解释。

## Abstract
Molecular assays can resolve clonal structure, but they are expensive and typically sparse in time, whereas phenotypic observations such as imaging can be collected frequently but often are not preserved in the context needed for later interpretation. We present CLONEID, an event-based framework for organizing clone-resolved phenotypic, molecular, and specimen-context records so that genotype-to-phenotype interpretation can be maintained across time. CLONEID links time-stamped Events, assay-specific Perspectives, and reconciled Identities through structured ingestion, provenance-aware retrieval, and reproducible export, complementing upstream clone-calling methods. In a long-term gastric cancer density-selection experiment, CLONEID linked repeated culture events, growth measurements, and late karyotypic profiling within a shared record, supporting longitudinal interpretation of phenotypic adaptation together with underlying chromosomal state.