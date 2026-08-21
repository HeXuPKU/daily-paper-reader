---
title: "scUnify: a unified framework for training and inference across multiple single-cell foundation models"
title_zh: scUnify：一个用于跨多个单细胞基础模型训练与推理的统一框架
authors: "KIM, D., Hong, A., Jeong, K., KIM, K."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.01.708392v2.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 直接涉及大规模基因组模型，为多种单细胞基础模型提供统一训练与推理框架
tldr: 单细胞基础模型在软件依赖和下游任务性能上差异大，比较与复用困难。scUnify框架在保留各模型所需处理流程的同时，将模型训练器、下游任务和适配策略解耦为可重用组件。在五个模型中复现了推理和训练流程，并扩展多种参数高效微调方法，验证了自定义任务跨模型扩展能力。该框架支持系统化比较组合，并在统一工作流中扩展自定义任务。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有单细胞基础模型在软件要求和下游性能上差异大，难以统一比较和复用。
method: 提出scUnify框架，保留各模型所需处理，将训练器、任务和适配策略模块化分离。
result: 在五个模型上复现原始流程，支持多种微调方法，并实现自定义任务跨模型扩展。
conclusion: scUnify能系统化比较异构模型组合，支持在统一工作流中扩展自定义任务。
---

## 摘要
单细胞基础模型（scFMs）在软件需求以及跨下游任务和适应策略的性能上各不相同，这给比较和重用带来了复杂性。我们提出了scUnify，一个在保留每个骨干网络所需处理流程的同时，将模型特定的训练器、下游任务和适应策略分离为可重用组件的框架。在五个scFM上，scUnify复现了原始推理和训练工作流，通过多种参数高效微调方法扩展了模型原生任务，并通过将新实现的自定义可训练任务连接到多个骨干网络和适应策略，展示了其可扩展性。总之，这些能力使研究人员能够在统一的工作流程中系统地比较这些组合，并在异质scFM之间扩展自定义任务。

## Abstract
Single-cell foundation models (scFMs) differ in software requirements and performance across downstream tasks and adaptation strategies, complicating comparison and reuse. We present scUnify, a framework that preserves each backbone's required processing while separating model-specific trainers, downstream tasks, and adaptation strategies as reusable components. Across five scFMs, scUnify reproduced original inference and training workflows, extended model-native tasks with multiple parameter-efficient fine-tuning methods, and demonstrated extensibility by connecting a newly implemented custom trainable task to multiple backbones and adaptation strategies. Together, these capabilities enable researchers to systematically compare these combinations and extend custom tasks across heterogeneous scFMs within a common workflow.