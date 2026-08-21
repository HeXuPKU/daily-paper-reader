---
title: Automating scientific annotations for open transcriptomic profiles via multi-stage agents
title_zh: 通过多阶段智能体自动化开放转录组谱的科学注释
authors: "Zhang, X., Paithankar, S., Pu, J., Murtaza, M. S., Shankar, R., Leshchiner, D., Koirala, S., Palmer, Z., Nault, R., Li, X., Xie, Y., Chen, B."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.19.745739v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 基于大语言模型的多阶段智能体用于GEO元数据策展
tldr: 公共转录组数据库中元数据异质且不一致，严重制约大规模数据重用。提出GEOMeta，一种基于大语言模型的多阶段智能体流程，通过检索、提取、标准化、本体映射和质控模块实现自动化元数据整理。利用该方法为约六十万个人类bulk RNA-seq样本生成了标准化注释，并发现开源Flash模型能以低一个数量级的成本取得接近前沿推理模型的注释质量。GEOMeta为处理不断增长的通量数据提供了可扩展资源与可重复框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 公共转录组数据库中元数据异质且不一致，严重阻碍样本的大规模重用。
method: 基于大语言模型的多阶段智能体流程，分步完成检索、提取、标准化、本体映射和质控。
result: 为约六十万个人类bulk RNA-seq样本生成标准化注释，并证明开源Flash模型注释质量接近前沿推理模型，成本低一个数量级。
conclusion: 该工作为公共转录组元数据整理提供了可扩展资源和可重复框架，促进数据重用。
---

## 摘要
公共转录组数据库包含数百万个样本，然而其大规模再利用受到异质且不一致报告的元数据的阻碍。在基因表达综合数据库（GEO）中，关键的生物学信息通常分布在研究级和样本级记录中，需要依赖上下文的解释。我们在此提出GEOMeta，一个基于大型语言模型（LLM）的多阶段工作流程，配备任务专业化智能体，用于自动化GEO元数据整理。该流程将元数据检索、特定任务信息提取、字段标准化、本体映射和质量控制分离开来。利用GEOMeta，我们为大约60万个人类批量RNA-seq样本生成了标准化注释。为展示其实用性，我们基准测试了转录组表示模型，用于从转录组嵌入预测性别、年龄、组织和疾病。我们进一步前瞻性地注释了新提交的GEO研究，并评估了22个前沿LLM。最近的开源Flash模型实现了与领先推理模型相当的注释质量，同时将成本降低了一个数量级。GEOMeta为元数据整理提供了可扩展的资源和可复现的框架。

## Abstract
Public transcriptomic repositories contain millions of samples, yet their large-scale reuse is hindered by heterogeneous and inconsistently reported metadata. In the Gene Expression Omnibus (GEO), key biological information is often distributed across study- and sample-level records, requiring context-dependent interpretation. Here we present GEOMeta, a large language model (LLM)-based multi-stage workflow with task-specialized agents for automated GEO metadata curation. The pipeline separates metadata retrieval, task-specific information extraction, field standardization, ontology mapping and quality control. Using GEOMeta, we generated standardized annotations for approximately 600,000 human bulk RNA-seq samples. To demonstrate its utility, we benchmarked transcriptome representation models for predicting sex, age, tissue and disease from transcriptome embeddings. We further prospectively annotated newly submitted GEO studies and evaluated 22 frontier LLMs. Recent open-source Flash models achieved annotation quality comparable to leading reasoning models while reducing costs by an order of magnitude. GEOMeta provides a scalable resource and reproducible framework for metadata curation.