---
title: Automating scientific annotations for open transcriptomic profiles via multi-stage agents
title_zh: 通过多阶段智能体自动化开放转录组谱的科学注释
authors: "Zhang, X., Paithankar, S., Pu, J., Murtaza, M. S., Shankar, R., Leshchiner, D., Koirala, S., Palmer, Z., Nault, R., Li, X., Xie, Y., Chen, B."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.19.745739v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 基于大语言模型的多阶段智能体自动化基因组元数据策展
tldr: 公共转录组库GEO中样本元数据异构且报告不一，阻碍大规模数据重用。本文提出GEOMeta：基于大语言模型的多阶段智能体工作流，分离元数据检索、信息提取、字段标准化、本体映射与质控。它为近60万个人类bulk RNA-seq样本生成标准化注释，并支撑转录组表示模型的性别/年龄/组织/疾病预测基准，还前瞻性标注新增研究。GEOMeta提供了可扩展且可复现的元数据整理框架。
source: biorxiv
selection_source: fresh_fetch
motivation: GEO等公共转录组库的元数据异构且报告不一致，严重阻碍大规模数据重用。
method: 提出GEOMeta多阶段智能体工作流，将元数据检索、信息提取、字段标准化、本体映射与质控模块分离。
result: 应用于约60万个人类bulk RNA-seq样本，生成标准化注释并支撑性别/年龄/组织/疾病预测基准；还前瞻性注释了新提交GEO研究。
conclusion: GEOMeta为元数据整理提供了可扩展且可复现的框架；开源Flash模型在低成本下实现同等质量，可用于公共转录组数据重利用。
---

## 摘要
公共转录组数据库包含数百万个样本，然而其大规模复用受到异构且不一致报告的元数据的阻碍。在基因表达综合数据库（GEO）中，关键的生物学信息通常分布在研究级和样本级记录中，需要依赖上下文的解读。这里我们提出GEOMeta，一个基于大语言模型（LLM）的多阶段工作流程，具有任务专用智能体，用于自动化GEO元数据整理。该流程分离了元数据检索、特定任务信息提取、字段标准化、本体映射和质量控制。利用GEOMeta，我们为大约60万个人类批量RNA-seq样本生成了标准化注释。为了展示其效用，我们对用于从转录组嵌入预测性别、年龄、组织和疾病的转录组表示模型进行了基准测试。我们还前瞻性地注释了新提交的GEO研究，并评估了22个前沿LLM。最近的开源Flash模型实现了与领先推理模型相当的注释质量，同时成本降低了一个数量级。GEOMeta为元数据整理提供了可扩展的资源和可复现的框架。

## Abstract
Public transcriptomic repositories contain millions of samples, yet their large-scale reuse is hindered by heterogeneous and inconsistently reported metadata. In the Gene Expression Omnibus (GEO), key biological information is often distributed across study- and sample-level records, requiring context-dependent interpretation. Here we present GEOMeta, a large language model (LLM)-based multi-stage workflow with task-specialized agents for automated GEO metadata curation. The pipeline separates metadata retrieval, task-specific information extraction, field standardization, ontology mapping and quality control. Using GEOMeta, we generated standardized annotations for approximately 600,000 human bulk RNA-seq samples. To demonstrate its utility, we benchmarked transcriptome representation models for predicting sex, age, tissue and disease from transcriptome embeddings. We further prospectively annotated newly submitted GEO studies and evaluated 22 frontier LLMs. Recent open-source Flash models achieved annotation quality comparable to leading reasoning models while reducing costs by an order of magnitude. GEOMeta provides a scalable resource and reproducible framework for metadata curation.