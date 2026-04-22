---
title: "CROssBARv2: A Unified Computational Framework for Heterogeneous Biomedical Data Representation and LLM-Driven Exploration"
title_zh: CROssBARv2：一种用于异构生物医学数据表示和 LLM 驱动探索的统一计算框架
authors: "Sen, B., Ulusoy, E., Darcan, M., Ergun, M., Lobentanzer, S., Rifaioglu, A. S., Turei, D., Saez-Rodriguez, J., Dogan, T."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.12.718028v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 大语言模型驱动的异构生物医学数据和知识图谱探索
tldr: CROssBARv2是一个统一的生物医学数据集成平台，旨在解决数据碎片化和元数据不均的问题。它通过构建包含本体、元数据和深度学习嵌入的大规模知识图谱，整合了异构生物医学资源。该平台集成了CROssBAR-LLM，利用知识图谱增强大语言模型的问答能力，有效减少幻觉。研究通过多项实验证明了其在药物重定向、蛋白质功能预测及语义搜索方面的卓越性能，为转化医学研究提供了可扩展且AI就绪的基础设施。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-001.webp\", \"caption\": \"Figure 1. Overview of the CROssBARv2 workflow. (a) Integration of data from 34 well-established sources covering various biomedical domains. (b) Automatic retrieval, standardisation, and integration of source data using modular adapter scripts. (c) CROssBARv2 KG schema, comprising 14 node types and 51 edge types. (d) Storage of the KG in a Neo4j graph database, along with rich metadata and node embeddings computed using deep learning-based methods. (e) Execution of the CROssBAR-LLM workflow, which translates natural language queries into Cypher, executes the queries on KG, and synthesizes structured results into natural language responses; also supports vector-based similarity search.\", \"page\": 6, \"index\": 1, \"width\": 890, \"height\": 1158}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-002.webp\", \"caption\": \"Figure 2. Exploration of the CROssBARv2 KG through three complementary interfaces. a) Natural language querying via the CROssBAR-LLM tool enables users to interact with the KG through questions written in plain language, supported by a backend that connects large language models with the Neo4j database (https://crossbarv2.hubiodatalab.com/llm). b) Programmatic access\", \"page\": 7, \"index\": 2, \"width\": 875, \"height\": 1252}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-003.webp\", \"caption\": \"Figure 5. CROssBAR-LLM benchmarking performance results on Cypher query generation and biomedical question answering tasks. (a) The number of correct Cypher queries produced by various LLMs utilised in CROssBAR-LLM (out of 50 cases). (b) The numbers of correct answers for standalone LLMs (striped bars) and CROssBAR-LLMs (solid bars) when answering in-house curated\", \"page\": 18, \"index\": 3, \"width\": 888, \"height\": 777}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-004.webp\", \"caption\": \"Figure 6. Deep learning-based utilization of CROssBARv2 for biological relationship prediction. (a) Overview of Heterogeneous Graph Transformer (HGT) based ProtHGT model and its training on the CROssBARv2 knowledge graph for protein function prediction. (b) Protein function prediction performance evaluated on the DeepHGAT Human dataset using Fmax scores. ProtHGT models that utilise ESM2 and ProtT5 protein language models achieved top performance in all categories.\", \"page\": 20, \"index\": 4, \"width\": 888, \"height\": 1196}]"
motivation: 针对生物医学数据存储碎片化、模态特定且元数据不统一导致的集成分析与重现性难题。
method: 构建了一个富含来源信息的异构知识图谱，并结合深度学习向量嵌入与基于知识图谱增强的LLM问答系统。
result: 实验表明该平台在生物学一致性验证、知识增强问答基准测试以及蛋白质功能预测任务中均表现优异。
conclusion: CROssBARv2为假设生成和知识发现提供了一个可扩展、用户友好且AI就绪的统一计算框架。
---

