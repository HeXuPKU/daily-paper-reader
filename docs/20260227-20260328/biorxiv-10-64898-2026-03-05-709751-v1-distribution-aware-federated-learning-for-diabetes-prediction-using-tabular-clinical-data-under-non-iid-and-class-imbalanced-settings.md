---
title: Distribution-Aware Federated Learning for Diabetes Prediction Using Tabular Clinical Data Under Non-IID and Class-Imbalanced Settings
title_zh: 针对非独立同分布和类别不平衡设置下使用表格临床数据进行糖尿病预测的分布感知联邦学习
authors: "Amin, R., Rana, M. M. H., Aktar, S."
date: 2026-03-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.05.709751v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 使用临床数据进行糖尿病预测的联邦学习
tldr: 针对联邦学习在糖尿病预测中面临的非独立同分布（Non-IID）和类别不平衡挑战，本文提出了一种分布感知联邦学习（DA-FL）框架。该方法通过引入少数类放大因子并结合类别加权交叉熵损失，在不共享原始数据的前提下优化全局模型聚合权重。实验表明，DA-FL显著提升了模型在不平衡临床数据下的预测性能和稳定性。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-05-709751-v1/fig-001.webp\", \"caption\": \"Fig. 1 DA-FL System Architecture for Distribution-Aware Federated Learning for Clinical Diabetes Prediction\", \"page\": 6, \"index\": 1, \"width\": 854, \"height\": 442}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-05-709751-v1/fig-002.webp\", \"caption\": \"Fig. 4 Performance Comparison Across Non-IID Severity Levels.\", \"page\": 15, \"index\": 2, \"width\": 775, \"height\": 265}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-05-709751-v1/fig-003.webp\", \"caption\": \"Fig. 2 Client-wise Positive Rate (%) Across Non-IID Levels.\", \"page\": 10, \"index\": 3, \"width\": 623, \"height\": 406}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-05-709751-v1/fig-004.webp\", \"caption\": \"Table 3 Performance Comparison Across Non-IID Severity Levels (Round 30)\", \"page\": 14, \"index\": 4, \"width\": 677, \"height\": 247}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-05-709751-v1/fig-005.webp\", \"caption\": \"Fig. 3 Convergence Behavior of FL Methods Under Non-IID and Class-Imbalanced Conditions(K=5 Clients, T=30 Rounds).\", \"page\": 14, \"index\": 5, \"width\": 777, \"height\": 267}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-05-709751-v1/fig-006.webp\", \"caption\": \"Table 2 Training Stability Analysis Across 30 Communication Rounds (α = 0.5)\", \"page\": 13, \"index\": 6, \"width\": 548, \"height\": 227}]"
motivation: 传统的联邦学习聚合策略仅根据数据集大小加权，忽略了医疗机构间严重的类别分布差异，导致模型偏向多数类。
method: 提出DA-FL框架，利用局部与全局正类率之比计算少数类放大因子，并结合客户端的类别加权损失函数进行双层修正。
result: "在CDC糖尿病数据集上的实验显示，DA-FL在F1-Macro和G-Mean指标上分别比FedAvg提升了18.2%和26.7%，且稳定性提升了31倍。"
conclusion: DA-FL为现实中存在非独立同分布和类别不平衡问题的联邦临床预测提供了一种高效且易于部署的解决方案。
---

## 摘要
联邦学习（FL）能够在不进行集中式数据共享的情况下实现协作式临床模型训练，但其部署受到统计异质性（非独立同分布数据，non-IID）以及医疗机构间固有类别不平衡的阻碍。传统的聚合策略（如 FedAvg 和 FedProx）仅根据数据集大小对客户端更新进行加权，忽略了类别分布，从而导致全局模型向多数类倾斜。为解决这一问题，我们提出了分布感知联邦学习（DA-FL），它引入了一个少数类放大因子 φ_k，该因子计算为客户端本地正类率与全局正类率的比值。结合客户端层面的类别加权交叉熵损失，DA-FL 形成了一种两级修正机制，在不增加额外数据共享的情况下缓解了不平衡问题。在 CDC BRFSS 2021 糖尿病数据集（包含 5 个模拟客户端、3 种 non-IID 水平下的 236,378 条记录）上的实验表明，在适度 non-IID 条件下，DA-FL 相比 FedAvg 将 F1-Macro 提高了 18.2%，G-Mean 提高了 26.7%，同时在 30 轮通信中实现了 31 倍的 F1-Macro 稳定性提升。这些研究结果表明，DA-FL 是现实 non-IID 和类别不平衡设置下联邦临床预测的一种有效且具有实际部署价值的解决方案。

## Abstract
Federated learning (FL) enables collaborative clinical model training without centralized data sharing, yet its deployment is hindered by statistical heterogeneity (non-IID data) and inherent class imbalance across healthcare institutions. Conventional aggregation strategies such as FedAvg and FedProx weight client updates solely by dataset size, ignoring class distributions and thereby biasing the global model toward the majority class. To address this, we propose Distribution-Aware Federated Learning (DA-FL), which introduces a minority-class amplification factor{phi} k computed as the ratio of a clients local positive class rate to the global positive class rate. Combined with class-weighted cross-entropy loss at the client level, DA-FL forms a two-level correction mechanism that mitigates imbalance without additional data sharing. Experiments on the CDC BRFSS 2021 diabetes dataset (236,378 records across five simulated clients under three non-IID levels) show that DA-FL improves F1-Macro by 18.2% and G-Mean by 26.7% over FedAvg under moderate non-IID conditions, while achieving 31-fold greater F1-Macro stability across 30 communication rounds. These findings demonstrate that DA-FL is an effective and practically deployable solution for federated clinical prediction under realistic non-IID and class-imbalanced settings.