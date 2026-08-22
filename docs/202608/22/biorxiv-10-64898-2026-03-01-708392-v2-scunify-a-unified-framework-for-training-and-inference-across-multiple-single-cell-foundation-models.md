---
title: "scUnify: a unified framework for training and inference across multiple single-cell foundation models"
title_zh: scUnify：一个用于跨多个单细胞基础模型进行训练与推理的统一框架
authors: "KIM, D., Hong, A., Jeong, K., KIM, K."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.01.708392v2.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 单细胞基础模型的统一框架，与大规模基因组模型相关
tldr: 单细胞基础模型在软件需求、下游任务表现和适配策略上差异大，难以比较和复用。scUnify提出统一框架，保留各骨干模型的必要处理流程，将模型专属训练器、下游任务和适配策略解耦为可复用组件。在五个模型上复现推理与训练流程，并扩展多种参数高效微调方法，能将新任务连接到多个骨干和适配策略，支持系统性比较与扩展。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有单细胞基础模型在软件依赖和性能上差异大，导致比较和复用困难。
method: scUnify将模型专属训练器、下游任务和适配策略分离为可复用组件，保留各骨干必要处理流程。
result: 在五个scFM上复现原生流程，支持多种微调方法，并可连接自定义训练任务到多个骨干和策略。
conclusion: 该框架支持异质模型统一工作流，便于系统比较和扩展自定义任务。
---

## 摘要
单细胞基础模型（scFMs）在软件需求以及跨下游任务和适应性策略的性能上各不相同，这使得比较和复用变得复杂。我们提出了scUnify，这是一个保留每个骨干网络所需处理流程、同时将特定于模型的训练器、下游任务和适应性策略分离为可复用组件的框架。在五个scFM上，scUnify复现了原始推理和训练工作流，通过多种参数高效微调方法扩展了模型原生任务，并通过将新实现的可定制训练任务连接到多个骨干网络和适应性策略展示了可扩展性。总体而言，这些能力使研究者能够在统一工作流中系统地比较这些组合，并在异构scFM之间扩展定制任务。

## Abstract
Single-cell foundation models (scFMs) differ in software requirements and performance across downstream tasks and adaptation strategies, complicating comparison and reuse. We present scUnify, a framework that preserves each backbone's required processing while separating model-specific trainers, downstream tasks, and adaptation strategies as reusable components. Across five scFMs, scUnify reproduced original inference and training workflows, extended model-native tasks with multiple parameter-efficient fine-tuning methods, and demonstrated extensibility by connecting a newly implemented custom trainable task to multiple backbones and adaptation strategies. Together, these capabilities enable researchers to systematically compare these combinations and extend custom tasks across heterogeneous scFMs within a common workflow.