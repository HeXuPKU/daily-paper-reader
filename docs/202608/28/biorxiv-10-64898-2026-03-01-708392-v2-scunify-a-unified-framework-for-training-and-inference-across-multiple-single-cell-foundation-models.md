---
title: "scUnify: a unified framework for training and inference across multiple single-cell foundation models"
title_zh: scUnify：一个用于跨多个单细胞基础模型训练和推理的统一框架
authors: "KIM, D., Hong, A., Jeong, K., KIM, K."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.01.708392v2.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 统一单细胞基础模型的训练与推理，支撑大规模基因组模型
tldr: 单细胞基础模型在软件要求和功能上各异，限制其比较与复用。scUnify将模型专属处理、下游任务和适应策略解耦为可复用组件，在统一工作流中支持多模型训练与推理。在五个模型上复现了原始流程，集成多种参数高效微调，并可将自定义任务灵活对接不同骨干。该框架促进异质单细胞模型的系统比较与功能扩展。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有单细胞基础模型软件要求和性能千差万别，导致比较与复用困难。
method: 提出scUnify框架，将模型专属训练器、下游任务与适应策略分离为独立组件，保留各骨干必要处理。
result: 在五个scFM上复现推理与训练，集成多种参数高效微调，并能将自定义任务接入不同骨干。
conclusion: scUnify提供统一工作流，实现异质单细胞基础模型的系统比较与自定义任务扩展。
---

## 摘要
单细胞基础模型（scFMs）在软件要求以及跨下游任务和适应策略的性能上各不相同，这使比较和复用变得复杂。我们提出了scUnify，一个保留每个骨干网络所需处理流程、同时将模型特定的训练器、下游任务和适应策略拆分为可复用组件的框架。在五个scFM上，scUnify复现了原始推理和训练工作流，通过多种参数高效微调方法扩展了模型原生任务，并通过将新实现的自定义可训练任务连接到多个骨干网络和适应策略展示了其可扩展性。总之，这些能力使研究人员能够在统一工作流中系统地比较这些组合，并在异构scFM之间扩展自定义任务。

## Abstract
Single-cell foundation models (scFMs) differ in software requirements and performance across downstream tasks and adaptation strategies, complicating comparison and reuse. We present scUnify, a framework that preserves each backbone's required processing while separating model-specific trainers, downstream tasks, and adaptation strategies as reusable components. Across five scFMs, scUnify reproduced original inference and training workflows, extended model-native tasks with multiple parameter-efficient fine-tuning methods, and demonstrated extensibility by connecting a newly implemented custom trainable task to multiple backbones and adaptation strategies. Together, these capabilities enable researchers to systematically compare these combinations and extend custom tasks across heterogeneous scFMs within a common workflow.