## 摘要
生物医学发现受到碎片化、特定模态的存储库以及不均匀元数据的阻碍，这限制了综合分析、可访问性和可重复性。为了应对这些挑战，我们提出了 CROssBARv2，这是一个具有丰富溯源信息的生物医学数据与知识整合平台，它将异构来源统一为一个可维护、可扩展的系统。通过将多种数据类型整合到一个富含标准化本体、丰富元数据和基于深度学习的向量嵌入的广泛知识图谱中，CROssBARv2 减轻了研究人员在多个孤立数据库中检索的需求，并能促进包括预测建模和机制推理在内的下游任务，从而实现药物重定向和蛋白质功能预测等应用。该平台通过 CROssBAR-LLM 提供交互式图谱探索和基于嵌入的语义搜索。CROssBAR-LLM 是一个直观的自然语言问答系统，它将大语言模型（LLM）的输出锚定在底层知识图谱中，以减轻幻觉问题。我们通过以下方式评估了 CROssBARv2：(i) 多项用例分析，以测试生物学一致性和关系有效性；(ii) 知识增强的生物医学问答基准测试，将 CROssBAR-LLM 与通用 LLM 进行对比；以及 (iii) 利用 CROssBARv2 的异构结构进行蛋白质功能预测的深度学习预测建模实验。总之，CROssBARv2 提供了一个可扩展、AI 就绪且用户友好的基础，促进了假设生成、知识发现和转化研究。

## Abstract
Biomedical discovery is hindered by fragmented, modality-specific repositories and uneven metadata, limiting integrative analysis, accessibility, and reproducibility. To address these challenges, we present CROssBARv2, a provenance-rich biomedical data-and-knowledge integration platform that unifies heterogeneous sources into a maintainable, scalable system. By consolidating diverse data types into an extensive knowledge graph enriched with standardised ontologies, rich metadata, and deep learning-based vector embeddings, CROssBARv2 alleviates the need for researchers to navigate multiple siloed databases and can facilitate downstream tasks, including predictive modelling and mechanistic reasoning, enabling applications such as drug repurposing and protein function prediction. The platform offers interactive graph exploration and embedding-based semantic search with CROssBAR-LLM, an intuitive natural language question-answering system that grounds large language model (LLM) outputs in the underlying knowledge graph to mitigate hallucinations. We assess CROssBARv2 through (i) multiple use-case analyses to test biological coherence and relational validity; (ii) knowledge-augmented biomedical question-answering benchmarks comparing CROssBAR-LLM against generalist LLMs; and (iii) a deep learning-based predictive modelling experiment for protein function prediction leveraging the heterogeneous structure of CROssBARv2. Collectively, CROssBARv2 provides a scalable, AI-ready, and user-friendly foundation that facilitates hypothesis generation, knowledge discovery, and translational research.

---

## 论文详细总结（自动生成）

这是一份关于论文《CROssBARv2：一种用于异构生物医学数据表示和 LLM 驱动探索的统一计算框架》的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
生物医学研究面临着**数据碎片化**的严重挑战。海量数据分布在不同的、模态特定的存储库中（如蛋白质、药物、疾病、通路等），且元数据标准不一，导致跨领域集成分析极其困难。
*   **研究动机**：现有的集成工具往往难以维护、扩展性差，且缺乏直观的交互方式。
*   **核心目标**：构建一个统一的、AI 就绪的计算框架，将异构生物医学数据整合为大规模知识图谱（KG），并利用大语言模型（LLM）提供自然语言交互能力，以支持药物重定向、蛋白质功能预测等转化医学研究。

### 2. 方法论：核心思想与技术细节
CROssBARv2 的核心是一个**多层级的集成架构**，主要包含以下关键组件：
*   **知识图谱构建 (KG Construction)**：
    *   利用 **BioCypher** 框架，通过模块化适配器从 34 个权威数据源（如 UniProt, ChEMBL, Reactome, ClinVar 等）自动提取、标准化并整合数据。
    *   **图谱规模**：包含 14 种节点类型（蛋白质、药物、疾病、基因、通路等）和 51 种关系类型（边）。
    *   **存储与检索**：使用 **Neo4j** 图数据库存储，并为节点生成深度学习嵌入（如蛋白质的 ESM2/ProtT5 嵌入、药物的 Morgan 指纹、结构的 Node2Vec 嵌入）。
*   **CROssBAR-LLM 工作流**：
    *   **自然语言转 Cypher (NL-to-Cypher)**：用户输入自然语言问题，系统通过 Prompt Engineering 引导 LLM 生成 Neo4j 查询语句（Cypher）。
    *   **知识增强生成 (RAG)**：在 KG 中执行查询获取结构化事实，再由 LLM 将结果汇总为自然语言回答，有效减少了 LLM 的“幻觉”现象。
    *   **语义搜索**：集成基于向量相似度的搜索，允许用户通过生物学含义而非仅靠关键词查找相关实体。

