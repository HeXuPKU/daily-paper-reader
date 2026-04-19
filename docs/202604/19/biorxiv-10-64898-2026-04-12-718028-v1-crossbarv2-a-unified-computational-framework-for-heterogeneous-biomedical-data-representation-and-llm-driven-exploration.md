---
title: "CROssBARv2: A Unified Computational Framework for Heterogeneous Biomedical Data Representation and LLM-Driven Exploration"
title_zh: CROssBARv2：一种用于异构生物医学数据表示和 LLM 驱动探索的统一计算框架
authors: "Sen, B., Ulusoy, E., Darcan, M., Ergun, M., Lobentanzer, S., Rifaioglu, A. S., Turei, D., Saez-Rodriguez, J., Dogan, T."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.12.718028v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 大语言模型驱动的集成生物医学知识图谱探索
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
生物医学发现受到碎片化、特定模态的存储库以及不均衡元数据的阻碍，这限制了综合分析、可访问性和可重复性。为了应对这些挑战，我们提出了 CROssBARv2，这是一个具有丰富溯源信息的生物医学数据与知识集成平台，它将异构来源统一为一个可维护、可扩展的系统。通过将多种数据类型整合到一个由标准化本体、丰富元数据和基于深度学习的向量嵌入所增强的广泛知识图谱中，CROssBARv2 减轻了研究人员在多个孤岛式数据库中检索的需求，并能促进包括预测建模和机制推理在内的下游任务，从而实现药物重定位和蛋白质功能预测等应用。该平台通过 CROssBAR-LLM 提供交互式图探索和基于嵌入的语义搜索，CROssBAR-LLM 是一个直观的自然语言问答系统，它将大语言模型（LLM）的输出锚定在底层知识图谱中，以缓解幻觉问题。我们通过以下方式评估了 CROssBARv2：(i) 多个用例分析以测试生物学一致性和关系有效性；(ii) 将 CROssBAR-LLM 与通用 LLM 进行对比的知识增强型生物医学问答基准测试；以及 (iii) 利用 CROssBARv2 的异构结构进行蛋白质功能预测的深度学习预测建模实验。总的来说，CROssBARv2 提供了一个可扩展、AI 就绪且用户友好的基础，促进了假设生成、知识发现和转化研究。

## Abstract
Biomedical discovery is hindered by fragmented, modality-specific repositories and uneven metadata, limiting integrative analysis, accessibility, and reproducibility. To address these challenges, we present CROssBARv2, a provenance-rich biomedical data-and-knowledge integration platform that unifies heterogeneous sources into a maintainable, scalable system. By consolidating diverse data types into an extensive knowledge graph enriched with standardised ontologies, rich metadata, and deep learning-based vector embeddings, CROssBARv2 alleviates the need for researchers to navigate multiple siloed databases and can facilitate downstream tasks, including predictive modelling and mechanistic reasoning, enabling applications such as drug repurposing and protein function prediction. The platform offers interactive graph exploration and embedding-based semantic search with CROssBAR-LLM, an intuitive natural language question-answering system that grounds large language model (LLM) outputs in the underlying knowledge graph to mitigate hallucinations. We assess CROssBARv2 through (i) multiple use-case analyses to test biological coherence and relational validity; (ii) knowledge-augmented biomedical question-answering benchmarks comparing CROssBAR-LLM against generalist LLMs; and (iii) a deep learning-based predictive modelling experiment for protein function prediction leveraging the heterogeneous structure of CROssBARv2. Collectively, CROssBARv2 provides a scalable, AI-ready, and user-friendly foundation that facilitates hypothesis generation, knowledge discovery, and translational research.

---

## 论文详细总结（自动生成）

这篇论文介绍了 **CROssBARv2**，一个旨在统一异构生物医学数据并利用大语言模型（LLM）驱动探索的计算框架。以下是对该论文的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：生物医学数据高度碎片化，分布在不同模态、不同标准的孤岛数据库中。现有的知识图谱（KG）往往缺乏丰富的元数据（如溯源、置信度）、维护困难、可重复性差，且对非编程人员不友好。
*   **整体含义**：论文旨在构建一个“AI就绪”的集成平台。它不仅整合了海量异构数据，还通过深度学习嵌入（Embeddings）和LLM集成，解决了传统KG查询门槛高以及通用LLM在专业领域容易产生“幻觉”的问题。

