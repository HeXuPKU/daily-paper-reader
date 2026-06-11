---
title: "High-Dimensional Sensitivity Analysis for Genomic Studies: An Adversarial Framework for Learning Worst-Case Latent Confounders"
title_zh: 基因组研究的高维敏感性分析：一种学习最坏情况潜在混杂因素的对抗框架
authors: "Lin, Y., Lin, K."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.27.728283v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 用于基因组混杂分析的深度学习对抗框架
tldr: 高维基因组研究常因未测量混杂因素导致假阳性，现有方法无法量化发现对假设混杂的稳健性。本文提出sensGAN，一种对抗深度学习框架，通过预测增益约束学习最差潜在混杂变量，最小化基因关联，从而定量识别解释观察效应所需的最小混杂强度。模拟实验表明该方法能准确恢复潜在结构，优于现有方法识别混杂敏感基因。在阿尔茨海默病小胶质细胞数据中，成功分离稳健疾病通路与由未测量共病病理驱动的信号，提供了实用的灵敏度分析工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法无法量化基因发现对假设混杂强度的稳健性，需要一种正式的灵敏度分析框架来评估结果可靠性。
method: 提出sensGAN对抗框架，通过预测增益约束学习最差潜在混杂变量，系统探索混杂谱并识别所需最小混杂强度。
result: 在模拟中准确恢复潜在结构，优于现有方法；在阿尔茨海默病数据中成功区分稳健疾病通路与混杂信号。
conclusion: sensGAN为高维基因组研究提供定量灵敏度分析，有助于识别稳健的生物标志物并公开可用。
---

## 摘要
高维基因组学研究常常受到未测量的生物学过程的混杂影响，这些过程掩盖了疾病特异性信号。虽然现有工作流程可以估计这些潜在混杂因素，但它们无法量化发现对不同水平假设混杂的稳健性。我们提出了sensGAN，一种深度学习对抗框架，通过在新颖的预测增益约束下学习“最坏情况”潜在变量来系统探索混杂谱，这些变量会消除最多的基因关联。通过识别解释观察到的效应所需的最小混杂强度，我们的方法将范式转向正式的定量敏感性分析。在各种模拟中，sensGAN准确恢复了潜在结构，并在识别对混杂敏感的基因方面优于现有方法。应用于人类阿尔茨海默病小胶质细胞，我们的框架优先考虑了稳健的疾病通路，同时成功分离了由未测量的共病神经退行性病理驱动的信号。我们的方法公开可用，存放在GitHub仓库yifanlinz/AD_sensitivity_ICML中。

## Abstract
High-dimensional genomics studies are frequently confounded by unmeasured biological processes that obscure disease-specific signals. While existing workflows can estimate these latent confounders, they fail to quantify how robust a discovery is to varying levels of hypothetical confounding. We introduce sensGAN, a deep-learning adversarial framework that systematically explores the confounding spectrum by learning "worst-case" latent variables that nullify the most gene associations under novel predictive-gain constraints. By identifying the minimum confounding strength required to explain away an observed effect, our method shifts the paradigm toward a formal, quantitative sensitivity analysis. In diverse simulations, sensGAN accurately recovers latent structures and outper-forms existing methods in identifying confounder-sensitive genes. Applied to human Alzheimers disease microglia, our framework prioritizes robust disease pathways while successfully isolating signals driven by unmeasured co-occurring neurodegenerative pathologies. Our method is publicly available, deposited at the GitHub repository yifanlinz/AD_sensitivity_ICML.