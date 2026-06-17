---
title: "Predicted Effector Gene Aggregation, Standards and Unified Schema (PEGASUS): A Community Framework for Effector Gene Reporting"
title_zh: 预测效应基因聚合、标准与统一模式（PEGASUS）：效应基因报告的社区框架
authors: "McMahon, A., Ji, Y., Costanzo, M., Butterworth, A. S., Pahl, M., Szyszkowski, S., Heilbron, K., Shiyanbola, A., Tsepilov, Y. A., Spracklen, C. N., Hite, D., Shilin, A., PEG Working Group,, Parkinson, H. E., Burtt, N. P., Harris, L. W."
date: 2026-06-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.16.731894v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 针对GWAS预测效应基因报告的社区框架
tldr: GWAS报告预测效应基因（PEG）时方法、证据和格式各异，缺乏互操作性和FAIR合规。PEGASUS框架由社区共同制定，规定了元数据标准、结构化证据矩阵和简洁PEG列表，平衡透明度与提交负担。该框架提升了PEG报告的可比性、可重复性和可复用性，支持跨研究比较和方法基准测试。数据可通过PEG Data Registry共享，便于整合下游资源。
source: biorxiv
selection_source: fresh_fetch
motivation: GWAS中预测效应基因（PEG）报告缺乏统一标准，导致列表间难以比较、复用和基准测试，需建立社区共识框架。
method: 通过2024年研讨会和2025年工作组，多利益相关者共同开发PEGASUS框架，包含元数据、证据矩阵和PEG列表三层结构。
result: PEGASUS框架提供了首个社区标准，实现PEG报告的可比性、机器可读性和FAIR合规，并通过平台促进数据共享。
conclusion: PEGASUS是首个社区驱动的效应基因报告规范，将提升GWAS后研究的可靠性与整合效率。
---

## 摘要
全基因组关联研究（GWAS）越来越多地报告预测效应基因（PEGs）——即假设介导相关变异生物学效应的基因。这些基因是推进变异到功能研究、机制理解和治疗发现的关键输出。然而，PEG列表的快速增长并未被组织、注释和报告这些预测的标准所匹配。如最近的景观分析所示，PEG列表在方法、证据定义、命名法、来源追踪和数据结构方面差异很大，限制了互操作性、基准测试、重用以及FAIR原则的遵从。为填补这一空白，我们召集了一个国际多利益相关者社区，包括方法开发者、数据生成者、资源维护者、策展人、资助者、期刊编辑和下游用户。通过2024年的研讨会和2025年的工作组系列，我们开发了预测效应基因聚合、标准与统一模式（PEGASUS）框架。PEGASUS规定了：(i) 元数据标准，用于捕获来源、性状和GWAS描述符、证据来源和整合方法；(ii) 结构化证据矩阵，报告所有基因和每个位点优先排序所依据的所有证据；(iii) 简洁的PEG列表，总结作者优先排序的基因，并透明地链接到底层证据。该框架平衡了透明度、机器可读性、提交者的负担以及与现有社区标准的一致性。PEGASUS提供了首个社区开发的模式，用于报告预测效应基因及其支持证据。作者采用此框架将提高PEG输出的可比性、可重复性和可重用性，促进更稳健的生物学推断，实现跨资源的基因优先排序方法比较以支持社区基准测试，并整合到下游资源和分析流程中。符合PEGASUS的数据可通过PEG数据注册平台（https://kpndataregistry.org/peg）共享，促进重用并为未来与公开共享的GWAS数据整合奠定基础。

## Abstract
Genome-wide association studies (GWAS) increasingly report predicted effector genes (PEGs) - genes hypothesised to mediate the biological effects of associated variants. These function as key outputs for advancing variant-to-function research, mechanistic understanding, and therapeutic discovery. However, the rapid growth of PEG lists has not been matched by standards for organising, annotating, and reporting these predictions. As shown by recent landscape analyses, PEG lists vary widely in methodology, evidence definition, nomenclature, provenance tracking, and data structure, limiting interoperability, benchmarking, reuse, and adherence to FAIR principles. To address this gap, we convened an international multi-stakeholder community comprising method developers, data generators, resource maintainers, curators, funders, journal editors, and downstream users. Through a 2024 workshop and a 2025 working group series, we developed the Predicted Effector Gene Aggregation, Standards and Unified Schema (PEGASUS) framework. PEGASUS specifies (i) a metadata standard to capture provenance, trait and GWAS descriptors, evidence sources, and integration methods; (ii) a structured evidence matrix reporting all genes and all evidence underpinning prioritisation at each locus; and (iii) a concise PEG list that summarises author-prioritised genes linked transparently to underlying evidence. The framework balances transparency, machine readability, burden on submitters, and alignment with existing community standards. PEGASUS provides the first community-developed schema for reporting predicted effector genes and their supporting evidence. Adoption of this framework by authors will improve the comparability, reproducibility, and reusability of PEG outputs across studies, facilitating more robust biological inference, enabling cross-resource comparison of gene-prioritisation methods to support community benchmarking, and integration into downstream resources and analytical pipelines. PEGASUS-compliant data can be shared via the PEG Data Registry platform (https://kpndataregistry.org/peg), promoting re-use and establishing the basis for future integration with publicly shared GWAS data.