### 3. 实验设计
研究通过三个维度验证了系统的有效性：
*   **生物学一致性验证 (Use-case Analysis)**：通过具体案例（如伊马替尼的药物重定向、特定蛋白质的功能关联）展示系统在复杂生物医学推理中的表现。
*   **LLM 基准测试 (Benchmarking)**：
    *   **任务 1**：评估不同 LLM（GPT-4o, Claude 3.5 Sonnet, Gemini 1.5 Pro 等）生成 Cypher 语句的准确性。
    *   **任务 2**：对比“独立 LLM”与“CROssBAR-LLM (RAG 模式)”在回答 50 个精心设计的生物医学问题时的准确率。
*   **深度学习预测建模**：
    *   **任务**：蛋白质功能预测（GO 条目预测）。
    *   **模型**：开发了 **ProtHGT**（基于异构图变换器 Heterogeneous Graph Transformer）。
    *   **数据集**：使用 DeepHGAT Human 数据集作为 Benchmark，对比了不同蛋白质语言模型（ESM2, ProtT5）作为输入特征的效果。

### 4. 资源与算力
*   **硬件使用**：论文明确提到在模型训练和嵌入生成过程中使用了 **NVIDIA A100 GPU**。
*   **训练细节**：ProtHGT 模型的训练以及大规模节点嵌入（如 Node2Vec 和蛋白质语言模型特征提取）均依赖高性能计算资源，但未详细列出总训练时长。

### 5. 实验数量与充分性
*   **实验覆盖面**：研究涵盖了从数据库查询准确性、自然语言问答质量到下游深度学习预测任务的多个层面，实验设计较为全面。
*   **充分性评价**：
    *   使用了 50 个涵盖不同复杂度的测试用例进行 LLM 评估，具有一定的代表性。
    *   在蛋白质功能预测中，对比了多种主流的蛋白质语言模型，实验结果具有统计学意义。
    *   **客观性**：通过与通用 LLM 的直接对比，客观展示了知识图谱在消除幻觉方面的优势。

### 6. 主要结论与发现
*   **LLM 性能提升**：CROssBAR-LLM 在生物医学问答中的表现显著优于独立 LLM，尤其是在处理需要跨数据库关联的复杂查询时，准确率大幅提升。
*   **Cypher 生成能力**：GPT-4o 和 Claude 3.5 Sonnet 在将自然语言转化为图查询语句方面表现最强。
*   **预测建模优势**：利用 CROssBARv2 提供的异构图结构训练的 ProtHGT 模型，在蛋白质功能预测任务上达到了 SOTA（当前最佳）水平，证明了异构信息对生物学推理的重要性。
*   **消除幻觉**：通过将 LLM 锚定在结构化知识图谱上，系统能够提供可追溯来源的证据，极大地增强了结果的可信度。

### 7. 优点与亮点
*   **高度集成性**：成功将 34 个异构数据源统一在一个模式下，解决了数据孤岛问题。
*   **AI 就绪 (AI-ready)**：不仅提供原始数据，还预计算了高质量的向量嵌入，方便下游机器学习任务直接调用。
*   **交互创新**：结合了 LLM 的易用性和图数据库的严谨性，降低了非技术背景研究人员探索复杂生物数据的门槛。
*   **开源与模块化**：基于 BioCypher 构建，具有良好的可维护性和社区扩展潜力。

### 8. 不足与局限
*   **LLM 依赖性**：系统的核心性能（尤其是 NL-to-Cypher）高度依赖于底层商业 LLM 的能力，可能存在成本和隐私合规问题。
*   **复杂查询瓶颈**：对于极度复杂的自然语言请求，生成的 Cypher 语句可能仍会出现逻辑偏差。
*   **数据更新延迟**：虽然流程自动化，但知识图谱的实时更新仍面临大规模数据处理的同步压力。
*   **偏差风险**：底层数据源本身的偏差（如某些研究较多的蛋白质信息更丰富）可能会被传播到预测模型中。

（完）
