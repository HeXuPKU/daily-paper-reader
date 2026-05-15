---
title: A Scalable Sign-Aware Multi-Omics Knowledge Graph Foundation Model for Mechanistic Drug Action and Clinical Response Predictions
title_zh: 一种用于机制性药物作用和临床反应预测的可扩展符号感知多组学知识图谱基座模型
authors: "Mottaqi, M., Zhang, S., Adoremos, I., Zhang, P., Xie, L."
date: 2026-05-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.29.721775v2.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 用于临床反应预测的多组学知识图谱基础模型
tldr: 针对生物医学知识图谱中缺乏符号化（激活/抑制）逻辑的问题，本文提出了SIGMA-KG知识图谱和FLASH基础模型。SIGMA-KG整合了多组学与临床数据并标注了极性，而FLASH通过轻量化有符号异构图神经网络进行预训练。该模型在药物作用机制、临床反应及药物相互作用预测等任务中表现优异，并成功应用于药物重定位，具有极高的临床验证成功率。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的生物医学知识图谱多为无符号关联，忽略了分子间激活或抑制的调控逻辑，限制了药物机制预测的准确性和可解释性。
method: 开发了包含极性信息的SIGMA-KG知识图谱，并设计了基于结构平衡理论的轻量化有符号异构图神经网络FLASH进行自监督预训练。
result: "FLASH在多项下游任务中优于9种主流基准模型，并在药物重定位实验中达到了69.6%的外部临床验证成功率。"
conclusion: SIGMA-KG与FLASH框架为药物研发和临床安全评估提供了一种可扩展且具备机制推理能力的符号感知基础模型。
---

## 摘要
从机制上预测药物作用的后果需要区分分子相互作用是激活性的还是抑制性的，然而大多数生物医学知识图谱和图神经网络将生物学过程表示为无符号的关联。这种局限性模糊了调控逻辑，限制了机制可解释性，并降低了下游治疗预测的准确性。现有方法还受到化学覆盖范围有限以及跨生物尺度的分子与临床数据整合不足的进一步约束。在此，我们提出了 SIGMA-KG（符号化多组学图谱知识图谱），一个大规模符号化多组学知识图谱，以及 FLASH（快速轻量级符号异构图神经网络架构），一种用于在生物医学知识图谱上进行基座模型预训练的快速轻量级符号异构图神经网络。SIGMA-KG 整合了除已批准药物之外的化学基因组扰动，以及转录组学、蛋白质组学和临床数据，明确编码了生物学和表型效应的方向与极性。FLASH 能够在该符号图谱上进行大规模高效的自监督预训练，通过结构平衡原理学习可迁移的表示，从而保留激活和抑制效应如何在多跳生物通路中进行组合。在包括靶点特异性作用模式预测、药物诱导的临床反应建模和药物相互作用预测在内的多个下游任务中（无需特定任务的微调），预训练的 FLASH 基座模型始终优于或媲美九种最先进的无符号、关系型和符号图基准模型，同时显著提高了计算效率。我们通过可解释的归纳式药物重定向进一步展示了 FLASH 的转化效用，为四种复杂疾病识别了新的治疗候选药物，外部临床验证成功率达 69.6%。总之，SIGMA-KG 和 FLASH 为机制性潜空间推理提供了一个可扩展的符号感知框架，提升了药物研发、联合用药设计和临床安全性评估的预测准确性。

## Abstract
Mechanistically predicting the consequences of drug action requires distin-guishing whether molecular interactions are activating or inhibitory, yet most biomedical knowledge graphs and graph neural networks represent biology as unsigned associations. This limitation obscures regulatory logic, restricts mechanistic interpretability and reduces the accuracy of downstream therapeutic predictions. Existing approaches are further constrained by limited chemical coverage and insufficient integration of molecular and clinical data across biological scales. Here we present SIGMA-KG (SIGned Multi-omics Atlas Knowledge Graph), a large-scale signed multi-omics knowledge atlas, and FLASH (Fast Lightweight Architecture for Signed Heterogeneous GNN), a fast and lightweight signed heterogeneous graph neural network for foundation-model pretraining on biomedical knowledge graphs. SIGMA-KG integrates chemogenomic perturbations beyond approved drugs with transcriptomic, proteomic and clinical data, explicitly encoding the direction and polarity of biological and phenotypic effects. FLASH enables efficient self-supervised pretraining on this signed atlas at scale, learning transferable representations that preserve how activating and inhibitory effects compose across multi-hop biological pathways through structural balance principles. Across multiple downstream tasks (without task-specific fine-tuning), including target-specific mode-of-action prediction, drug-induced clinical response modeling and drug-drug interaction prediction, the pretrained FLASH foundation model consistently outperforms or matches nine state-of-the-art unsigned, relational and signed graph baselines while substantially improving computational efficiency. We further demonstrate the translational utility of FLASH through explainable inductive drug repurposing, identifying novel ther-apeutic candidates for four complex diseases with a 69.6% external clinical validation success rate. Together, SIGMA-KG and FLASH provide a scalable, sign-aware framework for mechanistic latent-space reasoning, advancing the predictive accuracy of drug discovery, polypharmacy design, and clinical safety assessment.