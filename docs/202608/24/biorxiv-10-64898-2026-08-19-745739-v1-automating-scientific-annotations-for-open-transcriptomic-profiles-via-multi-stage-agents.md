---
title: Automating scientific annotations for open transcriptomic profiles via multi-stage agents
title_zh: 通过多阶段代理实现开放转录组谱的自动化科学注释
authors: "Zhang, X., Paithankar, S., Pu, J., Murtaza, M. S., Shankar, R., Leshchiner, D., Koirala, S., Palmer, Z., Nault, R., Li, X., Xie, Y., Chen, B."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.19.745739v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 基于大语言模型的多阶段智能体自动化GEO转录组元数据标注
tldr: 公共转录组数据库（如GEO）的元数据异构且不一致，关键信息散落于研究级和样本级记录，阻碍大规模数据重用。为此提出GEOMeta，一种基于大型语言模型的多阶段代理工作流，将元数据整理拆分为检索、信息提取、字段标准化、本体映射和质量控制等专属步骤。应用该方法为约60万个人类bulk RNA-seq样本生成标准化注释，并前瞻性注释新研究、评估22个前沿LLM。开源Flash模型在质量上媲美顶级推理模型，成本降低一个数量级，为元数据整理提供了可扩展且可复现的框架。
source: biorxiv
selection_source: fresh_fetch
motivation: GEO等公共转录组库的元数据异构且不一致，关键信息分散，阻碍大规模数据重用，需要自动化整理方案。
method: 提出GEOMeta，一种基于LLM的多阶段代理工作流，分离检索、提取、标准化、本体映射和质量控制步骤。
result: 为约60万个人类bulk RNA-seq样本生成标准化注释；评估显示开源Flash模型质量媲美顶级推理模型，成本降低一个数量级。
conclusion: GEOMeta提供可扩展且可复现的元数据整理框架，助力公共转录组数据的大规模重用。
---

## 摘要
公共转录组存储库包含数百万个样本，然而其大规模复用受到异构且报告不一致的元数据的阻碍。在基因表达综合数据库（GEO）中，关键的生物学信息通常分布在研究级和样本级记录中，需要依赖上下文的解读。我们在此提出GEOMeta，一个基于大语言模型（LLM）的多阶段工作流程，配备任务专用代理，用于自动化GEO元数据整理。该流程将元数据检索、任务特定信息提取、字段标准化、本体映射和质量控制分开。利用GEOMeta，我们为约60万个人类批量RNA-seq样本生成了标准化注释。为展示其实用性，我们评测了基于转录组嵌入预测性别、年龄、组织和疾病的转录组表示模型。我们进一步前瞻性地注释了新提交的GEO研究，并评估了22个前沿大语言模型。最新的开源Flash模型实现了与领先推理模型相当的注释质量，同时将成本降低了一个数量级。GEOMeta为元数据整理提供了可扩展的资源和可复现的框架。

## Abstract
Public transcriptomic repositories contain millions of samples, yet their large-scale reuse is hindered by heterogeneous and inconsistently reported metadata. In the Gene Expression Omnibus (GEO), key biological information is often distributed across study- and sample-level records, requiring context-dependent interpretation. Here we present GEOMeta, a large language model (LLM)-based multi-stage workflow with task-specialized agents for automated GEO metadata curation. The pipeline separates metadata retrieval, task-specific information extraction, field standardization, ontology mapping and quality control. Using GEOMeta, we generated standardized annotations for approximately 600,000 human bulk RNA-seq samples. To demonstrate its utility, we benchmarked transcriptome representation models for predicting sex, age, tissue and disease from transcriptome embeddings. We further prospectively annotated newly submitted GEO studies and evaluated 22 frontier LLMs. Recent open-source Flash models achieved annotation quality comparable to leading reasoning models while reducing costs by an order of magnitude. GEOMeta provides a scalable resource and reproducible framework for metadata curation.