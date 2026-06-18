---
title: COMPASS enables cohort-independent digital biomarker discovery and pathway quantification
title_zh: COMPASS实现与队列无关的数字生物标志物发现和通路量化
authors: "Sinha, S., Ghosh, P."
date: 2026-06-14
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.02.687315v4.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 一种不依赖参考队列的通路活性评分方法可作为功能基因组整合框架
tldr: 精准医学中通路活性定量常依赖参考队列，导致可重复性差。COMPASS框架通过数据驱动推导基因特异性激活阈值，并标准化偏差，将方向相反的基因整合为复合评分，无需外部参考。在多种数据集中，COMPASS显著优于GSVA和ssGSEA，尤其对双向基因程序稳健。该方法提供了精确、可解释且临床可转化的生物标志物发现与结果建模方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有通路活性评分依赖参考队列，可重复性和临床转化性不足，亟需不依赖队列的精确定量方法。
method: COMPASS从数据中推导基因激活阈值，标准化偏差，并整合方向相反基因，构建复合活性评分，无需参考队列或归一化。
result: COMPASS在多种数据集上稳健量化细胞状态，比GSVA/ssGSEA更一致，对双向程序尤其鲁棒，成功应用于脓毒症基因签名。
conclusion: COMPASS解决了可重复性和临床转化的关键需求，为生物标志物发现和结果预测提供了可解释的定量框架。
---

## 摘要
可重复且临床可转移的通路活性量化仍然是精准医学的主要障碍，其中生物标志物性能通常取决于队列组成和标准化策略。在此，我们介绍COMPASS（复合活性评分系统），这是一个基于确定性阈值的框架，无需依赖参考队列即可将基因表达转化为定量通路活性评分。COMPASS直接从数据中推导基因特异性激活阈值，标准化偏离阈值，并将方向相反的基因整合为一个复合评分。这使得无需编码即可进行透明的活性评分、统计比较和生存分析。跨多种生物学和临床数据集，COMPASS稳健地量化细胞状态，对新方法的拟人性和疾病相关性进行基准测试，并分层结果。与GSVA和ssGSEA相比，COMPASS在数据集之间表现出更高的一致性，并在自举分析中具有更强的稳健性，特别是对于双向程序，包括经监管批准的脓毒症基因特征。因此，COMPASS解决了在不同生物学和临床环境中精确、可解释且临床可转移的生物标志物发现和结果建模的关键未满足需求。

## Abstract
Reproducible and clinically transferable quantification of pathway activity remains a major barrier in precision medicine, where biomarker performance often depends on cohort composition and normalization strategies. Here, we introduce COMPASS (COMPosite Activity Scoring System), a deterministic threshold-based framework that converts gene expression into quantitative pathway activity scores without reliance on reference cohorts. COMPASS derives gene-specific activation thresholds directly from data, standardizes deviations from thresholds, and integrates directionally opposing genes into a single composite score. This enabled transparent activity scoring, statistical comparisons, and survival analyses without coding. Across diverse biological and clinical datasets, COMPASS robustly quantified cellular states, benchmarked the humanness and disease relevance of new approach methodologies, and stratified outcomes. Compared to GSVA and ssGSEA, COMPASS demonstrated greater consistency across datasets and improved robustness in bootstrap analyses, particularly for bidirectional programs, including regulatory-approved sepsis gene signatures. COMPASS therefore addresses a critical unmet need for exact, interpretable, and clinically transferable biomarker discovery and outcome modeling across diverse biological and clinical settings.