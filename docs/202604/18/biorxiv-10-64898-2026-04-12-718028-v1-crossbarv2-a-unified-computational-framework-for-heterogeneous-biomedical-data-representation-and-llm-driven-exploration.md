---
title: "CROssBARv2: A Unified Computational Framework for Heterogeneous Biomedical Data Representation and LLM-Driven Exploration"
title_zh: CROssBARv2：一种用于异构生物医学数据表示和 LLM 驱动探索的统一计算框架
authors: "Sen, B., Ulusoy, E., Darcan, M., Ergun, M., Lobentanzer, S., Rifaioglu, A. S., Turei, D., Saez-Rodriguez, J., Dogan, T."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.12.718028v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 大语言模型驱动的异构生物医学数据与知识图谱探索
tldr: CROssBARv2是一个统一的生物医学数据集成平台，旨在解决数据碎片化和元数据不均的问题。它将异构数据整合为包含本体、元数据和深度学习嵌入的大规模知识图谱。通过集成CROssBAR-LLM，该平台支持自然语言问答并利用知识图谱减少模型幻觉，为药物重定位和蛋白质功能预测等下游任务提供支持，是促进假设生成和转化研究的AI就绪型基础框架。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-001.webp\", \"caption\": \"Figure 1. Overview of the CROssBARv2 workflow. (a) Integration of data from 34 well-established sources covering various biomedical domains. (b) Automatic retrieval, standardisation, and integration of source data using modular adapter scripts. (c) CROssBARv2 KG schema, comprising 14 node types and 51 edge types. (d) Storage of the KG in a Neo4j graph database, along with rich metadata and node embeddings computed using deep learning-based methods. (e) Execution of the CROssBAR-LLM workflow, which translates natural language queries into Cypher, executes the queries on KG, and synthesizes structured results into natural language responses; also supports vector-based similarity search.\", \"page\": 6, \"index\": 1, \"width\": 890, \"height\": 1158}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-002.webp\", \"caption\": \"Figure 2. Exploration of the CROssBARv2 KG through three complementary interfaces. a) Natural language querying via the CROssBAR-LLM tool enables users to interact with the KG through questions written in plain language, supported by a backend that connects large language models with the Neo4j database (https://crossbarv2.hubiodatalab.com/llm). b) Programmatic access\", \"page\": 7, \"index\": 2, \"width\": 875, \"height\": 1252}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-003.webp\", \"caption\": \"Figure 5. CROssBAR-LLM benchmarking performance results on Cypher query generation and biomedical question answering tasks. (a) The number of correct Cypher queries produced by various LLMs utilised in CROssBAR-LLM (out of 50 cases). (b) The numbers of correct answers for standalone LLMs (striped bars) and CROssBAR-LLMs (solid bars) when answering in-house curated\", \"page\": 18, \"index\": 3, \"width\": 888, \"height\": 777}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-004.webp\", \"caption\": \"Figure 6. Deep learning-based utilization of CROssBARv2 for biological relationship prediction. (a) Overview of Heterogeneous Graph Transformer (HGT) based ProtHGT model and its training on the CROssBARv2 knowledge graph for protein function prediction. (b) Protein function prediction performance evaluated on the DeepHGAT Human dataset using Fmax scores. ProtHGT models that utilise ESM2 and ProtT5 protein language models achieved top performance in all categories.\", \"page\": 20, \"index\": 4, \"width\": 888, \"height\": 1196}]"
motivation: 针对生物医学数据存储碎片化、模态特定且元数据不统一导致的集成分析与重现性难题。
method: 构建了一个包含丰富来源、标准化本体和向量嵌入的可扩展知识图谱，并开发了基于知识图谱增强的自然语言问答系统CROssBAR-LLM。
result: 通过多用例分析、生物医学问答基准测试以及蛋白质功能预测实验，验证了系统在生物学一致性、减少幻觉和预测建模方面的有效性。
conclusion: CROssBARv2为生物医学知识发现提供了一个可扩展、用户友好且AI就绪的统一计算框架。
---

