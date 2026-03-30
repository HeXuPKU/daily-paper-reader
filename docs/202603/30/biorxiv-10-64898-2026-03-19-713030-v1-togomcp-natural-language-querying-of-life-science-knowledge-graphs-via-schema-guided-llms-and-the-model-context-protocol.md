---
title: "TogoMCP: Natural Language Querying of Life-Science Knowledge Graphs via Schema-Guided LLMs and the Model Context Protocol"
title_zh: TogoMCP：通过模式引导的大语言模型和模型上下文协议实现生命科学知识图谱的自然语言查询
authors: "Kinjo, A. R., Yamamoto, Y., Bustamante-Larriet, S., Labra-Gayo, J. E., Fujisawa, T."
date: 2026-03-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.19.713030v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于查询生命科学知识图谱的LLM驱动智能体
tldr: TogoMCP是一个利用大语言模型（LLM）和模型上下文协议（MCP）实现生命科学知识图谱自然语言查询的系统。它通过MIE文件动态提供数据库模式上下文，并采用实体解析与SPARQL生成分离的两阶段工作流，显著提升了复杂生物医学查询的准确性，解决了LLM在生成SPARQL时容易产生幻觉的问题，为非专家研究者提供了便捷的知识检索工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 生命科学知识图谱查询需要复杂的SPARQL技能和模式知识，而LLM在缺乏引导时容易生成错误的谓词或标识符。
method: 通过MIE文件动态提供数据库模式上下文，并利用MCP协议构建了结合外部API实体解析与模式引导SPARQL生成的两阶段工作流。
result: "在涉及23个数据库的基准测试中，TogoMCP显著优于基准模型，在精确可验证问题上的胜率超过80%。"
conclusion: 研究表明，简洁且动态交付的模式上下文比复杂的编排逻辑更能有效提升LLM在特定领域知识图谱上的查询性能。
---

## 摘要
查询由 DBCLS 维护的 RDF Portal 知识图谱（该图谱汇集了 70 多个生命科学数据库）需要精通 SPARQL 和特定数据库的 RDF 模式，这使得大多数研究人员难以利用这一资源。大语言模型 (LLMs) 原则上可以将自然语言问题转化为可执行的 SPARQL，但由于缺乏模式层面的上下文，它们经常会虚构不存在的谓词，或者无法将实体名称解析为特定数据库的标识符。我们提出了 TogoMCP，这是一个将 LLM 重塑为协议驱动推理引擎的系统，通过模型上下文协议 (MCP) 编排专用工具。其设计的两个核心机制为：(i) MIE (Metadata-Interoperability-Exchange) 文件，这是一种简洁的 YAML 文档，在查询时动态地为 LLM 提供每个目标数据库的结构和语义上下文；(ii) 一个两阶段工作流，将通过外部 REST API 进行的实体解析与模式引导的 SPARQL 生成相分离。在涵盖 5 种类型和 23 个数据库的 50 个生物学问题的基准测试中，TogoMCP 相比于无辅助的基准模型取得了显著提升（Cohen's d = 0.92, Wilcoxon p < 10⁻⁶），对于具有精确、可验证答案的问题类型，胜率超过 80%。消融研究表明，MIE 文件是唯一不可或缺的组件：移除它们会将效果降低到不显著的水平 (d = 0.08)，而仅需一行加载相关 MIE 文件的指令即可恢复复杂行为协议带来的全部收益。这些结果提出了一个通用的设计原则：简洁、动态交付的模式上下文比复杂的编排逻辑更有价值。

数据库 URL：https://togomcp.rdfportal.org/

## Abstract
Querying the RDF Portal knowledge graph maintained by DBCLS--which aggregates more than 70 life-science databases--requires proficiency in both SPARQL and database-specific RDF schemas, placing this resource beyond the reach of most researchers. Large Language Models (LLMs) can, in principle, translate natural-language questions into executable SPARQL, but without schema-level context, they frequently fabricate non-existent predicates or fail to resolve entity names to database-specific identifiers. We present TogoMCP, a system that recasts the LLM as a protocol-driven inference engine orchestrating specialized tools via the Model Context Protocol (MCP). Two mechanisms are essential to its design: (i) the MIE (Metadata-Interoperability-Exchange) file, a concise YAML document that dynamically supplies the LLM with each target databases structural and semantic context at query time; and (ii) a two-stage workflow separating entity resolution via external REST APIs from schema-guided SPARQL generation. On a benchmark of 50 biologically grounded questions spanning five types and 23 databases, TogoMCP achieved a large improvement over an unaided baseline (Cohens d = 0.92, Wilcoxon p < 10-6), with win rates exceeding 80% for question types with precise, verifiable answers. An ablation study identified MIE files as the single indispensable component: removing them reduced the effect to a non-significant level (d = 0.08), while a one-line instruction to load the relevant MIE file recovered the full benefit of an elaborate behavioral protocol. These results suggest a general design principle: concise, dynamically delivered schema context is more valuable than complex orchestration logic.

Database URLhttps://togomcp.rdfportal.org/

---

## 论文详细总结（自动生成）

