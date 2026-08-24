---
title: "scUnify: a unified framework for training and inference across multiple single-cell foundation models"
title_zh: scUnify：一个用于跨多个单细胞基础模型训练和推理的统一框架
authors: "KIM, D., Hong, A., Jeong, K., KIM, K."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.01.708392v2.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 面向多种单细胞基础模型的统一训练推理框架，促进基因组大模型的系统比较与复用
tldr: 单细胞基础模型在软件需求、任务性能和适应策略上差异显著，导致难以比较与复用。scUnify保留各模型所需处理，将模型特定训练器、下游任务和适应策略解耦为可复用组件，构建统一框架。在五个scFM上完整复现了原始推理和训练流程，结合多种参数高效微调方法扩展原生任务，并成功接入新自定义任务。该框架支持跨模型组合的系统比较，并促进自定义任务在异构模型间扩展。
source: biorxiv
selection_source: fresh_fetch
motivation: 单细胞基础模型因软件需求与性能差异大，造成比较和复用困难，亟需统一框架。
method: 保留各基础模型处理流程，将模型专属训练器、下游任务与适应策略拆分为可复用组件。
result: 在五个单细胞基础模型上复现原工作流，用多种PEFT扩展原生任务，并接入自定义训练任务。
conclusion: 为异构scFM提供统一训练与推理工作流，支持系统比较组合与自定义任务扩展。
---

## 摘要
单细胞基础模型在软件要求以及跨下游任务和适应策略的性能上有所不同，使得比较和重用变得复杂。我们提出了scUnify，一个保留每个主干网络所需处理流程的框架，同时将模型特定的训练器、下游任务和适应策略分离为可复用组件。在五个单细胞基础模型上，scUnify复现了原始推理和训练工作流，通过多种参数高效微调方法扩展了模型原生任务，并展示了通过将新实现的自定义可训练任务连接到多个主干网络和适应策略的可扩展性。这些能力共同使研究人员能够在统一的工作流程中系统地比较这些组合，并在异质的单细胞基础模型之间扩展自定义任务。

## Abstract
Single-cell foundation models (scFMs) differ in software requirements and performance across downstream tasks and adaptation strategies, complicating comparison and reuse. We present scUnify, a framework that preserves each backbone's required processing while separating model-specific trainers, downstream tasks, and adaptation strategies as reusable components. Across five scFMs, scUnify reproduced original inference and training workflows, extended model-native tasks with multiple parameter-efficient fine-tuning methods, and demonstrated extensibility by connecting a newly implemented custom trainable task to multiple backbones and adaptation strategies. Together, these capabilities enable researchers to systematically compare these combinations and extend custom tasks across heterogeneous scFMs within a common workflow.