## 摘要
生物医学发现受到碎片化、特定模态的存储库和不均匀元数据的阻碍，限制了综合分析、可访问性和可重复性。为了应对这些挑战，我们提出了 CROssBARv2，这是一个具有丰富溯源信息的生物医学数据与知识整合平台，它将异构来源统一为一个可维护、可扩展的系统。通过将多种数据类型整合到一个广泛的知识图谱中，并辅以标准化的本体、丰富的元数据和基于深度学习的向量嵌入，CROssBARv2 减轻了研究人员在多个孤立数据库中检索的需求，并能促进包括预测建模和机制推理在内的下游任务，从而支持药物重定向和蛋白质功能预测等应用。该平台通过 CROssBAR-LLM 提供交互式图谱探索和基于嵌入的语义搜索，CROssBAR-LLM 是一个直观的自然语言问答系统，它将大语言模型（LLM）的输出锚定在底层知识图谱中，以减轻幻觉。我们通过以下方式评估了 CROssBARv2：(i) 多个用例分析，以测试生物学一致性和关系有效性；(ii) 知识增强的生物医学问答基准测试，将 CROssBAR-LLM 与通用 LLM 进行比较；以及 (iii) 利用 CROssBARv2 的异构结构进行蛋白质功能预测的深度学习预测建模实验。总之，CROssBARv2 提供了一个可扩展、AI 就绪且用户友好的基础，促进了假设生成、知识发现和转化研究。

## Abstract
Biomedical discovery is hindered by fragmented, modality-specific repositories and uneven metadata, limiting integrative analysis, accessibility, and reproducibility. To address these challenges, we present CROssBARv2, a provenance-rich biomedical data-and-knowledge integration platform that unifies heterogeneous sources into a maintainable, scalable system. By consolidating diverse data types into an extensive knowledge graph enriched with standardised ontologies, rich metadata, and deep learning-based vector embeddings, CROssBARv2 alleviates the need for researchers to navigate multiple siloed databases and can facilitate downstream tasks, including predictive modelling and mechanistic reasoning, enabling applications such as drug repurposing and protein function prediction. The platform offers interactive graph exploration and embedding-based semantic search with CROssBAR-LLM, an intuitive natural language question-answering system that grounds large language model (LLM) outputs in the underlying knowledge graph to mitigate hallucinations. We assess CROssBARv2 through (i) multiple use-case analyses to test biological coherence and relational validity; (ii) knowledge-augmented biomedical question-answering benchmarks comparing CROssBAR-LLM against generalist LLMs; and (iii) a deep learning-based predictive modelling experiment for protein function prediction leveraging the heterogeneous structure of CROssBARv2. Collectively, CROssBARv2 provides a scalable, AI-ready, and user-friendly foundation that facilitates hypothesis generation, knowledge discovery, and translational research.

---

## 论文详细总结（自动生成）

这是一份关于论文《CROssBARv2: A Unified Computational Framework for Heterogeneous Biomedical Data Representation and LLM-Driven Exploration》的深度结构化总结：

### 1. 论文的核心问题与整体含义
*   **核心问题**：生物医学数据高度碎片化，存储在互不通用的特定模态数据库中，且元数据标准不一。这导致研究人员在进行跨领域综合分析（如药物重定向、蛋白质功能预测）时面临巨大的数据获取和整合障碍。
*   **研究背景**：虽然大语言模型（LLM）在生物医学问答中表现出色，但其容易产生“幻觉”，且缺乏对最新、结构化知识的直接访问。
*   **整体含义**：CROssBARv2 旨在构建一个统一的、AI 就绪的生物医学知识发现平台。它通过整合海量异构数据构建知识图谱（KG），并结合 LLM 提供自然语言交互界面，将 AI 的推理能力与结构化知识的准确性结合起来。

