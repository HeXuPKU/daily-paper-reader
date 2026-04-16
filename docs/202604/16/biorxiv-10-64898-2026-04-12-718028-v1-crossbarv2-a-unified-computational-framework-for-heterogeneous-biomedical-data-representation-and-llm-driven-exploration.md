---
title: "CROssBARv2: A Unified Computational Framework for Heterogeneous Biomedical Data Representation and LLM-Driven Exploration"
title_zh: CROssBARv2：一种用于异构生物医学数据表示和大语言模型驱动探索的统一计算框架
authors: "Sen, B., Ulusoy, E., Darcan, M., Ergun, M., Lobentanzer, S., Rifaioglu, A. S., Turei, D., Saez-Rodriguez, J., Dogan, T."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.12.718028v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 大语言模型驱动的异构生物医学数据与知识图谱探索
tldr: CROssBARv2是一个统一的生物医学数据集成平台，旨在解决数据碎片化和元数据不均的问题。它将异构数据整合为包含标准化本体、丰富元数据和深度学习嵌入的大规模知识图谱。通过集成CROssBAR-LLM，该平台支持自然语言问答并利用知识图谱减少大模型幻觉，为药物重定位、蛋白质功能预测等下游任务提供可扩展、AI就绪的研究基础。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-001.webp\", \"caption\": \"Figure 1. Overview of the CROssBARv2 workflow. (a) Integration of data from 34 well-established sources covering various biomedical domains. (b) Automatic retrieval, standardisation, and integration of source data using modular adapter scripts. (c) CROssBARv2 KG schema, comprising 14 node types and 51 edge types. (d) Storage of the KG in a Neo4j graph database, along with rich metadata and node embeddings computed using deep learning-based methods. (e) Execution of the CROssBAR-LLM workflow, which translates natural language queries into Cypher, executes the queries on KG, and synthesizes structured results into natural language responses; also supports vector-based similarity search.\", \"page\": 6, \"index\": 1, \"width\": 890, \"height\": 1158}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-002.webp\", \"caption\": \"Figure 2. Exploration of the CROssBARv2 KG through three complementary interfaces. a) Natural language querying via the CROssBAR-LLM tool enables users to interact with the KG through questions written in plain language, supported by a backend that connects large language models with the Neo4j database (https://crossbarv2.hubiodatalab.com/llm). b) Programmatic access\", \"page\": 7, \"index\": 2, \"width\": 875, \"height\": 1252}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-003.webp\", \"caption\": \"Figure 5. CROssBAR-LLM benchmarking performance results on Cypher query generation and biomedical question answering tasks. (a) The number of correct Cypher queries produced by various LLMs utilised in CROssBAR-LLM (out of 50 cases). (b) The numbers of correct answers for standalone LLMs (striped bars) and CROssBAR-LLMs (solid bars) when answering in-house curated\", \"page\": 18, \"index\": 3, \"width\": 888, \"height\": 777}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-004.webp\", \"caption\": \"Figure 6. Deep learning-based utilization of CROssBARv2 for biological relationship prediction. (a) Overview of Heterogeneous Graph Transformer (HGT) based ProtHGT model and its training on the CROssBARv2 knowledge graph for protein function prediction. (b) Protein function prediction performance evaluated on the DeepHGAT Human dataset using Fmax scores. ProtHGT models that utilise ESM2 and ProtT5 protein language models achieved top performance in all categories.\", \"page\": 20, \"index\": 4, \"width\": 888, \"height\": 1196}]"
motivation: 针对生物医学领域数据存储碎片化、模态特定且元数据不统一导致的集成分析与重现性难题。
method: 构建了一个包含丰富来源、标准化本体和向量嵌入的大规模知识图谱，并开发了基于知识图谱增强的自然语言问答系统CROssBAR-LLM。
result: 通过多项用例分析、生物医学问答基准测试以及蛋白质功能预测实验，验证了系统在生物学一致性、关系有效性和预测准确性方面的优势。
conclusion: CROssBARv2为假设生成、知识发现和转化研究提供了一个可扩展、用户友好且支持AI驱动探索的统一计算框架。
---

