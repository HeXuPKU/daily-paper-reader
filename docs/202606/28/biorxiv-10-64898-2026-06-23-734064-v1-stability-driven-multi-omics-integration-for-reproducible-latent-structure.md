---
title: Stability-driven multi-omics integration for reproducible latent structure
title_zh: 基于稳定性的多组学整合用于可重复潜在结构识别
authors: "Guan, H., Gerwen, M. v., Kim-Schulze, S., Colicino, E., Dolios, G., Petrick, L."
date: 2026-06-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.23.734064v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 多组学整合框架及稳定性评估，可用于GWAS功能整合
tldr: 高维多组学数据整合常因采样变异导致结果不可重复。本文提出稳定性驱动框架，结合稀疏广义典型相关分析与重复交叉验证、样本外投影及稳定性评估。在甲状腺癌队列中，该方法识别出可重复的代谢组与蛋白质组潜在成分，且与疾病关联一致并反映时序变化。该框架为多组学研究提供了提升可重复性和生物推断稳健性的通用策略。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有高维多组学整合方法因采样变异性导致潜在结构不可重复，缺乏系统稳定性评估。
method: 提出稳定性驱动框架，融合稀疏广义典型相关分析、重复交叉验证、样本外投影及组件与特征级稳定性评估。
result: 在甲状腺癌队列中识别出可重复的代谢组与蛋白质组潜在成分，其与疾病一致关联并反映诊断前时序变化。
conclusion: 该框架可推广至其他多组学场景，提高潜在结构可重复性与生物推断稳健性。
---

## 摘要
高维多组学数据整合为刻画复杂生物系统提供了新的机会。尽管采样变异性经常影响发现结果的可靠性，特别是在小样本队列中，但所推导的潜在结构的可重复性和泛化性尚未得到充分评估。我们提出了一种基于稳定性的多组学整合框架，该框架将稀疏广义典型相关分析与重复交叉验证、样本外投影以及组分层面和特征层面稳定性的系统评估相结合。我们将该框架应用于甲状腺癌病例对照队列（n=162）中的非靶向代谢组学和Olink靶向炎症蛋白质组学数据。我们的基于稳定性的整合识别出了可重复的代谢组学和蛋白质组学潜在组分，这些组分在样本外疾病关联中表现出一致性，并追踪了相对于诊断时间的时间结构变化。所提出的框架提供了一种通用的策略，用于识别可重复的潜在结构，从而提高多组学研究中生物推断的稳健性。

## Abstract
High-dimensional multi-omics data integration offers novel opportunities to characterize complex biological systems. Even though sampling variability frequently compromises findings, particularly in small cohorts, the reproducibility and generalizability of the derived latent structures are insufficiently evaluated. We propose a Stability-driven framework for multi-omics integration that combines sparse generalized canonical correlation analysis with repeated cross-validation, out-of-sample projection, and systematic evaluation of both component-level and feature-level stability. We apply this framework to untargeted metabolomic and Olink targeted inflammation proteomic profiles in a thyroid cancer case-control cohort (n = 162). Our Stability-driven integration identified reproducible metabolomic and proteomic latent components that showed consistent out-of-sample disease associations and tracked temporally structured changes relative to time to diagnosis. The proposed framework provides a generalizable strategy for identifying reproducible latent structures that improve robustness of biological inference in multi-omics studies.