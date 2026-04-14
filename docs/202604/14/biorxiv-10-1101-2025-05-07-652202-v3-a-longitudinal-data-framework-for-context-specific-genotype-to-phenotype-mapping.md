---
title: A longitudinal data framework for context-specific genotype-to-phenotype mapping
title_zh: 一种用于特定情境下基因型到表型映射的纵向数据框架
authors: "Veith, T., Beck, R. J., Tagal, V., Li, T., Alahmari, S., Cole, J., Hannaby, D., Kyei, J., Yu, X., Maksin, K., Schultz, A., Lee, H., Diaz, A., Lupo, J., El Naqa, I., Eschrich, S. A., Ji, H., Andor, N."
date: 2026-04-08
pdf: "https://www.biorxiv.org/content/10.1101/2025.05.07.652202v3.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 纵向癌症数据中基因型到表型映射的框架
tldr: CLONEID是一个基于事件的数据框架，旨在解决纵向研究中分子检测稀疏与表型观测频繁之间的脱节问题。它通过整合时间戳事件、特定分析视角和协调身份，实现了克隆分辨率下的表型、分子及样本背景记录的统一管理。该框架在胃癌长期实验中得到验证，成功关联了生长测量与核型分析，为研究表型适应及其背后的染色体状态提供了持续的基因型-表型映射支持。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-05-07-652202-v3/fig-001.webp\", \"caption\": \"Figure 1: Event-based architecture of CLONEID. (A) The same data model is used across clinical, in vivo and in vitro settings. Time-stamped Events capture specimen relationships, interventions and environmental context. (B) Longitudinal phenotype measurements anchor every event. (C) Assay-specific molecular readouts are represented as Perspectives, which preserve what was measured together with the upstream data required for provenance. (D) Multiple Perspectives are reconciled into an inferred Identity across assays and time. Together, this design enables integrated, queryable and reproducible retrieval of longitudinal genotype–phenotype records.\", \"page\": 2, \"index\": 1, \"width\": 1129, \"height\": 586}]"
motivation: 现有的分子检测成本高且时间跨度大，而频繁收集的表型数据往往缺乏长期解释所需的样本背景信息。
method: 开发了CLONEID框架，通过结构化摄取、溯源检索和可重复导出，将时间戳事件、分析视角与协调后的克隆身份进行关联。
result: 在胃癌密度选择实验中，该框架成功整合了重复培养事件、生长测量和后期核型分析，支持了对表型适应的纵向解释。
conclusion: CLONEID为纵向研究中的基因型到表型映射提供了有效的组织工具，能够跨时间维持复杂的生物学解释。
---

## 摘要
分子检测可以解析克隆结构，但其成本高昂且在时间分布上通常较为稀疏，而诸如成像之类的表型观测虽然可以频繁收集，但往往未能保存在后续解释所需的背景信息中。我们提出了 CLONEID，这是一个基于事件的框架，用于组织克隆解析的表型、分子和样本背景记录，从而使基因型到表型的解释能够跨时间维持。CLONEID 通过结构化摄取、来源感知的检索和可重复的导出，将带有时间戳的事件（Events）、特定检测的视角（Perspectives）和协调一致的身份（Identities）联系起来，是对上游克隆识别（clone-calling）方法的补充。在一项长期的胃癌密度选择实验中，CLONEID 在共享记录中关联了重复的培养事件、生长测量和后期的核型分析，支持了对表型适应及其底层染色体状态的纵向解释。

## Abstract
Molecular assays can resolve clonal structure, but they are expensive and typically sparse in time, whereas phenotypic observations such as imaging can be collected frequently but often are not preserved in the context needed for later interpretation. We present CLONEID, an event-based framework for organizing clone-resolved phenotypic, molecular, and specimen-context records so that genotype-to-phenotype interpretation can be maintained across time. CLONEID links time-stamped Events, assay-specific Perspectives, and reconciled Identities through structured ingestion, provenance-aware retrieval, and reproducible export, complementing upstream clone-calling methods. In a long-term gastric cancer density-selection experiment, CLONEID linked repeated culture events, growth measurements, and late karyotypic profiling within a shared record, supporting longitudinal interpretation of phenotypic adaptation together with underlying chromosomal state.