## 摘要
生物医学发现受到碎片化、特定模态的存储库以及不均衡元数据的阻碍，限制了综合分析、可访问性和可重复性。为了应对这些挑战，我们提出了 CROssBARv2，这是一个具有丰富溯源信息的生物医学数据与知识集成平台，它将异构来源统一为一个可维护、可扩展的系统。通过将多种数据类型整合进一个由标准化本体、丰富元数据和基于深度学习的向量嵌入所增强的广泛知识图谱中，CROssBARv2 减轻了研究人员在多个孤立数据库中检索的需求，并能促进包括预测建模和机制推理在内的下游任务，从而实现药物重定向和蛋白质功能预测等应用。该平台通过 CROssBAR-LLM 提供交互式图谱探索和基于嵌入的语义搜索。CROssBAR-LLM 是一个直观的自然语言问答系统，它将大语言模型（LLM）的输出锚定在底层知识图谱中，以减轻幻觉问题。我们通过以下方式评估了 CROssBARv2：(i) 多项用例分析，以测试生物学一致性和关系有效性；(ii) 知识增强的生物医学问答基准测试，将 CROssBAR-LLM 与通用 LLM 进行对比；(iii) 利用 CROssBARv2 的异构结构进行基于深度学习的蛋白质功能预测建模实验。总而言之，CROssBARv2 提供了一个可扩展、AI 就绪且用户友好的基础，有助于促进假设生成、知识发现和转化研究。

## Abstract
Biomedical discovery is hindered by fragmented, modality-specific repositories and uneven metadata, limiting integrative analysis, accessibility, and reproducibility. To address these challenges, we present CROssBARv2, a provenance-rich biomedical data-and-knowledge integration platform that unifies heterogeneous sources into a maintainable, scalable system. By consolidating diverse data types into an extensive knowledge graph enriched with standardised ontologies, rich metadata, and deep learning based vector embeddings, CROssBARv2 alleviates the need for researchers to navigate multiple siloed databases and can facilitate downstream tasks, including predictive modelling and mechanistic reasoning, enabling applications such as drug repurposing and protein function prediction. The platform offers interactive graph exploration and embedding-based semantic search with CROssBAR-LLM, an intuitive natural language question-answering system that grounds large language model (LLM) outputs in the underlying knowledge graph to mitigate hallucinations. We assess CROssBARv2 through (i) multiple use-case analyses to test biological coherence and relational validity; (ii) knowledge-augmented biomedical question-answering benchmarks comparing CROssBAR-LLM against generalist LLMs; and (iii) a deep learning based predictive modelling experiment for protein function prediction leveraging the heterogeneous structure of CROssBARv2. Collectively, CROssBARv2 provides a scalable, AI-ready, and user-friendly foundation that facilitates hypothesis generation, knowledge discovery, and translational research.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **CROssBARv2** 的综合性计算框架，旨在通过构建大规模异构生物医学知识图谱（KG）并结合大语言模型（LLM），解决生物医学数据碎片化、元数据不统一以及 AI 模型（如 LLM）在专业领域易产生幻觉的问题。

以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **数据碎片化：** 生物医学知识散落在数以千计的独立数据库中，缺乏统一的表示，阻碍了跨领域的集成分析。
*   **元数据缺失：** 现有的知识图谱往往缺乏溯源信息（Provenance）和置信度评分，导致研究者难以区分实验验证数据与预测数据。
*   **LLM 幻觉：** 通用大模型在处理复杂的生物医学查询时，由于缺乏结构化知识的约束，容易生成虚假信息。
*   **核心目标：** 构建一个可维护、可扩展、AI 就绪的集成平台，通过“知识图谱+大模型”的架构，为药物重定位、蛋白质功能预测和机制推理提供可靠的工具。

### 2. 方法论：核心思想与关键技术
*   **知识图谱构建：**
    *   **数据集成：** 利用 `Pypath` 和 `BioCypher` 框架，从 34 个权威来源（如 UniProt, ChEMBL, DrugBank, KEGG 等）自动提取数据。
    *   **异构结构：** 包含 14 种节点类型（蛋白质、基因、药物、疾病、通路等）和 51 种边缘类型，共计约 270 万个节点和 1260 万条边。
    *   **丰富元数据：** 每条边都带有来源、证据代码、PubMed ID 和置信度评分。
*   **多模态表示学习（嵌入）：**
    *   集成多种 SOTA 预训练模型生成的向量：蛋白质（ESM2, ProtT5）、小分子（SELFormer）、基因（Nucleotide Transformer）、疾病（Doc2Vec）等。
