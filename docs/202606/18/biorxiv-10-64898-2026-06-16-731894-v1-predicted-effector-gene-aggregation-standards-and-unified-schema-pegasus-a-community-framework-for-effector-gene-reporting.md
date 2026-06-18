---
title: "Predicted Effector Gene Aggregation, Standards and Unified Schema (PEGASUS): A Community Framework for Effector Gene Reporting"
title_zh: 预测效应基因聚合、标准与统一模式（PEGASUS）：效应基因报告的社区框架
authors: "McMahon, A., Ji, Y., Costanzo, M., Butterworth, A. S., Pahl, M., Szyszkowski, S., Heilbron, K., Shiyanbola, A., Tsepilov, Y. A., Spracklen, C. N., Hite, D., Shilin, A., PEG Working Group,, Parkinson, H. E., Burtt, N. P., Harris, L. W."
date: 2026-06-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.16.731894v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: GWAS预测效应基因的社区框架，整合功能基因组学
tldr: 全基因组关联研究（GWAS）报告预测效应基因（PEG）时缺乏统一标准，导致互操作性差、难以复用。为此，国际多利益相关方社区通过研讨会和小组工作，制定了PEGASUS框架。该框架包括元数据标准、结构化证据矩阵和简明PEG列表，平衡透明度与机器可读性。该框架为PEG报告提供了首个社区模式，有望提升不同研究间PEG输出的可比性、可重复性和可重用性。
source: biorxiv
selection_source: fresh_fetch
motivation: GWAS日益报告预测效应基因，但缺乏报告标准，导致列表在方法、证据定义、命名和数据结构上差异大，限制了互操作性和FAIR原则遵守。
method: 通过2024年研讨会和2025年工作组，联合方法开发者、数据生成者、维护者等多方，制定了PEGASUS框架，包含元数据标准、证据矩阵和PEG列表三部分。
result: PEGASUS指定了捕获来源、性状和证据的元数据标准，以及所有基因和证据的结构化矩阵，并生成简明PEG列表，透明链接底层证据。
conclusion: PEGASUS框架提升了PEG输出的可比性、可重复性和可重用性，支持跨资源基准测试，并可通过PEG数据注册平台共享，促进下游资源整合。
---

## 摘要
全基因组关联研究（GWAS）越来越多地报告预测效应基因（PEGs）——这些基因被假定介导相关变异的生物学效应。这些作为推进变异-功能研究、机制理解和治疗发现的关键输出。然而，PEG列表的快速增长并未伴随着组织、注释和报告这些预测的标准。正如最近的格局分析所示，PEG列表在方法、证据定义、命名法、来源追踪和数据结构方面差异很大，限制了互操作性、基准测试、重用和FAIR原则的遵守。为解决这一差距，我们召集了一个国际多利益相关者社区，包括方法开发者、数据生成者、资源维护者、策展人、资助者、期刊编辑和下游用户。通过2024年研讨会和2025年工作组系列，我们开发了预测效应基因聚合、标准与统一模式（PEGASUS）框架。PEGASUS规定了（i）元数据标准，以捕获来源、性状和GWAS描述符、证据来源和整合方法；（ii）结构化证据矩阵，报告每个位点的所有基因和所有支撑优先排序的证据；以及（iii）简洁的PEG列表，总结作者优先排序的基因，并透明地关联到底层证据。该框架平衡了透明度、机器可读性、提交者负担以及与现有社区标准的一致性。PEGASUS提供了首个社区开发的模式，用于报告预测效应基因及其支持证据。作者采用该框架将提高PEG输出在各研究之间的可比性、可重复性和可重用性，促进更可靠的生物学推断，支持基因优先排序方法的跨资源比较以进行社区基准测试，并整合到下游资源和分析流程中。符合PEGASUS的数据可通过PEG数据注册平台（https://kpndataregistry.org/peg）共享，促进重用，并为未来与公开共享的GWAS数据整合奠定基础。

