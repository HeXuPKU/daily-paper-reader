---
title: "Integrating Semantic Retrieval, LLM-based Refinement, and Structured Expert Curation for Scalable AOP Gene Mapping"
title_zh: 整合语义检索、基于大语言模型的精炼和结构化专家策展以实现可扩展的AOP基因映射
authors: "Schaffert, A., Fratello, M., Kangas, K., Torres Maia, M., del Giudice, G., Mobus, L., Accardi, C., Al-Abdulraheem, Z., Campini, L., Galardo, F., Federico, A., Ciancaleoni, G., Juppi, H.-K., Paparella, M., Serra, A., Greco, D."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.25.734475v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 基于LLM的细化流程，适用于生物医学知识提取
tldr: 毒理基因组学在监管毒理中有应用潜力，但将分子响应转化为机制决策解释困难；AOP框架提供翻译途径，但需要可扩展的KE-基因映射。本工作提出嵌入语义检索、LLM辅助精炼和双独立专家策展的工作流，通过规则整合最终确定映射并赋予置信度。该流程覆盖1254个KE（来自523个AOP）和15833个人类基因，相比以往NLP方法性能提升且更符合专家判断。生成的资源通过CTD化学组指纹分析展示覆盖和置信度信息，为毒理基因组学与AOP机制解释搭建实践桥梁。
source: biorxiv
selection_source: fresh_fetch
motivation: 毒理基因组学应用受限于分子响应到AOP机制翻译的困难，需可扩展的KE-基因映射方法。
method: 采用嵌入语义检索筛选候选，LLM精炼过滤，双独立专家策展与规则整合进行最终映射并评分。
result: 产出覆盖1254 KE（523 AOP）和15833人类基因的全面映射资源，性能优于传统NLP方法。
conclusion: 该工作流和资源桥接毒理基因组学与AOP机制解释，支持更新扩展至OECD Omics2AOP。
---

## 摘要
毒理基因组学可以支持监管毒理学，但其应用受到将分子反应转化为机制性、决策相关解释的难度的限制。不良结果通路（AOPs）为这种转化提供了框架，然而组学应用需要将关键事件（KEs）可扩展地映射到分子特征。在此，我们提出了一种AI辅助的多步骤KE到基因映射工作流，该工作流使用基于嵌入的语义检索来识别候选本体/通路术语，使用大语言模型辅助精炼来筛选这些候选，并使用双重独立专家组策展结合基于规则的整合来最终确定映射并推导置信度分数。与早期基于NLP的方法相比，该工作流提高了KE到本体/通路的映射性能，生成的候选注释更符合专家判断，同时大幅减少了手动扩充的需求。另外，KE标题中明确的基因和蛋白质提及被进一步锚定以提高特异性，每个策展映射都被分配了策展人原因代码，以支持透明、可追溯和置信度感知的复用。将该工作流应用于AOP-Wiki，生成了一个涵盖523个AOP中1254个KE并连接15833个人类基因的全面KE到基因集资源。通过基于CTD的策展参考化学组的AOP指纹识别展示了实用性，凸显了在AOP背景下化学相关基因特征的扩大覆盖和基于置信度的解释。该工作流及生成的资源为毒理基因组学和基于AOP的机制解释之间提供了实用的桥梁，并支持常规更新及未来扩展到OECD Omics2AOP中的其他组学层次。

## Abstract
Toxicogenomics can support regulatory toxicology, but its use is limited by the difficulty of translating molecular responses into mechanistic, decision-relevant interpretations. Adverse Outcome Pathways (AOPs) provide a framework for this translation, yet omics applications require scalable mapping of Key Events (KEs) to molecular features. Here, we present an AI-assisted, multi-step workflow for KE-to-gene mapping that uses embedding-based semantic retrieval to identify candidate ontology/pathway terms, large language model-assisted refinement to filter these candidates, and double-independent expert group curation with rule-based consolidation to finalize mappings and derive confidence scores. Compared with earlier NLP-based approaches, the workflow improves KE-to-ontology/pathway mapping performance and generates candidate annotations that better align with expert judgment while substantially reducing the need for manual augmentation. Explicit gene and protein mentions in KE titles were additionally grounded to improve specificity, and each curated mapping was assigned curator reason codes to support transparent, traceable, and confidence-aware reuse. Applied across AOP-Wiki, the workflow produced a comprehensive KE-to-gene set resource covering 1,254 KEs across 523 AOPs and linking 15,833 human genes. Utility is demonstrated through CTD-based AOP fingerprinting of curated reference chemical groups, highlighting expanded coverage and confidence-informed interpretation of chemical-associated gene signatures in an AOP context. The workflow and resulting resource provide a practical bridge between toxicogenomics and AOP-based mechanistic interpretation and support routine updating and future extension to additional omics layers within OECD Omics2AOP.