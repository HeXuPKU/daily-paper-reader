---
title: Automating Biomedical Knowledge Graph Construction For Context-Aware Scientific Inference
title_zh: 自动化构建上下文感知的生物医学知识图谱以支持科学推断
authors: "Zheng, Y., Liu, W., Zeng, B., Feng, Y., Du, X., Zhou, L., Li, Y."
date: 2026-08-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.14.699420v4.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 基于大语言模型构建上下文感知生物医学知识图谱的端到端框架
tldr: 现有生物医学信息抽取将动态机制简化为无上下文二元关联，造成语义损失。AutoBioKG用复合三元组编码环境条件与属性，基于开放信息抽取和自训练构建上下文感知知识图谱，在零样本基准上超越基线3.6-17.8个百分点，并提升BioASQ问答效果。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有抽取方法忽略生物医学交互的动态性，将复杂机制简化为无上下文二元关联，导致语义丢失。
method: 利用开放信息抽取模型提取复合三元组，融合环境条件与实体属性，并通过自我训练优化泛化能力。
result: 在DDI、ChemProt、BioRED零样本基准上取得最高F1，超过最强基线3.6-17.8个百分点。
conclusion: 将文献转换为结构化上下文感知知识图谱，为生物医学问答等下游任务提供可扩展方案。
---

## 摘要
生物医学交互本质上具有动态性，常常在特定生理状态下发生转变甚至逆转。然而，现有的抽取方法将这些复杂机制简化为与上下文无关的二元关联，导致语义损失和矛盾证据。在此，我们提出AutoBioKG，一种端到端框架，通过利用复合三元组在编码核心关系的同时编码环境条件和实体属性，构建上下文感知的知识图谱。该框架基于在BioOpenIE上训练并通过对未标注文献的伪标签进行自训练进一步优化的开放信息抽取模型，展现出广泛的泛化能力。值得注意的是，AutoBioKG在DDI、ChemProt和BioRED上取得了最高的零样本F1分数，在每项基准测试中均比表现最佳的基线高出3.6至17.8个百分点。此外，在BioASQ生物医学问答评估中，AutoBioKG生成的图谱在是/否问题、事实型问题和列表问题上的表现优于现有方法，尤其是在需要细粒度上下文信息的查询中。综合来看，这些结果支持AutoBioKG作为一种可扩展框架，用于将非结构化文献转化为结构化的、上下文感知的生物医学知识。

## Abstract
Biomedical interactions are inherently dynamic, often shifting or even reversing under specific physiological states. However, existing extraction methods simplify these complex mechanisms into context-agnostic binary associations, resulting in semantic loss and contradictory evidence. Here, we present AutoBioKG, an end-to-end framework that constructs context-aware knowledge graphs by leveraging composite triples to encode environmental conditions and entity attributes alongside core relationships. Powered by an open information extraction model trained on BioOpenIE and further refined through self-training with pseudo-labels from unlabeled literature, the framework exhibits broad generalization. Notably, AutoBioKG achieved the highest zero-shot F1 across DDI, ChemProt, and BioRED, outperforming the best-performing baseline on each benchmark by 3.6-17.8 percentage points. Furthermore, AutoBioKG-derived graphs outperformed existing approaches on yes/no, factoid, and list questions in the BioASQ biomedical question-answering evaluation, particularly for queries requiring fine-grained contextual information. Together, these results support AutoBioKG as a scalable framework for transforming unstructured literature into structured, context-aware biomedical knowledge.