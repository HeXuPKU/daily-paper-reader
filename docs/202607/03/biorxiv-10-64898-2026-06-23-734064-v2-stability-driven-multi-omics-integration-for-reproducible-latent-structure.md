---
title: Stability-driven multi-omics integration for reproducible latent structure
title_zh: 基于稳定性的多组学整合方法用于可重复的潜在结构识别
authors: "Guan, H., Gerwen, M. v., Kim-Schulze, S., Colicino, E., Dolios, G., Petrick, L."
date: 2026-06-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.23.734064v2.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 多组学整合框架可用于GWAS功能整合
tldr: 高维多组学数据整合常因采样变异导致发现不可重复。本文提出稳定性驱动框架，融合稀疏广义典型相关分析与重复交叉验证，系统性评估组件与特征稳定性。在甲状腺癌队列中识别出可重复的代谢组和蛋白质组潜在成分，具有一致的样本外疾病关联。该框架提高了多组学生物推断的稳健性，具有普适价值。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有高维多组学整合方法对结果可重复性评估不足，影响生物推断的稳健性。
method: 结合稀疏广义典型相关分析、重复交叉验证和样本外投影，评估组件级和特征级稳定性。
result: 在甲状腺癌队列中识别出可重复的代谢组与蛋白质组潜在成分，具有一致疾病关联和时间结构变化。
conclusion: 提出通用策略以识别可重复潜在结构，提高多组学生物推断的稳健性。
---

## 摘要
高维多组学数据整合为表征复杂生物系统提供了新的机遇。然而，由于采样变异性经常会影响研究结果的可重复性，特别是在小样本队列中，所推导出的潜在结构的可重复性和推广性往往评估不足。我们提出了一种基于稳定性的多组学整合框架，该框架将稀疏广义典型相关分析与重复交叉验证、样本外投影以及组分水平和特征水平稳定性的系统评估相结合。我们将此框架应用于一项甲状腺癌病例对照队列（n=162）的非靶向代谢组学和Olink靶向炎症蛋白质组学数据。我们的基于稳定性的整合识别出了可重复的代谢组学和蛋白质组学潜在成分，这些成分在样本外也显示出一致的疾病关联，并追踪了与诊断时间相关的时相结构变化。该框架为提高多组学研究中生物学推断的稳健性提供了可推广的策略。

## Abstract
High-dimensional multi-omics data integration offers novel opportunities to characterize complex biological systems. Even though sampling variability frequently compromises findings, particularly in small cohorts, the reproducibility and generalizability of the derived latent structures are insufficiently evaluated. We propose a Stability-driven framework for multi-omics integration that combines sparse generalized canonical correlation analysis with repeated cross-validation, out-of-sample projection, and systematic evaluation of both component-level and feature-level stability. We apply this framework to untargeted metabolomic and Olink targeted inflammation proteomic profiles in a thyroid cancer case-control cohort (n = 162). Our Stability-driven integration identified reproducible metabolomic and proteomic latent components that showed consistent out-of-sample disease associations and tracked temporally structured changes relative to time to diagnosis. The proposed framework provides a generalizable strategy for identifying reproducible latent structures that improve robustness of biological inference in multi-omics studies.