## Abstract
Genome-wide association studies (GWAS) increasingly report predicted effector genes (PEGs) - genes hypothesised to mediate the biological effects of associated variants. These function as key outputs for advancing variant-to-function research, mechanistic understanding, and therapeutic discovery. However, the rapid growth of PEG lists has not been matched by standards for organising, annotating, and reporting these predictions. As shown by recent landscape analyses, PEG lists vary widely in methodology, evidence definition, nomenclature, provenance tracking, and data structure, limiting interoperability, benchmarking, reuse, and adherence to FAIR principles. To address this gap, we convened an international multi-stakeholder community comprising method developers, data generators, resource maintainers, curators, funders, journal editors, and downstream users. Through a 2024 workshop and a 2025 working group series, we developed the Predicted Effector Gene Aggregation, Standards and Unified Schema (PEGASUS) framework. PEGASUS specifies (i) a metadata standard to capture provenance, trait and GWAS descriptors, evidence sources, and integration methods; (ii) a structured evidence matrix reporting all genes and all evidence underpinning prioritisation at each locus; and (iii) a concise PEG list that summarises author-prioritised genes linked transparently to underlying evidence. The framework balances transparency, machine readability, burden on submitters, and alignment with existing community standards. PEGASUS provides the first community-developed schema for reporting predicted effector genes and their supporting evidence. Adoption of this framework by authors will improve the comparability, reproducibility, and reusability of PEG outputs across studies, facilitating more robust biological inference, enabling cross-resource comparison of gene-prioritisation methods to support community benchmarking, and integration into downstream resources and analytical pipelines. PEGASUS-compliant data can be shared via the PEG Data Registry platform (https://kpndataregistry.org/peg), promoting re-use and establishing the basis for future integration with publicly shared GWAS data.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：全基因组关联研究（GWAS）在识别与性状关联的遗传变异后，越来越多地进一步报告“预测效应基因”（Predicted Effector Genes, PEGs）——即假设介导变异生物学效应的基因。然而，不同研究在报告PEG时，在方法论、证据定义、基因命名、来源追踪以及数据结构上存在巨大差异，严重限制了不同研究之间的互操作性、基准测试、结果复用以及对FAIR（可发现、可访问、可互操作、可复用）原则的遵守。
- **整体含义**：缺乏统一的报告标准导致大量PEG数据难以整合和比较，阻碍了从GWAS到生物学机制理解、治疗靶点发现的转化进程。因此，迫切需要建立一个社区共识的报告框架，以提升PEG输出的可比性、可重复性和可重用性。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：通过多利益相关方社区（包括方法开发者、数据生成者、资源维护者、策展人、资助者、期刊编辑和下游用户）的协作，制定一个名为 **PEGASUS（Predicted Effector Gene Aggregation, Standards and Unified Schema）** 的统一报告框架。
- **关键技术细节**：
  - **元数据标准**：用于捕获来源、性状和GWAS描述符、证据来源以及整合方法。
  - **结构化证据矩阵**：在每个位点，报告所有基因以及所有用于支持优先排序的证据（如功能注释、染色质相互作用、表达数量性状位点等），形成完整的矩阵。
  - **简洁PEG列表**：总结作者优先排序的基因，并透明地链接到底层证据。
- **算法/流程**（文字说明）：
  1. 定义统一的元数据字段（如研究ID、性状名称、样本量、分析软件、p值阈值等）。
  2. 构建证据矩阵，每一行对应一个候选基因，每一列对应一种证据类型（如eQTL、Hi-C、pLoF等），单元格记录是否存在证据及其强度。
  3. 从证据矩阵中提取作者最终优先排序的基因列表，每个基因附带唯一的证据链接标识。
  4. 所有符合PEGASUS的数据通过PEG数据注册平台（https://kpndataregistry.org/peg）共享。

- 该框架平衡了透明度、机器可读性、提交者负担以及现有社区标准（如GWAS Catalog）的一致性。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **实验设计说明**：该论文并非传统意义上的算法或实验验证论文，而是社区标准制定报告。因此，没有采用标准数据集进行定量实验对比。
- **使用的数据集/场景**：作者引用了“最近的格局分析”（landscape analyses），展示了现有PEG列表在方法、证据定义、命名等方面的广泛差异。这些格局分析作为背景，而非实验。
- **Benchmark**：没有定义具体的benchmark指标。框架旨在成为未来PEG报告的基准格式。
- **对比的方法**：无；但框架通过社区协商，参考了现有资源（如GWAS Catalog、Open Targets等）的数据结构，以保持一致性。

### 4. 资源与算力

- **未提及**：论文全文未涉及任何GPU型号、数量、训练时长等计算资源信息。重点在于社区标准和元数据格式设计，不依赖大规模计算资源。

### 5. 实验数量与充分性

- **实验数量**：无传统实验。论文主要基于2024年研讨会和2025年工作组系列（多轮次、多利益相关方讨论）形成共识。属于定性过程，未进行定量消融实验或对比实验。
- **充分性评估**：框架通过国际多利益相关方社区迭代形成，成员包括方法开发者、数据生成者、资源维护者、策展人、资助者、期刊编辑、下游用户，具备较高的社区代表性。然而，框架尚未经过大规模实际数据提交流程的测试，其充分性有待后续应用验证。论文未报告任何用户试点或模拟数据测试结果。

### 6. 论文的主要结论与发现

- PEGASUS提供了**首个社区开发的、专用于报告预测效应基因及其支持证据的模式**。
- 该框架明确了三个组成部分：元数据标准、结构化证据矩阵、简洁PEG列表，平衡了透明度与机器可读性。
- 作者采用该框架将提高PEG输出在各研究之间的**可比性、可重复性和可重用性**。
- 符合PEGASUS的数据可通过公共注册平台共享，促进后续的跨资源比较、社区基准测试以及与下游资源（如基因功能数据库）整合。

### 7. 优点：方法或实验设计上的亮点

- **社区驱动**：聚集了从方法开发者到下游用户、资助者、期刊编辑的广泛利益相关方，确保框架符合实际应用场景和各方需求。
- **结构化与透明**：提出“证据矩阵”概念，将所有候选基因及其所有支撑证据以结构化方式呈现，而非仅输出最终名单，增强了结果的透明度和可审计性。
- **兼容性**：明确与现有社区标准（如GWAS Catalog）对齐，降低采纳门槛。
- **公共注册平台**：提供专门的注册平台方便数据共享，有助于形成开放科学文化。
- **FAIR原则**：框架设计直接支持数据的可发现、可访问、可互操作、可复用。

### 8. 不足与局限

- **缺乏实证验证**：框架属于规范提议，尚未经过大规模实际PEG数据提交流程的压力测试或用户满意度调查，可能在实际应用中发现兼容性或易用性问题。
- **实验覆盖不足**：没有对不同类型GWAS（如罕见变异、多基因性状、跨族群）或不同整合方法进行模拟验证，未评估框架对复杂场景（如基因间区效应、多效位点）的适应能力。
- **偏差风险**：证据来源的选择和优先排序规则的确定主要依赖社区讨论，可能存在主观性；此外，框架鼓励透明报告，但并未强制规定证据质量阈值，可能导致不同研究间仍存在主观差异。
- **应用限制**：框架主要面向常见变异GWAS，对于插入/缺失、结构变异或非编码变异的效应基因预测可能需额外扩展。同时，注册平台仍处于初期，未来可持续发展与维护需关注。
- **未提供软件工具**：论文没有附带自动化的验证工具（如schema validator、格式转换器），可能增加提交者负担。

（完）
