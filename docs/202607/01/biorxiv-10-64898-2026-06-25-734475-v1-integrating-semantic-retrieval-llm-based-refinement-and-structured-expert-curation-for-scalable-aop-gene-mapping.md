---
title: "Integrating Semantic Retrieval, LLM-based Refinement, and Structured Expert Curation for Scalable AOP Gene Mapping"
title_zh: 整合语义检索、基于大语言模型的精炼和结构化专家整理的可扩展AOP基因映射
authors: "Schaffert, A., Fratello, M., Kangas, K., Torres Maia, M., del Giudice, G., Mobus, L., Accardi, C., Al-Abdulraheem, Z., Campini, L., Galardo, F., Federico, A., Ciancaleoni, G., Juppi, H.-K., Paparella, M., Serra, A., Greco, D."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.25.734475v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: LLM辅助的毒理基因组学基因映射工作流
tldr: 毒理基因组学在监管毒理学中应用受限，因难以将分子反应机械地映射至AOP关键事件。本研究提出AI辅助多步工作流：利用嵌入语义检索识别候选通路，大语言模型精炼筛选，双独立专家策展及规则整合生成最终映射。在AOP-Wiki上实现覆盖523个AOP、1254个KE、15833个人类基因的映射资源，性能较以往NLP方法显著提升。该资源提供可追踪的置信度分数和策展理由，为毒理基因组学与AOP的桥接提供可扩展、可更新的支持。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有毒理基因组学映射方法难以规模化且依赖人工，需要将分子特征高效准确地关联到AOP关键事件。
method: 采用嵌入语义检索候选术语，LLM精炼筛选，双独立专家策展并基于规则整合，分配策展理由代码和置信度。
result: 在AOP-Wiki上产出覆盖523个AOP、1254个KE、15833个人类基因的映射资源，性能优于先前NLP方法。
conclusion: 该工作流和资源为毒理基因组学与AOP的整合提供了可扩展、可更新的桥梁，支持置信度感知的机制解释。
---

## 摘要
毒理基因组学可以支持监管毒理学，但其应用受到将分子反应转化为机制性、决策相关解释的难度限制。不良结局通路（AOP）为此转化提供了框架，然而组学应用需要将关键事件（KE）可扩展地映射到分子特征上。本文提出了一种AI辅助的多步骤KE-to-基因映射工作流程，该流程使用基于嵌入的语义检索来识别候选本体/通路术语，利用大语言模型辅助精炼来筛选这些候选，并通过双独立专家组整理结合基于规则的整合来最终确定映射并推导置信度评分。与早期基于NLP的方法相比，该工作流程提高了KE-to-本体/通路的映射性能，生成的候选注释与专家判断更一致，同时大幅减少了手动扩充的需求。KE标题中显式的基因和蛋白质提及被进一步锚定以提高特异性，每个整理后的映射分配了整理者原因代码，以支持透明、可追溯且具有置信度感知的重复使用。该工作流程应用于AOP-Wiki，生成了一个涵盖523个AOP中1254个KE、连接15833个人类基因的综合性KE-to-基因集资源。通过基于CTD的参考化学基团AOP指纹分析展示了其实用性，突出了在AOP背景下化学相关基因特征覆盖范围的扩展和置信度感知的解释。该工作流程及其生成的资源为毒理基因组学和基于AOP的机制解释之间架起了实用的桥梁，并支持常规更新以及未来扩展至OECD Omics2AOP中额外的组学层面。

## Abstract
Toxicogenomics can support regulatory toxicology, but its use is limited by the difficulty of translating molecular responses into mechanistic, decision-relevant interpretations. Adverse Outcome Pathways (AOPs) provide a framework for this translation, yet omics applications require scalable mapping of Key Events (KEs) to molecular features. Here, we present an AI-assisted, multi-step workflow for KE-to-gene mapping that uses embedding-based semantic retrieval to identify candidate ontology/pathway terms, large language model-assisted refinement to filter these candidates, and double-independent expert group curation with rule-based consolidation to finalize mappings and derive confidence scores. Compared with earlier NLP-based approaches, the workflow improves KE-to-ontology/pathway mapping performance and generates candidate annotations that better align with expert judgment while substantially reducing the need for manual augmentation. Explicit gene and protein mentions in KE titles were additionally grounded to improve specificity, and each curated mapping was assigned curator reason codes to support transparent, traceable, and confidence-aware reuse. Applied across AOP-Wiki, the workflow produced a comprehensive KE-to-gene set resource covering 1,254 KEs across 523 AOPs and linking 15,833 human genes. Utility is demonstrated through CTD-based AOP fingerprinting of curated reference chemical groups, highlighting expanded coverage and confidence-informed interpretation of chemical-associated gene signatures in an AOP context. The workflow and resulting resource provide a practical bridge between toxicogenomics and AOP-based mechanistic interpretation and support routine updating and future extension to additional omics layers within OECD Omics2AOP.