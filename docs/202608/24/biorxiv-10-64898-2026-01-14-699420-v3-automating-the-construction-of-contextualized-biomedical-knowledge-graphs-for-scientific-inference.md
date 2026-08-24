---
title: Automating the Construction of Contextualized Biomedical Knowledge Graphs for Scientific Inference
title_zh: 自动化构建用于科学推断的语境化生物医学知识图谱
authors: "Zheng, Y., Liu, W., Zeng, B., Feng, Y., Du, X., Zhou, L., Li, Y."
date: 2026-08-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.14.699420v3.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 情境化生物医学知识图谱构建框架，可用于GWAS位点的功能注释与机制推断
tldr: 生物医学相互作用往往随生理状态动态变化甚至逆转，但现有抽取方法将其简化为上下文无关的二元关联，导致语义丢失和矛盾证据。为此，AutoBioKG利用复合三元组同时编码环境条件、实体属性与核心关系，并基于BioOpenIE训练开放信息抽取模型，通过自训练利用未标注文献提升泛化。在DDI、ChemProt、BioRED上零样本F1超过最强基线3.6-17.8个百分点，在BioASQ问答中处理细粒度问题也明显更优。该工作为大规模构建上下文感知的生物医学知识图谱提供了可行方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有生物医学关系抽取忽略生理状态等上下文，将动态交互简化为静态二元关联，导致语义丢失与矛盾证据。
method: AutoBioKG采用复合三元组编码环境与属性，基于BioOpenIE训练开放抽取模型，并利用自训练伪标签优化泛化。
result: 在DDI、ChemProt、BioRED上零样本F1领先最强基线3.6-17.8个百分点，BioASQ问答中优于现有知识图谱方法。
conclusion: 该框架将非结构化文献转化为上下文感知知识图谱，为生物医学科学推理提供可扩展支撑。
---

## 摘要
生物医学相互作用本质上是动态的，常常在特定生理状态下发生转变甚至逆转。然而，现有的提取方法将这些复杂机制简化为与语境无关的二元关联，导致语义损失和相互矛盾的证据。在此，我们提出了AutoBioKG，一个端到端框架，通过利用复合三元组在核心关系之外编码环境条件和实体属性，从而构建上下文感知的知识图谱。该框架由在BioOpenIE上训练并通过对未标记文献的伪标签进行自训练进一步精炼的开放信息提取模型驱动，展现出广泛的泛化能力。值得注意的是，AutoBioKG在DDI、ChemProt和BioRED上取得了最高的零样本F1分数，在每项基准测试上比最佳基线高出3.6至17.8个百分点。此外，在BioASQ生物医学问答评估中，AutoBioKG生成的图谱在是/否、事实型和列表型问题上优于现有方法，尤其是在需要细粒度上下文信息的查询上。综上所述，这些结果支持AutoBioKG作为一个可扩展的框架，用于将非结构化文献转化为结构化的、上下文感知的生物医学知识。

## Abstract
Biomedical interactions are inherently dynamic, often shifting or even reversing under specific physiological states. However, existing extraction methods simplify these complex mechanisms into context-agnostic binary associations, resulting in semantic loss and contradictory evidence. Here, we present AutoBioKG, an end-to-end framework that constructs context-aware knowledge graphs by leveraging composite triples to encode environmental conditions and entity attributes alongside core relationships. Powered by an open information extraction model trained on BioOpenIE and further refined through self-training with pseudo-labels from unlabeled literature, the framework exhibits broad generalization. Notably, AutoBioKG achieved the highest zero-shot F1 across DDI, ChemProt, and BioRED, outperforming the best-performing baseline on each benchmark by 3.6-17.8 percentage points. Furthermore, AutoBioKG-derived graphs outperformed existing approaches on yes/no, factoid, and list questions in the BioASQ biomedical question-answering evaluation, particularly for queries requiring fine-grained contextual information. Together, these results support AutoBioKG as a scalable framework for transforming unstructured literature into structured, context-aware biomedical knowledge.