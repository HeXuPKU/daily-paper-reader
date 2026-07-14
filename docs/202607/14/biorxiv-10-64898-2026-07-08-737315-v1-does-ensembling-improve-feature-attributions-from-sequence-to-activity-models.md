---
title: Does ensembling improve feature attributions from sequence-to-activity models?
title_zh: 集成方法能否改进序列到活性模型的特征归因？
authors: "Maslova, A., Libbrecht, M."
date: 2026-07-13
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.08.737315v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 研究序列到活性模型中集成方法对可解释性的改进，有助于变异效应解读。
tldr: 序列到活动模型广泛应用于基因组活动预测，但其特征归因可靠性不足。本文评估模型集成能否改善归因质量，发现集成多个模型的归因显著提升转录因子模体识别与调控遗传变异预测等下游任务。蒙特卡洛丢弃法以更低训练代价接近多模型集成性能，表明集成是提升归因可靠性的有效策略，尤其适合计算资源有限场景。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737315-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1706, \"height\": 947, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737315-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1704, \"height\": 1011, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737315-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1698, \"height\": 1526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737315-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1703, \"height\": 1166, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-08-737315-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1395, \"height\": 314, \"label\": \"Table\"}]"
motivation: 当前特征归因缺乏可靠性度量，需要探索通过模型集成提升归因质量的方法。
method: 训练多个独立模型或采用蒙特卡洛丢弃法形成集成，用DeepLIFT计算归因后集成，对比不同方式对下游任务的影响。
result: 集成多个模型的归因显著改善模体识别和变异预测；蒙特卡洛丢弃法以较低成本接近多模型集成效果。
conclusion: 模型集成能有效提升基因组特征归因质量，蒙特卡洛丢弃法在训练效率上具有优势，为xAI在基因组学的应用提供实用方案。
---

## 摘要
序列到活性模型以DNA序列为输入，预测转录因子结合和基因表达等基因组活性。应用DeepLIFT等可解释AI方法于这些模型，近期已在许多基因组问题上取得突破，包括转录因子结合语法和预测遗传变异效应。然而，序列到活性解释的可靠性仍存在显著不确定性。因此，我们需要准确的置信度概率度量来区分可靠与不可靠的解释。为此，研究人员近期致力于表征S2A模型集成间的变异性。然而，先前工作侧重于使用模型集成来改进模型预测本身。本文旨在评估模型集成是否也能用于改进事后xAI方法的特征归因。我们发现，对多个模型的归因进行集成可改进下游应用，包括识别转录因子基序和预测调控性遗传变异。我们证明，使用蒙特卡洛dropout形成集成在训练时计算成本低得多的情况下，能接近但未达到训练多个模型的性能。

## Abstract
Sequence-to-activity models take as input DNA sequence and predict genomic activities such as transcription factor binding and gene expression. Applying explainable AI (xAI) methods such as DeepLIFT to these models has recently led to breakthroughs towards many genomic problems, including transcription factor binding grammar and predicting effects of genetic variants. However, there remains significant uncertainty about the reliability of sequence-to-activity interpretations.Thus, we need accurate probabilistic measures of confidence to distinguish reliable from unreliable interpretations. Towards this end, researchers have recently aimed to characterize variability acrossensembles of S2A models. However, previous work has focused on using model ensembles to improve the model predictions themselves. Here, we aim to evaluate whether model ensembles can also be used to improve feature attributions from post-hoc xAI methods. We find that ensembling attributions from multiple models improves downstream applications, including identifying transcription factor motifs and predicting regulatory genetic variants. We show that forming an ensemble using Monte Carlo Dropout (MCDropout) gets near to, but does not match, the performance of training multiple models, at much less train-time computational cost.