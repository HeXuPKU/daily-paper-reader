---
title: Human Proteome-wide Mechanistic Interpretation of Missense Variants through Protein Feature Enrichment Score
title_zh: 人类蛋白质组规模错义变异的机制性解释：基于蛋白质特征富集分数
authors: "Kwon, S., Safer, J., DiStefano, M., Lebo, M., Rehm, H. L., Iqbal, S."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.26.726248v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 蛋白质特征富集用于错义变异解释，辅助因果变异识别
tldr: "错义变异解读是临床遗传学核心挑战，多数为意义不明确变异。本研究提出蛋白质特征富集分数（PFES），基于103个蛋白质结构、功能和理化特征，对85,321个致病和130,719个对照变异进行统计富集。PFES将变异划分为PF富集（致病样）、PF中性、PF耗尽（良性样），并通过可解释特征子分数揭示机制。结果显示PFES与VUS重分类高度一致，区分功能丧失与功能获得变异。已计算2.23亿可能错义变异，构建公开资源，提供致病性及蛋白质特征破坏的解读。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有错义变异预测工具准确率高但缺乏机制解释，且大多数变异为意义不明确变异，亟需可翻译的解读方法。
method: 基于20个蛋白质功能类别的103个特征，对致病和对照变异进行统计富集，计算PFES并分解为生物学可解释的子分数。
result: "PFES将变异分为三类，与VUS重分类一致；功能获得变异富集蛋白质相互作用特征；覆盖2.23亿变异，17.7%为PF富集。"
conclusion: PFES不仅预测致病性，还能揭示破坏的蛋白质特征，为罕见病基因和治疗靶点研究提供机制依据。
---

## 摘要
错义变异解读仍是临床和医学遗传学中的核心挑战，大多数观察到的变异属于意义未明变异（VUS）。计算性变异效应预测器可实现高致病性分类性能，但无法揭示潜在机制和可转化的解读。在此，我们提出蛋白质特征富集分数（PFES），通过统计富集103种蛋白质结构、功能和理化特征（涵盖20个蛋白质功能类别的85,321个致病变异和130,719个对照变异），量化错义变异的分子背景。我们显示，变异的蛋白质特征（PF）富集模式在功能类别内保守，而在类别间变化显著，其幅度和方向取决于功能背景。PFES不仅将变异划分为PF-富集（致病样）、PF-中性 和 PF-贫乏（良性样）类别，还通过将分数分解为来自生物学可解释蛋白质特征属性的子分数，提供机制性解读。我们证明，PFES与VUS重分类和优先级排序具有高度一致性：在596个基因中，倾向致病性的VUS-high变异在PF-富集变异中富集了七倍。PFES分解进一步揭示，功能缺失和功能获得变异的区别在于后者中蛋白质-蛋白质相互作用特征的不成比例富集。我们计算了2.23亿个可能的错义变异（17.7%为PF-富集）的PFES，并构建了一个公共资源，不仅解决变异是否致病的问题，还指出哪些蛋白质特性被破坏。在20,153个基因上的蛋白质组范围应用优先考虑了已知的罕见病基因，并提名了治疗上可干预的靶点，这些靶点的致病变异由可解释的结构和功能蛋白质特征破坏驱动。

## Abstract
Missense variant interpretation remains a central challenge in clinical and medical genetics, with most observed variants being variants of uncertain significance (VUS). Computational variant effect predictors can achieve high pathogenicity classification performance, but without revealing the underlying mechanism and a translatable interpretation. Here we present the Protein Feature Enrichment Score (PFES), which quantifies the molecular context of missense variants through statistical enrichment of 103 protein structural, functional, and physicochemical features across 85,321 pathogenic and 130,719 control variants spanning 20 protein functional classes. We show that the protein feature (PF) enrichment patterns of variants are conserved within functional classes and vary substantially across classes, both in magnitude and directions depending on functional context. PFES not only partitions variants into PF-Enriched (pathogenic-like), PF-Neutral, and PF-Depleted (benign-like) categories but also provides a mechanistic interpretation by decomposing the score into subscores from biologically interpretable protein feature attributes. We demonstrate that PFES shows a high concordance with VUS reclassification and prioritization: across 596 genes, pathogenicity-leaning VUS-high variants were seven-fold enriched in PF-Enriched variants. PFES decomposition further revealed that loss-of-function and gain-of-function variants are distinguished by disproportionate enrichment of protein-protein interaction features in the latter. We computed PFES across 223 million possible missense variants (17.7% PF-Enriched) and built a publicly available resource that addresses not just whether a variant is pathogenic, but which protein characteristics are disrupted. Proteome-wide application across 20,153 genes prioritizes established rare disease genes and nominates therapeutically amenable targets whose pathogenic variation is driven by interpretable structural and functional protein feature disruption.