*   **CROssBAR-LLM 系统：**
    *   **Text-to-Cypher：** 将用户的自然语言问题转换为 Neo4j 数据库的 Cypher 查询语句。
    *   **混合搜索：** 结合图遍历（显式关系）和向量相似度搜索（隐式语义关系）。
    *   **知识增强生成：** 将图数据库返回的结构化结果反馈给 LLM，生成有据可查的自然语言回答。

### 3. 实验设计与基准测试
*   **生物学有效性验证：** 使用 `metapath2vec` 算法在蛋白质家族、药物-疾病关联和通路同义性三个场景下进行嵌入空间分析，验证图谱结构的生物学一致性。
*   **De Novo 分子机制推导：** 针对数据库中不存在的虚拟分子，通过向量相似度定位到已知药物（如 MRI-1569），并利用图谱路径解释其潜在的治疗机制。
*   **LLM 性能评估：**
    *   **Cypher 生成：** 测试了 GPT-4o, Claude 3.5, DeepSeek R1 等模型生成复杂图查询语句的准确率。
    *   **生物医学问答：** 使用 100 个内部真/假问题和 50 个 `GeneTuring` 基准问题，对比了独立 LLM、联网搜索 LLM 与 CROssBAR-LLM 的表现。
*   **预测建模：** 提出 **ProtHGT**（基于异构图变换器），在蛋白质功能预测任务上对比了 `DeepHGAT`、`PSPGO` 等方法。

### 4. 资源与算力
*   **算力说明：** 论文中**未详细列出**具体的 GPU 训练时长或集群规模。
*   **基础设施：** 提到系统部署在基于 Docker 容器化的虚拟专用服务器（VPS）上，使用 Neo4j 作为图数据库引擎，通过 GraphQL API 提供访问。
*   **模型使用：** 蛋白质嵌入使用了 ESM2-3B 等大型预训练模型，这暗示了在数据预处理阶段需要相当规模的 GPU 资源。

### 5. 实验数量与充分性
*   **实验规模：** 涵盖了从底层图谱质量验证到高层 LLM 应用，再到下游深度学习预测的全流程。
*   **充分性：** 实验设计较为全面。不仅有定量指标（Fmax, HR@K, 准确率），还有定性的案例分析（如针对肥胖症和骨质疏松症的复杂多步推理）。
*   **客观性：** 对比了当前最顶尖的多个商用和开源 LLM，并使用了外部独立的 `GeneTuring` 基准，评估过程较为公正。

### 6. 主要结论与发现
*   **知识增强显著：** 结合知识图谱后，LLM 在生物医学问答中的准确率从随机水平（约 50%）提升至 90% 以上，显著优于单纯的联网搜索。
*   **异构性优势：** 在蛋白质功能预测中，利用 CROssBARv2 的多维关系（通路、领域、相互作用）使 ProtHGT 模型达到了 SOTA 性能。
*   **混合搜索能力：** 向量嵌入与图路径的结合，使得系统能够发现传统数据库中未直接记录的潜在关联（如虚拟分子的靶点预测）。

### 7. 优点与亮点
*   **端到端集成：** 实现了从原始数据抓取到自然语言交互的完整闭环。
*   **可解释性：** 所有的 LLM 输出都可以追溯到图谱中的具体节点和边，提供了生物医学研究急需的“溯源性”。
*   **AI 就绪：** 预先计算并集成了多种生物大分子的深度学习嵌入，极大方便了下游机器学习任务。
*   **用户友好：** 提供了自然语言界面、GraphQL API 和可视化浏览器，兼顾了实验科学家和计算科学家的需求。

### 8. 不足与局限
*   **标识符映射挑战：** 尽管使用了 Bioregistry，但在不同数据库间进行跨引用（Cross-referencing）时仍存在数据丢失或不一致的风险。
*   **疾病粒度问题：** 不同本体（如 Mondo, ICD）对疾病的分类粒度不同，可能导致查询结果在特定层级上出现偏差。
*   **LLM 依赖性：** 复杂的“多跳”查询对底层 LLM 的逻辑推理能力要求极高，较小的模型（如 GPT-4o-mini）在生成 Cypher 语句时表现较差。
*   **实时性限制：** 虽然有自动化脚本，但知识图谱的更新仍存在周期性，无法像联网搜索那样实时捕捉最新的预印本论文信息。

（完）