### 2. 论文提出的方法论
*   **核心思想**：构建一个包含丰富溯源信息的大规模知识图谱，并以此为基础，通过“图增强生成”（Graph-RAG）技术驱动 LLM 进行知识探索。
*   **关键技术细节**：
    *   **数据集成**：从 34 个权威来源（如 UniProt, ChEMBL, Ensembl, Reactome 等）自动检索并标准化数据。
    *   **KG 模式**：包含 14 种节点类型（蛋白质、药物、疾病、通路等）和 51 种关系类型，存储于 Neo4j 图数据库。
    *   **向量嵌入**：利用深度学习模型（如 ESM2 蛋白质语言模型）为节点生成向量嵌入，支持基于相似性的语义搜索。
    *   **CROssBAR-LLM 工作流**：
        1.  用户输入自然语言问题。
        2.  系统将问题转化为 **Cypher 查询语句**。
        3.  在 Neo4j 数据库中执行查询，获取结构化证据。
        4.  LLM 根据查询结果合成最终的自然语言回答，从而减少幻觉。

### 3. 实验设计
*   **数据集/场景**：
    *   **用例分析**：针对阿尔茨海默症等特定疾病进行药物重定向和机制推理。
    *   **问答基准测试**：使用 50 个内部策划的复杂生物医学问题。
    *   **蛋白质功能预测**：使用 DeepHGAT Human 数据集。
*   **Benchmark 与对比方法**：
    *   **LLM 对比**：对比了 GPT-4o, GPT-4-Turbo, Claude 3.5 Sonnet, Gemini 1.5 Pro 在独立运行与结合 CROssBARv2 后的表现。
    *   **预测模型对比**：在蛋白质功能预测任务中，对比了 ProtHGT 模型（基于 CROssBARv2）与现有的深度学习模型。

### 4. 资源与算力
*   **算力说明**：论文中提到了使用 ESM2 和 ProtT5 等预训练模型生成嵌入，并训练了 ProtHGT 模型。
*   **具体细节**：文中**未明确列出**具体的 GPU 型号、数量或总训练时长。但考虑到其集成的 34 个数据库规模和深度学习预测任务，该框架的构建和维护需要显著的计算资源和存储空间。

### 5. 实验数量与充分性
*   **实验规模**：
    *   **QA 测试**：进行了 50 组复杂查询测试，涵盖了 Cypher 语句生成的准确率和最终回答的正确性。
    *   **预测建模**：在标准数据集上进行了多指标（如 Fmax）评估。
*   **充分性评价**：实验设计较为全面，涵盖了从基础的知识检索到高级的预测建模。通过对比多种主流 LLM，验证了框架的普适性。虽然 50 个 QA 案例样本量不算巨大，但其针对性强，足以证明 Graph-RAG 模式的有效性。

### 6. 论文的主要结论与发现
*   **减少幻觉**：结合知识图谱后，LLM 在生物医学问答中的准确性显著提升，有效解决了通用模型胡编乱造事实的问题。
*   **Cypher 生成能力**：Claude 3.5 Sonnet 在将自然语言转化为图查询语句（Cypher）方面表现最强。
*   **预测性能提升**：利用 CROssBARv2 的异构图结构训练的 ProtHGT 模型，在蛋白质功能预测任务中达到了顶尖水平，证明了高质量集成数据对下游 AI 任务的价值。

### 7. 优点
*   **高度集成**：打破了生物医学数据的孤岛状态，提供了“一站式”数据访问。
*   **AI 就绪性**：不仅提供原始数据，还提供预计算的向量嵌入，方便直接用于机器学习。
*   **交互友好**：通过自然语言界面降低了非技术背景研究人员使用复杂图数据库的门槛。
*   **可解释性**：LLM 的回答基于图数据库的真实路径，具有可追溯的证据链。

### 8. 不足与局限
*   **维护成本**：集成 34 个动态更新的数据库，其数据同步和版本控制具有极高的维护挑战。
*   **Cypher 转化瓶颈**：对于极其复杂的跨多层关系的问题，LLM 生成的 Cypher 语句仍可能出错。
*   **数据偏差风险**：系统性能高度依赖于底层源数据库的质量，若源数据存在偏差，结果也会受到影响。
*   **实时性限制**：虽然集成了大量数据，但对于极少数前沿、尚未被收录进主流数据库的发现，系统可能无法覆盖。

（完）
