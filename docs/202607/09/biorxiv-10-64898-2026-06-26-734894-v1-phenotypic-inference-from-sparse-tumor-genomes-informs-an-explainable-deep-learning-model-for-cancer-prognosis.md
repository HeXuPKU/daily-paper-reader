---
title: Phenotypic inference from sparse tumor genomes informs an explainable deep-learning model for cancer prognosis
title_zh: 从稀疏肿瘤基因组推断表型为可解释的癌症预后深度学习模型提供信息
authors: "Grant, S., Nath, A."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.26.734894v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: PhenoMap利用机器学习从肿瘤基因组推断表型，与GWAS分析中的ML/DL应用相关
tldr: 癌症体细胞基因组变异是精准医疗的基础，但多数变异临床意义不明。现有AI模型缺乏可解释性。本研究提出PhenoMap框架，从稀疏肿瘤基因组推断表型状态，结合深度生存模型PhenoSurv，在多癌症中识别出关键预后因子。该方法在预测性能上超越现有模型，并提供机制性解释，推动可解释精准肿瘤学。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-26-734894-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1581, \"height\": 1683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-26-734894-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1633, \"height\": 1648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-26-734894-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1694, \"height\": 1258, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-26-734894-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1668, \"height\": 2379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-26-734894-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1670, \"height\": 980, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-26-734894-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1522, \"height\": 943, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-26-734894-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1708, \"height\": 1019, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-26-734894-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1659, \"height\": 1586, \"label\": \"Figure\"}]"
motivation: 现有AI模型在癌症预后中可解释性差，难以揭示基因与表型间的复杂相互作用，限制了临床转化。
method: 开发PhenoMap框架，利用9000个泛癌样本的基因组和转录组数据，通过机器学习从体细胞变异重建通路活性与表型特征，并集成到深度生存模型PhenoSurv中。
result: PhenoSurv在预后预测中优于现有模型，并发现NOTCH1信号、SMARCA4突变等在特定癌症中的关键预后作用。
conclusion: PhenoMap和PhenoSurv提供了准确、可解释且临床可行的精准肿瘤学模型，有望指导个性化治疗。
---

## 摘要
体细胞基因组改变在癌症中广泛被分析，并且仍然是个性化治疗的主要来源，但其临床效用仅限于少数可操作的靶点。AI/ML模型提供了捕捉全基因组复杂性的机会，但临床转化受到可解释性差、通常限于单基因效应以及忽视高阶表型相互作用的阻碍。为了解决这个问题，我们开发了PhenoMap，一个从体细胞变异推断肿瘤表型状态的机器学习框架。在9000个泛癌基因组和转录组上训练后，PhenoMap准确重建了基于表达的通路富集分数和整合的标志性癌症表型，实现了表型、通路和基因尺度的多层次解释。PhenoMap捕获了乳腺癌、肺癌和脑癌的分子亚型和关键耐药通路。我们在PhenoSurv中利用了这些特征，这是一个深度生存模型，整合了表型重建损失、Kullback-Leibler散度和生存损失，以学习生物学基础预测因子。PhenoSurv在提供稳健的机制解释的同时，优于最先进的生存模型。NOTCH1信号和SMARCA4突变成为激素受体阳性乳腺癌的主要预后因素。潜在由FAT1调节的TGF-β信号和炎症小体预测了肺腺癌的结局，而肌醇代谢和PI3K信号是脑癌的关键驱动因素。总之，PhenoMap和PhenoSurv为精准肿瘤学提供了准确、可解释且临床可操作的模型。

图形摘要

O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=191 SRC="FIGDIR/small/734894v1_ufig1.gif" ALT="图1">
查看更大版本 (37K):
org.highwire.dtl.DTLVardef@190f157org.highwire.dtl.DTLVardef@d496f1org.highwire.dtl.DTLVardef@101dbeeorg.highwire.dtl.DTLVardef@10e0799_HPS_FORMAT_FIGEXP  M_FIG C_FIG PhenoMap框架利用基因组数据和可解释的深度学习，为精准肿瘤学识别表型、通路和基因水平的预后标志物。

## Abstract
Somatic genomic alterations are widely profiled in cancer and remain the primary source for personalized therapy, yet their clinical utility is limited to few actionable targets. AI/ML models offer opportunities to capture genome-wide complexities, but clinical translation is hindered by poor interpretability, often limited to single-gene effects, and overlooks higher-order phenotypic interactions. To address this, we developed PhenoMap, a machine-learning framework that infers tumor phenotypic states from somatic variants. Trained on 9,000 pan-cancer genomes and transcriptomes, PhenoMap accurately reconstructs expression-based pathway enrichment scores and consolidated hallmark cancer phenotypes, enabling multilevel interpretation at phenotype, pathway, and gene scales. PhenoMap captured molecular subtypes and key resistance pathways across breast, lung, and brain cancers. We leveraged these features in PhenoSurv, a deep survival model integrating phenotypic reconstruction loss, Kullback-Leibler divergence, and survival loss to learn biologically-grounded predictors. PhenoSurv outperformed state-of-the-art survival models while providing robust mechanistic explanations. NOTCH1 signaling and SMARCA4 mutations emerged as a major prognostic factor in hormone receptor-positive breast cancer. TGF-{beta} signaling and inflammasomes, potentially modulated by FAT1, predicted lung adenocarcinoma outcomes, while inositol metabolism and PI3K signaling were key drivers in brain cancer. Together, PhenoMap and PhenoSurv provide accurate, interpretable, and clinically actionable models for precision oncology.

Graphical Abstract

O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=191 SRC="FIGDIR/small/734894v1_ufig1.gif" ALT="Figure 1">
View larger version (37K):
org.highwire.dtl.DTLVardef@190f157org.highwire.dtl.DTLVardef@d496f1org.highwire.dtl.DTLVardef@101dbeeorg.highwire.dtl.DTLVardef@10e0799_HPS_FORMAT_FIGEXP  M_FIG C_FIG PhenoMap framework leverages genomic data and explainable deep learning to identify phenotype, pathway, and gene-level prognostic markers for precision oncology.