以下是对论文《TogoMCP: Natural Language Querying of Life-Science Knowledge Graphs via Schema-Guided LLMs and the Model Context Protocol》的结构化总结：

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：生命科学领域的知识图谱（如 DBCLS 的 RDF Portal）规模庞大且结构复杂，包含超过 70 个数据库。普通研究人员难以掌握复杂的 SPARQL 查询语言以及各数据库特有的 RDF 模式（Schema）。
*   **LLM 的局限性**：虽然大语言模型（LLM）具备生成代码的能力，但在处理特定领域的知识图谱时，常因缺乏模式上下文而产生“幻觉”（虚构不存在的谓词），且无法将自然语言中的实体（如基因名）准确映射为数据库特定的标识符（URI）。
*   **研究意义**：开发一个能够理解数据库结构、准确解析实体并生成可执行 SPARQL 的智能体系统，降低生物医学数据的获取门槛。

### 2. 论文提出的方法论
TogoMCP 将 LLM 重塑为由协议驱动的推理引擎，核心思想是**“模式引导”**与**“工具编排”**。
*   **模型上下文协议 (MCP)**：利用 Anthropic 提出的 MCP 开放标准，将 LLM 与外部工具（API、数据库、文件系统）无缝连接。
*   **MIE (Metadata-Interoperability-Exchange) 文件**：这是系统的核心创新。一种简洁的 YAML 格式文档，包含数据库的类、谓词、标识符模式及示例查询。它在查询时动态加载到 LLM 的上下文窗口中，提供必要的“地图”。
*   **两阶段工作流**：
    1.  **实体解析阶段**：利用外部 REST API（如 TogoID, TogoVar）将自然语言中的实体名称转换为标准的 URI 或内部 ID。
    2.  **SPARQL 生成阶段**：在 MIE 文件的指导下，LLM 根据解析出的实体和模式结构生成并执行 SPARQL 查询。
*   **动态上下文注入**：系统不是一次性给 LLM 灌输所有知识，而是根据问题类型，通过 MCP 动态检索并提供相关的 MIE 片段。

### 3. 实验设计
*   **数据集/场景**：构建了一个包含 **50 个生物学问题**的基准测试集，涵盖 5 种查询类型（简单查询、多跳查询、聚合查询、跨数据库查询、比较查询）。
*   **覆盖范围**：涉及 RDF Portal 中的 **23 个不同数据库**。
*   **对比基准 (Baseline)**：
    *   **Baseline**：仅提供基本系统提示词的 LLM（如 Claude 3.5 Sonnet）。
    *   **TogoMCP (Full)**：启用 MCP 工具、MIE 文件和完整工作流的系统。
*   **评估指标**：查询成功率、Cohen's d 效应量、Wilcoxon 符号秩检验（统计显著性）。

### 4. 资源与算力
*   **模型使用**：实验主要基于 **Claude 3.5 Sonnet** 模型通过 MCP 协议进行调用。
*   **算力说明**：论文未提及具体的 GPU 训练算力或时长，因为该研究侧重于 **Agent 框架的设计与推理逻辑**，而非模型本身的预训练或微调。系统运行在标准的服务器环境下，通过 API 与 LLM 交互。

### 5. 实验数量与充分性
*   **实验规模**：50 个精心设计的生物学问题，虽然数量不算巨大，但覆盖了 23 个真实的异构数据库，具有很强的领域代表性。
*   **消融实验**：研究者进行了关键的消融实验，分别移除了 MIE 文件和 MCP 协议逻辑。
*   **充分性评价**：实验设计较为严谨，通过统计学检验（p < 10⁻⁶）证明了结果的显著性。消融实验明确指出了 MIE 文件是性能提升的决定性因素，实验逻辑闭环且客观。

### 6. 论文的主要结论与发现
*   **MIE 是关键**：MIE 文件是系统不可或缺的组件。移除 MIE 后，系统性能退化至与基准模型无异（d = 0.08）；而只需一行指令加载 MIE，即可恢复大部分性能。
*   **性能大幅提升**：TogoMCP 在精确可验证问题上的胜率超过 **80%**，整体表现显著优于无辅助的 LLM（Cohen's d = 0.92）。
*   **设计原则**：研究表明，**简洁、动态交付的模式上下文**比复杂的 Agent 编排逻辑更能有效提升 LLM 在特定领域知识图谱上的表现。

### 7. 优点
*   **架构优雅**：利用 MCP 协议实现了工具的标准化接入，易于扩展到其他数据库。
*   **解决幻觉**：通过 MIE 文件强制约束 LLM 使用合法的谓词，显著降低了 SPARQL 语法错误。
*   **实用性强**：两阶段工作流有效解决了生物医学领域最头疼的实体歧义和标识符映射问题。
*   **轻量化**：无需对 LLM 进行昂贵的微调，仅通过上下文工程即可实现专业级表现。

### 8. 不足与局限
*   **MIE 维护成本**：虽然 MIE 文件简洁，但仍需要领域专家人工编写和维护，目前仅覆盖了 23/70+ 个数据库。
*   **API 依赖**：系统高度依赖外部实体解析 API 的可用性和准确性，若 API 宕机或数据过时，第一阶段将失败。
*   **复杂查询瓶颈**：对于极度复杂的跨库推理，LLM 仍可能在多步工具调用中丢失逻辑，或受限于上下文窗口长度。
*   **评估规模**：50 个问题虽然质量高，但若能扩展到数百个问题的自动化评测集，结论将更具普适性。

（完）
