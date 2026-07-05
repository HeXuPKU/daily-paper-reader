---
title: "Integrating Semantic Retrieval, LLM-based Refinement, and Structured Expert Curation for Scalable AOP Gene Mapping"
title_zh: 整合语义检索、基于大语言模型的精细化与结构化专家审核以实现可扩展的AOP基因映射
authors: "Schaffert, A., Fratello, M., Kangas, K., Torres Maia, M., del Giudice, G., Mobus, L., Accardi, C., Al-Abdulraheem, Z., Campini, L., Galardo, F., Federico, A., Ciancaleoni, G., Juppi, H.-K., Paparella, M., Serra, A., Greco, D."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.25.734475v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 利用大语言模型进行毒理基因组学的基因映射优化
tldr: "毒理基因组学在监管毒理学中的应用受限于分子反应向机制性解释的转化困难。本文提出结合语义检索、大语言模型细化与结构化专家整理的AI辅助工作流，实现关键事件到基因的可扩展映射。该工作流在AOP-Wiki上覆盖1,254个KE与15,833个人类基因，性能优于传统NLP方法，并生成置信度评分与策展原因代码。成果为毒理基因组学与AOP机制解释搭建实用桥梁，支持常规更新与未来扩展。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有NLP方法难以高效且准确地为AOP关键事件映射基因，需大量人工补充，阻碍了毒理基因组学的应用。
method: 采用嵌入语义检索筛选候选本体/通路，结合LLM细化过滤，再经双独立专家组整理与规则合并，生成映射及置信度评分。
result: "在AOP-Wiki上实现1,254个KE到15,833个人类基因的映射，性能较先前NLP方法提升，更符合专家判断。"
conclusion: 该工作流提供了可扩展、透明且置信度感知的KE-基因映射资源，促进了毒理基因组学与AOP机制解释的融合。
---

## 摘要
毒理基因组学可以支持监管毒理学，但其应用受到将分子反应转化为机制性、与决策相关的解释的困难所限制。 adverse outcome pathways (AOPs) 为这种转化提供了框架，然而组学应用需要将关键事件 (KEs) 可扩展地映射到分子特征。在此，我们提出一个AI辅助的多步骤工作流程，用于KE-基因映射，该流程使用基于嵌入的语义检索来识别候选本体/通路术语，借助大语言模型辅助的精细化来筛选这些候选，并通过双独立专家组审核与基于规则的整合来最终确定映射并推导出置信度分数。与早期的基于NLP的方法相比，该工作流程提高了KE到本体/通路的映射性能，生成的候选注释更符合专家判断，同时大幅减少了手动增强的需求。此外，还对KE标题中显式的基因和蛋白质提及进行了锚定以提高特异性，并为每个经过审核的映射分配了审核者理由代码，以支持透明、可追溯且具有置信度意识的复用。将该工作流程应用于AOP-Wiki，产生了一个全面的KE-基因集资源，涵盖了523个AOP中的1,254个KE，并连接了15,833个人类基因。通过基于CTD的AOP指纹图谱对精选参考化学基团进行验证，展示了该资源的实用性，突显了在AOP背景下化学相关基因特征覆盖范围的扩大以及基于置信度的解释。该工作流程及生成的资源为毒理基因组学与基于AOP的机制解释之间架起了实用的桥梁，并支持常规更新以及未来扩展到OECD Omics2AOP中的其他组学层面。

## Abstract
Toxicogenomics can support regulatory toxicology, but its use is limited by the difficulty of translating molecular responses into mechanistic, decision-relevant interpretations. Adverse Outcome Pathways (AOPs) provide a framework for this translation, yet omics applications require scalable mapping of Key Events (KEs) to molecular features. Here, we present an AI-assisted, multi-step workflow for KE-to-gene mapping that uses embedding-based semantic retrieval to identify candidate ontology/pathway terms, large language model-assisted refinement to filter these candidates, and double-independent expert group curation with rule-based consolidation to finalize mappings and derive confidence scores. Compared with earlier NLP-based approaches, the workflow improves KE-to-ontology/pathway mapping performance and generates candidate annotations that better align with expert judgment while substantially reducing the need for manual augmentation. Explicit gene and protein mentions in KE titles were additionally grounded to improve specificity, and each curated mapping was assigned curator reason codes to support transparent, traceable, and confidence-aware reuse. Applied across AOP-Wiki, the workflow produced a comprehensive KE-to-gene set resource covering 1,254 KEs across 523 AOPs and linking 15,833 human genes. Utility is demonstrated through CTD-based AOP fingerprinting of curated reference chemical groups, highlighting expanded coverage and confidence-informed interpretation of chemical-associated gene signatures in an AOP context. The workflow and resulting resource provide a practical bridge between toxicogenomics and AOP-based mechanistic interpretation and support routine updating and future extension to additional omics layers within OECD Omics2AOP.