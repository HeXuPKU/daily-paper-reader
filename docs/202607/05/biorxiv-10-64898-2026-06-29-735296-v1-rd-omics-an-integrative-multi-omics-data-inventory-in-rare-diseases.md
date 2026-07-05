---
title: "RD-OMICS: An Integrative Multi-Omics Data Inventory in Rare Diseases"
title_zh: RD-OMICS：罕见病整合多组学数据目录
authors: "Sun, S., Wang, H., Mathe, E. A., Zhu, Q."
date: 2026-07-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735296v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 使用大语言模型辅助整合罕见病多组学数据
tldr: 罕见病研究受限于小样本、异质性和碎片化组学数据。本文构建RD-OMICS知识图谱，通过规则映射与LLM辅助语义分类的元数据管道，整合GEO中126种罕见病的11049个系列、37万样本及1.5万平台。案例验证其支持ALS等疾病的队列构建与药物重定位。该资源为碎片化数据转化为结构化的可互操作平台奠定基础，促进罕见病转化发现。
source: biorxiv
selection_source: fresh_fetch
motivation: 罕见病组学数据分散且注释不一致，缺乏整合资源，制约跨研究分析和治疗开发。
method: 开发元数据协调管道（规则映射+LLM语义分类），构建图数据模型整合疾病、实验、样本、平台等实体。
result: "整合126种罕见病的11049个GEO系列，含375,930样本、1,578平台、10,938项目；ALS案例验证队列构建与药物重利用。"
conclusion: RD-OMICS可扩展地将碎片化组学数据转化为结构化、互操作资源，推动罕见病治疗发现。
---

## 摘要
罕见病（Rare Diseases, RD）影响美国超过3000万人，但仅有不到5%的已识别疾病拥有FDA批准的治疗方法。罕见病研究进展受限于患者队列规模小、生物学异质性高，以及公开可用的组学数据分散、注释不一致，这限制了整合分析和转化发现。本文提出RD-OMICS，这是一个数据目录，以知识图谱的形式整合了来自基因表达综合数据库（GEO）的结构化罕见病组学数据。我们开发了一个元数据协调流程，结合了基于规则的映射和大语言模型（LLM）辅助的语义分类。定义了基于图的数据模型，将疾病条件、实验、样本、平台、项目和出版物等不同类型的数据整合到集中式目录图中。在本初步研究中，处理并整合了126种罕见病的11,049个GEO系列到RD-OMICS中，包括375,930个生物样本、1,578个测序和阵列平台、10,938个生物项目。案例研究展示了RD-OMICS在支持罕见病研究、组学队列构建以及基于转录组的肌萎缩侧索硬化症（ALS）药物重定位中的应用。RD-OMICS为将分散的组学数据转化为结构化、协调且可互操作的资源提供了可扩展的基础，促进了罕见病的治疗开发和其他转化发现。

## Abstract
Rare diseases (RD) impact over 30 million individuals in the United States, yet fewer than 5% of the identified conditions have FDA-approved treatments. Progress in RD research is hindered by small patient cohorts, biological heterogeneity, and the fragmented, inconsistently annotated publicly available omics data, which limits integrative analysis and translational discovery. Here, we present RD-OMICS, a data inventory with integrated and structured RD omics data from Gene Expression Omnibus (GEO), in the form of a knowledge graph. We developed a metadata harmonization pipeline that combines rule-based mapping and large language model (LLM)-assisted semantic categorization. The graph-based data model was defined to integrate different types of data including disease conditions, experiments, samples, platforms, projects, and publications into a centralized inventory graph. In this preliminary study, 11,049 GEO series for 126 rare diseases were processed and integrated into RD-OMICS, which includes 375,930 individual biospecimen samples, 1,578 sequencing and array platforms, 10,938 biological projects. Case studies demonstrate the use of RD-OMICS in supporting rare disease research, omics cohort construction, and transcriptome-based drug repurposing for amyotrophic lateral sclerosis (ALS). RD-OMICS provides a scalable foundation for transforming fragmented omics data into a structured, harmonized and interoperable resource, facilitating therapeutic development and other translational discoveries in rare diseases.