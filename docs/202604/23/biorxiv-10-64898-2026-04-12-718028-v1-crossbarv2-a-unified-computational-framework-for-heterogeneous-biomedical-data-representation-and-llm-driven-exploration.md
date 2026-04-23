---
title: "CROssBARv2: A Unified Computational Framework for Heterogeneous Biomedical Data Representation and LLM-Driven Exploration"
title_zh: CROssBARv2：一种用于异构生物医学数据表示和 LLM 驱动探索的统一计算框架
authors: "Sen, B., Ulusoy, E., Darcan, M., Ergun, M., Lobentanzer, S., Rifaioglu, A. S., Turei, D., Saez-Rodriguez, J., Dogan, T."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.12.718028v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 大语言模型驱动的集成生物医学知识图谱探索
tldr: CROssBARv2是一个统一的生物医学数据集成平台，旨在解决数据碎片化和元数据不均的问题。它通过构建包含标准化本体和深度学习嵌入的大规模知识图谱，整合了异构数据源。该平台集成了CROssBAR-LLM，利用知识图谱增强大模型输出的准确性，支持药物重用、蛋白质功能预测等下游任务，为生物医学发现和转化研究提供了可扩展、AI就绪的交互式探索工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-001.webp\", \"caption\": \"Figure 1. Overview of the CROssBARv2 workflow. (a) Integration of data from 34 well-established sources covering various biomedical domains. (b) Automatic retrieval, standardisation, and integration of source data using modular adapter scripts. (c) CROssBARv2 KG schema, comprising 14 node types and 51 edge types. (d) Storage of the KG in a Neo4j graph database, along with rich metadata and node embeddings computed using deep learning-based methods. (e) Execution of the CROssBAR-LLM workflow, which translates natural language queries into Cypher, executes the queries on KG, and synthesizes structured results into natural language responses; also supports vector-based similarity search.\", \"page\": 6, \"index\": 1, \"width\": 890, \"height\": 1158}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-002.webp\", \"caption\": \"Figure 2. Exploration of the CROssBARv2 KG through three complementary interfaces. a) Natural language querying via the CROssBAR-LLM tool enables users to interact with the KG through questions written in plain language, supported by a backend that connects large language models with the Neo4j database (https://crossbarv2.hubiodatalab.com/llm). b) Programmatic access\", \"page\": 7, \"index\": 2, \"width\": 875, \"height\": 1252}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-003.webp\", \"caption\": \"Figure 5. CROssBAR-LLM benchmarking performance results on Cypher query generation and biomedical question answering tasks. (a) The number of correct Cypher queries produced by various LLMs utilised in CROssBAR-LLM (out of 50 cases). (b) The numbers of correct answers for standalone LLMs (striped bars) and CROssBAR-LLMs (solid bars) when answering in-house curated\", \"page\": 18, \"index\": 3, \"width\": 888, \"height\": 777}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-004.webp\", \"caption\": \"Figure 6. Deep learning-based utilization of CROssBARv2 for biological relationship prediction. (a) Overview of Heterogeneous Graph Transformer (HGT) based ProtHGT model and its training on the CROssBARv2 knowledge graph for protein function prediction. (b) Protein function prediction performance evaluated on the DeepHGAT Human dataset using Fmax scores. ProtHGT models that utilise ESM2 and ProtT5 protein language models achieved top performance in all categories.\", \"page\": 20, \"index\": 4, \"width\": 888, \"height\": 1196}]"
motivation: 针对生物医学领域数据存储碎片化、模态特定且元数据不统一导致的集成分析与重现性难题。
method: 构建了一个集成了异构数据、标准化本体和向量嵌入的大规模知识图谱，并开发了基于知识图谱增强的自然语言问答系统CROssBAR-LLM。
result: 通过多用例分析、生物医学问答基准测试以及蛋白质功能预测实验，验证了系统在减少模型幻觉和提升预测性能方面的有效性。
conclusion: CROssBARv2为假设生成和知识发现提供了一个可扩展、用户友好且AI就绪的基础框架，显著促进了转化医学研究。
---

