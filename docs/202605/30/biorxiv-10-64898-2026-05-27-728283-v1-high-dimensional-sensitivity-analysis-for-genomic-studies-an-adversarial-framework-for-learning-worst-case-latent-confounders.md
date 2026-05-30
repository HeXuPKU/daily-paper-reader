---
title: "High-Dimensional Sensitivity Analysis for Genomic Studies: An Adversarial Framework for Learning Worst-Case Latent Confounders"
title_zh: 基因组研究的高维敏感性分析：一种学习最坏情况潜在混杂因素的对抗框架
authors: "Lin, Y., Lin, K."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.27.728283v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 基因组研究中的对抗敏感性分析框架，与GWAS混淆因子相关
tldr: 高维基因组学研究中未测量的混杂因素会掩盖疾病特异性信号。现有方法虽能估计潜在混杂，但无法量化发现的稳健性。本文提出sensGAN对抗框架，通过学习最坏情况潜在变量并施以预测增益约束，消除最多基因关联，从而识别解释效应所需的最小混杂强度。在模拟和阿尔茨海默病数据中，该方法准确恢复潜在结构，优先识别稳健通路，并成功隔离神经退行病理混杂信号。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基因组学敏感性分析无法量化发现对未测量混杂的稳健性，缺乏形式化定量框架。
method: 提出sensGAN对抗框架，通过学习最坏情况潜在变量并施以预测增益约束，最小化基因关联以探测混杂边界。
result: 模拟中准确恢复潜在结构并优于现有方法；阿尔茨海默病小胶质细胞数据中成功区分稳健通路与混杂信号。
conclusion: sensGAN提供形式化敏感性分析方法，量化发现对未测量混杂的稳健性，提升基因组学发现的可靠性。
---

## 摘要
高维基因组研究常常受到未测量的生物过程的混杂影响，这些过程掩盖了疾病特异性信号。虽然现有工作流程可以估计这些潜在混杂因素，但它们无法量化一个发现在不同水平的假设性混杂下有多稳健。我们引入了sensGAN，这是一个深度学习对抗框架，通过在学习具有新颖预测增益约束下使最多基因关联失效的“最坏情况”潜在变量，系统地探索混杂谱。通过识别解释所观察效应所需的最小混杂强度，我们的方法将范式转向形式化、定量的敏感性分析。在多种模拟中，sensGAN准确恢复了潜在结构，并在识别混杂敏感基因方面优于现有方法。应用于人类阿尔茨海默病的小胶质细胞，我们的框架优先考虑稳健的疾病通路，同时成功隔离了由未测量的共现神经退行性病理驱动的信号。我们的方法已公开，存放在GitHub仓库yifanlinz/AD_sensitivity_ICML。

## Abstract
High-dimensional genomics studies are frequently confounded by unmeasured biological processes that obscure disease-specific signals. While existing workflows can estimate these latent confounders, they fail to quantify how robust a discovery is to varying levels of hypothetical confounding. We introduce sensGAN, a deep-learning adversarial framework that systematically explores the confounding spectrum by learning "worst-case" latent variables that nullify the most gene associations under novel predictive-gain constraints. By identifying the minimum confounding strength required to explain away an observed effect, our method shifts the paradigm toward a formal, quantitative sensitivity analysis. In diverse simulations, sensGAN accurately recovers latent structures and outperforms existing methods in identifying confounder sensitive genes. Applied to human Alzheimer's disease microglia, our framework prioritizes robust disease pathways while successfully isolating signals driven by unmeasured co-occurring neurodegenerative pathologies. Our method is publicly available, deposited at the GitHub repository yifanlinz/AD_sensitivity_ICML.