### 2. 方法论：核心思想与关键技术
*   **核心思想**：通过自动化流水线将34个数据源整合进一个基于Neo4j的知识图谱，并结合深度学习生成的节点嵌入，实现“图遍历+向量搜索”的混合探索模式。
*   **关键技术细节**：
    *   **数据集成**：使用 `Pypath` 和 `BioCypher` 框架，确保数据符合FAIR原则（可发现、可访问、可互操作、可重用）。
    *   **知识图谱结构**：包含约270万个节点（14种类型）和1260万条边（51种类型），涵盖基因、蛋白质、药物、疾病、通路等。
    *   **多模态嵌入**：集成多种SOTA模型（如蛋白质的ESM2/ProtT5、小分子的SELFormer、疾病的doc2vec等）生成节点向量，支持语义相似性搜索。
    *   **CROssBAR-LLM**：采用 **Text-to-Cypher** 机制。用户输入自然语言，系统将其转化为图查询语言（Cypher），在KG中检索事实后再由LLM总结输出，从而确保回答的真实性。

### 3. 实验设计
*   **实验场景与数据集**：
    *   **生物学有效性验证**：使用 `metapath2vec` 算法在KG上进行随机游走，验证蛋白质家族聚类、药物-疾病关联和通路同义性。
    *   **LLM基准测试**：
        *   **Cypher生成**：测试50个复杂自然语言问题转化为Cypher查询的准确率。
        *   **问答准确性**：使用100个内部策划的真/假问题和外部的 `GeneTuring` 基准测试。
    *   **预测建模**：开发了 **ProtHGT**（基于异构图变换器），在 `DeepHGAT` 人类数据集上预测蛋白质功能（GO术语）。
*   **对比方法**：
    *   **LLM对比**：对比了 GPT-4o, Claude 3.5, Llama 3.1, DeepSeek R1 等在独立模式与 CROssBAR 增强模式下的表现。
    *   **预测模型对比**：对比了 DeepHGAT, PSPGO 以及基于序列的 SOTA 模型。

### 4. 资源与算力
*   **算力说明**：文中提到系统部署在配备 Docker 的虚拟专用服务器（VPS）上。
*   **具体细节**：论文未在正文中详细列出训练 ProtHGT 或生成千万级节点嵌入的具体 GPU 型号、数量及总训练时长（通常此类细节位于补充材料或引用的子项目中）。它强调了框架的可扩展性和容器化部署。

### 5. 实验数量与充分性
*   **实验规模**：
    *   涵盖了从底层图结构验证（metapath2vec）到高层应用（LLM问答、深度学习预测）的多个维度。
    *   使用了34个权威数据库作为数据源，基准测试包含150个以上的人工标注问题。
*   **充分性评价**：实验设计较为充分且客观。通过引入外部基准（GeneTuring）和与多种主流LLM对比，证明了该框架在减少幻觉和提升专业问答准确率方面的显著作用。

### 6. 主要结论与发现
*   **知识增强显著**：将 LLM 与 CROssBARv2 KG 结合后，生物医学问答的准确率从随机水平（约50%）提升至近乎完美（97%-98%）。
*   **混合搜索优势**：通过向量嵌入，系统能发现图中未直接连接但语义相似的实体（如发现 MRI-1569 作为 de novo 分子的潜在机制），这对于药物重定位至关重要。
*   **预测性能领先**：ProtHGT 模型在蛋白质功能预测任务中达到了 SOTA 水平，证明了异构图结构比单一序列信息更具表达力。

### 7. 优点
*   **易用性极佳**：为非编程人员提供了自然语言接口，为开发者提供了 GraphQL API 和 Neo4j 浏览器。
*   **溯源透明**：KG 中的每条边都带有证据代码、置信度分数和文献来源，极大增强了科研结论的可信度。
*   **高度自动化**：通过适配器脚本实现数据定期更新，解决了生物医学知识图谱容易过时的问题。

### 8. 不足与局限
*   **标识符映射挑战**：不同数据库间的标识符交叉引用（Cross-referencing）仍存在不一致或缺失，可能导致部分数据丢失。
*   **疾病粒度问题**：不同本体（如 Mondo, MeSH）对疾病的分类粒度不同，整合时可能存在语义重叠或模糊。
*   **LLM依赖性**：Text-to-Cypher 的准确性高度依赖于底层 LLM 的逻辑推理能力，对于极其复杂的嵌套查询，小型模型仍可能失败。

（完）