## 摘要
生物医学发现受到碎片化、特定模态的存储库和不均匀元数据的阻碍，限制了综合分析、可访问性和可重复性。为了应对这些挑战，我们提出了 CROssBARv2，这是一个来源信息丰富的生物医学数据与知识集成平台，将异构来源统一为一个可维护、可扩展的系统。通过将多种数据类型整合到广泛的知识图谱中，并辅以标准化的本体、丰富的元数据和基于深度学习的向量嵌入，CROssBARv2 减轻了研究人员在多个孤立数据库中检索的需求，并能促进包括预测建模和机制推理在内的下游任务，从而支持药物重定向和蛋白质功能预测等应用。该平台通过 CROssBAR-LLM 提供交互式图谱探索和基于嵌入的语义搜索，CROssBAR-LLM 是一个直观的自然语言问答系统，它将大语言模型（LLM）的输出锚定在底层知识图谱中，以减轻幻觉。我们通过以下方式评估了 CROssBARv2：(i) 多个用例分析以测试生物学一致性和关系有效性；(ii) 知识增强的生物医学问答基准测试，将 CROssBAR-LLM 与通用 LLM 进行比较；以及 (iii) 利用 CROssBARv2 的异构结构进行蛋白质功能预测的深度学习预测建模实验。总之，CROssBARv2 提供了一个可扩展、AI 就绪且用户友好的基础，促进了假设生成、知识发现和转化研究。

## Abstract
Biomedical discovery is hindered by fragmented, modality-specific repositories and uneven metadata, limiting integrative analysis, accessibility, and reproducibility. To address these challenges, we present CROssBARv2, a provenance-rich biomedical data-and-knowledge integration platform that unifies heterogeneous sources into a maintainable, scalable system. By consolidating diverse data types into an extensive knowledge graph enriched with standardised ontologies, rich metadata, and deep learning-based vector embeddings, CROssBARv2 alleviates the need for researchers to navigate multiple siloed databases and can facilitate downstream tasks, including predictive modelling and mechanistic reasoning, enabling applications such as drug repurposing and protein function prediction. The platform offers interactive graph exploration and embedding-based semantic search with CROssBAR-LLM, an intuitive natural language question-answering system that grounds large language model (LLM) outputs in the underlying knowledge graph to mitigate hallucinations. We assess CROssBARv2 through (i) multiple use-case analyses to test biological coherence and relational validity; (ii) knowledge-augmented biomedical question-answering benchmarks comparing CROssBAR-LLM against generalist LLMs; and (iii) a deep learning-based predictive modelling experiment for protein function prediction leveraging the heterogeneous structure of CROssBARv2. Collectively, CROssBARv2 provides a scalable, AI-ready, and user-friendly foundation that facilitates hypothesis generation, knowledge discovery, and translational research.

---

## 论文详细总结（自动生成）

这篇论文介绍了 **CROssBARv2**，这是一个旨在解决生物医学数据碎片化、提高大语言模型（LLM）在专业领域可靠性的统一计算框架。以下是对该论文的深度结构化总结：

### 1. 核心问题与整体含义（研究动机）
*   **数据碎片化**：生物医学知识散落在数以千计的孤立数据库中，缺乏统一的元数据和标准化描述，阻碍了集成分析。
*   **知识图谱（KG）局限性**：现有的生物医学知识图谱往往缺乏维护、可重复性差，且对非编程人员不友好。
*   **LLM 幻觉问题**：通用大模型在处理复杂生物医学问题时容易产生虚假信息（幻觉），且缺乏对结构化专业知识的直接访问。
*   **核心目标**：构建一个来源清晰、可扩展、AI 就绪的集成平台，通过将 LLM 与大规模知识图谱结合，实现可靠的生物医学探索和预测建模。

### 2. 方法论：核心思想与技术细节
CROssBARv2 的核心是一个异构知识图谱，结合了图数据库、深度学习嵌入和自然语言处理技术：
*   **数据集成流水线**：利用 `Pypath` 和 `BioCypher` 框架，通过模块化的“适配器（Adapters）”脚本自动从 34 个数据源（如 UniProt, ChEMBL, DrugBank, KEGG 等）抓取并标准化数据。
*   **知识图谱结构**：存储于 Neo4j 数据库，包含约 **270 万个节点**（14 种类型）和 **1260 万条边**（51 种类型），并附带丰富的元数据（如证据代码、置信度得分）。
*   **多模态节点嵌入**：为不同实体生成向量表示：
    *   **蛋白质**：使用 ESM2 和 ProtT5 模型。
    *   **化合物/药物**：使用 SELFormer 模型。
    *   **基因/疾病/本体**：使用 Nucleotide Transformer、doc2vec 和 anc2vec 等。
*   **CROssBAR-LLM**：一个“Text-to-Cypher”系统。它接收自然语言查询，通过 Prompt Engineering 驱动 LLM 生成 Cypher 查询语句，在 Neo4j 中执行后，再将结构化结果总结为自然语言。
*   **混合搜索机制**：结合了图路径遍历（显式关系）和向量相似度搜索（隐式语义关系）。

### 3. 实验设计与 Benchmark
论文通过三个维度的实验验证了系统的有效性：
*   **生物学有效性分析**：使用 `metapath2vec` 算法在图上进行随机游走，验证蛋白质家族、药物-疾病关联和通路同义性在嵌入空间中的聚类效果。
*   **LLM 基准测试**：
    *   **Cypher 生成**：测试了 GPT-4o、Claude 3.5、DeepSeek R1 等模型生成正确查询语句的能力（50 个复杂问题）。
    *   **专业问答**：对比了独立 LLM、联网搜索 LLM 与 CROssBAR-LLM 在 100 个内部真假题和 50 个 GeneTuring 任务上的表现。
*   **预测建模（ProtHGT）**：开发了基于异构图变换器（HGT）的蛋白质功能预测模型，在 DeepHGAT 数据集上进行 Benchmark，对比了序列模型和单网络模型。

### 4. 资源与算力
*   **算力说明**：论文提到系统部署在配备 Docker 容器化的虚拟专用服务器（VPS）上。
*   **模型参数**：使用了大规模预训练模型，如 ESM2 (3B 参数)、Nucleotide Transformer (2.5B 参数)。
*   **缺失信息**：论文**未明确说明**构建整个知识图谱和训练 ProtHGT 模型具体的 GPU 型号、数量及确切的训练时长。

### 5. 实验数量与充分性
*   **实验规模**：
    *   **定性分析**：展示了从头设计分子（De novo molecules）的机制推导用例。
    *   **定量分析**：LLM 测试涵盖了主流的 10 余种闭源和开源模型；蛋白质功能预测在三个 GO 子本体（MF, CC, BP）上均进行了测试。
*   **充分性评价**：实验设计较为全面，不仅有自动化指标（Fmax, HR@K），还有复杂的专家级用例分析。对比方法包含了当前最先进的序列模型和图神经网络，实验结果具有较高的客观性和说服力。

### 6. 主要结论与发现
*   **知识增强显著提升准确性**：在生物医学问答中，CROssBAR-LLM 的表现远超独立 LLM（准确率从随机水平提升至 90% 以上），有效消除了幻觉。
*   **异构信息的重要性**：ProtHGT 模型通过整合通路、领域和相互作用信息，在蛋白质功能预测上达到了 SOTA（最优）水平，证明了异构图结构的价值。
*   **混合搜索的威力**：通过向量相似度，系统能发现图中未直接连接但具有生物学相似性的实体，这在药物重定向和新分子机制研究中极具潜力。

### 7. 优点与亮点
*   **来源透明性**：每条边都带有来源和置信度元数据，解决了生物医学数据“不可信”的痛点。
*   **用户友好性**：提供了 GraphQL API、Neo4j 浏览器和自然语言对话三种接口，兼顾了开发者和实验生物学家的需求。
*   **可维护性**：基于 BioCypher 的流水线使得知识图谱的更新和扩展变得自动化，克服了以往 KG 容易“过时”的问题。

### 8. 不足与局限
*   **标识符映射挑战**：不同数据库间的 ID 交叉引用不完整或不一致，可能导致部分数据在集成时丢失。
*   **疾病粒度问题**：疾病本体（如 Mondo）的层级复杂，处理不同粒度的疾病关联时存在挑战。
*   **LLM 依赖性**：Text-to-Cypher 的准确性高度依赖于底层 LLM 的逻辑推理能力，对于极度复杂的嵌套查询，小规模模型仍可能失败。
*   **实时性限制**：虽然数据集成是自动化的，但并非实时更新，仍存在一定的滞后性。

（完）
