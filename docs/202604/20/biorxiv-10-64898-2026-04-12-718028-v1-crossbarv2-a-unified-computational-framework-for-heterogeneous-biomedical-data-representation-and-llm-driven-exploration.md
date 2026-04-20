---
title: "CROssBARv2: A Unified Computational Framework for Heterogeneous Biomedical Data Representation and LLM-Driven Exploration"
title_zh: CROssBARv2：一种用于异构生物医学数据表示和 LLM 驱动探索的统一计算框架
authors: "Sen, B., Ulusoy, E., Darcan, M., Ergun, M., Lobentanzer, S., Rifaioglu, A. S., Turei, D., Saez-Rodriguez, J., Dogan, T."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.12.718028v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 大语言模型驱动的集成生物医学知识图谱探索
tldr: CROssBARv2是一个统一的生物医学数据集成平台，旨在解决数据碎片化和元数据不均的问题。它通过构建包含多样化数据类型的大规模知识图谱，并结合深度学习向量嵌入和CROssBAR-LLM问答系统，实现了交互式图形探索和语义搜索。该框架不仅能缓解大模型的幻觉问题，还支持药物重定向和蛋白质功能预测等下游任务，为生物医学发现和转化研究提供了可扩展且AI就绪的基础。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-001.webp\", \"caption\": \"Figure 1. Overview of the CROssBARv2 workflow. (a) Integration of data from 34 well-established sources covering various biomedical domains. (b) Automatic retrieval, standardisation, and integration of source data using modular adapter scripts. (c) CROssBARv2 KG schema, comprising 14 node types and 51 edge types. (d) Storage of the KG in a Neo4j graph database, along with rich metadata and node embeddings computed using deep learning-based methods. (e) Execution of the CROssBAR-LLM workflow, which translates natural language queries into Cypher, executes the queries on KG, and synthesizes structured results into natural language responses; also supports vector-based similarity search.\", \"page\": 6, \"index\": 1, \"width\": 890, \"height\": 1158}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-002.webp\", \"caption\": \"Figure 2. Exploration of the CROssBARv2 KG through three complementary interfaces. a) Natural language querying via the CROssBAR-LLM tool enables users to interact with the KG through questions written in plain language, supported by a backend that connects large language models with the Neo4j database (https://crossbarv2.hubiodatalab.com/llm). b) Programmatic access\", \"page\": 7, \"index\": 2, \"width\": 875, \"height\": 1252}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-003.webp\", \"caption\": \"Figure 5. CROssBAR-LLM benchmarking performance results on Cypher query generation and biomedical question answering tasks. (a) The number of correct Cypher queries produced by various LLMs utilised in CROssBAR-LLM (out of 50 cases). (b) The numbers of correct answers for standalone LLMs (striped bars) and CROssBAR-LLMs (solid bars) when answering in-house curated\", \"page\": 18, \"index\": 3, \"width\": 888, \"height\": 777}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-004.webp\", \"caption\": \"Figure 6. Deep learning-based utilization of CROssBARv2 for biological relationship prediction. (a) Overview of Heterogeneous Graph Transformer (HGT) based ProtHGT model and its training on the CROssBARv2 knowledge graph for protein function prediction. (b) Protein function prediction performance evaluated on the DeepHGAT Human dataset using Fmax scores. ProtHGT models that utilise ESM2 and ProtT5 protein language models achieved top performance in all categories.\", \"page\": 20, \"index\": 4, \"width\": 888, \"height\": 1196}]"
motivation: 针对生物医学领域数据存储碎片化、模态特定且元数据不统一导致的集成分析与重现性难题。
method: 构建了一个集成了标准化本体、丰富元数据和深度学习嵌入的大规模知识图谱，并开发了基于知识图谱增强的自然语言问答系统CROssBAR-LLM。
result: 通过多项用例分析、生物医学问答基准测试以及蛋白质功能预测实验，验证了系统在生物学一致性、关系有效性和预测建模方面的优越性。
conclusion: CROssBARv2提供了一个可扩展、用户友好且AI就绪的计算框架，有效促进了生物医学领域的假设生成、知识发现和转化研究。
---

## 摘要
生物医学发现受到碎片化、特定模态的存储库以及不均衡元数据的阻碍，这限制了综合分析、可访问性和可重复性。为了应对这些挑战，我们提出了 CROssBARv2，这是一个具有丰富溯源信息的生物医学数据与知识集成平台，它将异构来源统一为一个可维护、可扩展的系统。通过将多种数据类型整合到一个由标准化本体、丰富元数据和基于深度学习的向量嵌入所增强的广泛知识图谱中，CROssBARv2 减轻了研究人员在多个孤岛式数据库中检索的需求，并能促进包括预测建模和机制推理在内的下游任务，从而实现药物重定位和蛋白质功能预测等应用。该平台通过 CROssBAR-LLM 提供交互式图探索和基于嵌入的语义搜索，CROssBAR-LLM 是一个直观的自然语言问答系统，它将大语言模型（LLM）的输出锚定在底层知识图谱中，以缓解幻觉问题。我们通过以下方式评估了 CROssBARv2：(i) 多个用例分析以测试生物学一致性和关系有效性；(ii) 将 CROssBAR-LLM 与通用 LLM 进行对比的知识增强型生物医学问答基准测试；以及 (iii) 利用 CROssBARv2 的异构结构进行蛋白质功能预测的深度学习预测建模实验。总的来说，CROssBARv2 提供了一个可扩展、AI 就绪且用户友好的基础，促进了假设生成、知识发现和转化研究。

## Abstract
Biomedical discovery is hindered by fragmented, modality-specific repositories and uneven metadata, limiting integrative analysis, accessibility, and reproducibility. To address these challenges, we present CROssBARv2, a provenance-rich biomedical data-and-knowledge integration platform that unifies heterogeneous sources into a maintainable, scalable system. By consolidating diverse data types into an extensive knowledge graph enriched with standardised ontologies, rich metadata, and deep learning-based vector embeddings, CROssBARv2 alleviates the need for researchers to navigate multiple siloed databases and can facilitate downstream tasks, including predictive modelling and mechanistic reasoning, enabling applications such as drug repurposing and protein function prediction. The platform offers interactive graph exploration and embedding-based semantic search with CROssBAR-LLM, an intuitive natural language question-answering system that grounds large language model (LLM) outputs in the underlying knowledge graph to mitigate hallucinations. We assess CROssBARv2 through (i) multiple use-case analyses to test biological coherence and relational validity; (ii) knowledge-augmented biomedical question-answering benchmarks comparing CROssBAR-LLM against generalist LLMs; and (iii) a deep learning-based predictive modelling experiment for protein function prediction leveraging the heterogeneous structure of CROssBARv2. Collectively, CROssBARv2 provides a scalable, AI-ready, and user-friendly foundation that facilitates hypothesis generation, knowledge discovery, and translational research.

---

## 论文详细总结（自动生成）

这是一份关于论文 **《CROssBARv2: A Unified Computational Framework for Heterogeneous Biomedical Data Representation and LLM-Driven Exploration》** 的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
生物医学研究面临着**数据碎片化**、**存储库模态特定**以及**元数据不统一**的严峻挑战。现有的知识图谱（KG）往往针对特定任务设计，缺乏丰富的上下文元数据（如证据来源、置信度评分），且对非编程人员不友好。此外，通用大语言模型（LLM）在处理专业生物医学问题时容易产生**幻觉**。
**CROssBARv2** 的研究动机在于构建一个统一、可扩展、AI就绪且用户友好的计算框架，通过集成异构生物医学数据并结合 LLM 驱动的探索工具，解决数据孤岛问题，提高研究的可重复性和发现效率。

### 2. 方法论：核心思想与关键技术
CROssBARv2 的核心是一个集成了大规模异构数据的知识图谱，其关键技术包括：
*   **数据集成与标准化**：利用 `BioCypher` 框架和自定义适配器脚本，从 34 个权威数据源（如 UniProt, ChEMBL, DrugBank, KEGG 等）自动抓取数据。涵盖 14 种节点类型（蛋白质、药物、疾病、基因等）和 51 种边缘类型，包含约 270 万个节点和 1260 万条边。
*   **丰富元数据与溯源**：每个节点和边缘都附带详细的属性，包括来源数据库、PubMed ID、证据代码和置信度评分，支持可靠的过滤分析。
*   **深度学习嵌入（Embeddings）**：为不同实体生成向量表示。例如，使用 `ESM2` 和 `ProtT5` 处理蛋白质，使用 `SELFormer` 处理化合物，使用 `Nucleotide Transformer` 处理基因。
*   **CROssBAR-LLM 系统**：
    *   **Text-to-Cypher**：将用户的自然语言查询转换为 Neo4j 数据库的 Cypher 查询语句。
    *   **知识增强生成（RAG 思想）**：将图谱检索到的结构化结果反馈给 LLM，生成有据可查的回答，显著降低幻觉。
*   **混合搜索机制**：结合了图遍历（显式关系）和向量相似度搜索（隐式语义关系）。

### 3. 实验设计：数据集、Benchmark 与对比方法
论文通过三个维度的实验验证了框架的有效性：
*   **生物学有效性分析**：使用 `metapath2vec` 算法在图谱上进行随机游走，评估蛋白质家族聚类、药物-疾病关联恢复和通路同义性。对比了 `Bioteque` 等现有资源。
*   **LLM 基准测试**：
    *   **Cypher 生成**：测试了 GPT-4o、Claude 3.5、DeepSeek R1 等模型生成复杂图查询的能力（50 个案例）。
    *   **生物医学问答**：使用 100 个内部策划的真/假问题和外部的 `GeneTuring` 基准测试。对比了独立 LLM、联网搜索模型（如 Perplexity Sonar）与 CROssBAR-LLM。
*   **预测建模实验**：开发了基于异构图变换器（HGT）的 **ProtHGT** 模型，用于蛋白质功能（GO 条目）预测。在 `DeepHGAT` 数据集上进行 Benchmark，对比了 `DeepHGAT`、`PSPGO` 及多种序列模型。

### 4. 资源与算力
*   **算力说明**：论文提到系统部署在配备 Docker 容器化的虚拟专用服务器（VPS）上。
*   **具体细节**：文中**未明确说明**训练 ProtHGT 模型或生成大规模嵌入的具体 GPU 型号（如 A100/H100）及确切的训练时长。但提到了使用了预训练的 3B 参数 ESM2 模型和 2.5B 参数的 Nucleotide Transformer。

### 5. 实验数量与充分性
*   **实验规模**：论文涵盖了从基础的图结构验证到复杂的 LLM 问答，再到下游的深度学习预测任务。
*   **充分性评价**：实验设计较为**充分且多元化**。通过 50 个 Cypher 案例、100 个专业问答以及标准化的蛋白质功能预测 Benchmark，从定性和定量两个角度进行了评估。对比方法涵盖了当前最先进的闭源和开源模型，实验过程体现了客观性和公平性。

### 6. 主要结论与发现
*   **知识增强的优越性**：CROssBAR-LLM 在生物医学问答中的准确率（如 Gemini 1.5 Pro 达到 98%）远高于独立 LLM（通常处于随机猜测水平）。
*   **异构数据的价值**：在蛋白质功能预测中，利用 CROssBARv2 异构图信息的 ProtHGT 模型在所有 GO 子本体中均取得了 SOTA（最高 Fmax 分数），证明了多维关系对生物发现的重要性。
*   **发现新机制的能力**：通过“盲测”从头设计的虚拟分子，框架成功找回了其已知的药理学机制（如 MRI-1569 的双靶点作用），证明了其在药物研发中的潜力。

### 7. 优点（亮点）
*   **易用性极高**：通过自然语言接口降低了非编程人员使用复杂知识图谱的门槛。
*   **溯源透明**：丰富的元数据解决了生物医学数据中常见的“信任”问题。
*   **混合搜索**：将图谱的逻辑严谨性与向量嵌入的语义灵活性完美结合。
*   **高度可重现**：基于 `BioCypher` 的管道确保了数据的定期更新和社区扩展。

### 8. 不足与局限
*   **标识符映射挑战**：不同数据库间的交叉引用不完整或不一致可能导致部分数据丢失。
*   **疾病粒度问题**：不同疾病分类系统（如 Mondo, ICD）间的粒度差异可能影响复杂查询的精确度。
*   **依赖外部 API**：CROssBAR-LLM 的性能高度依赖于底层 LLM（如 GPT-4）的接口，存在成本和隐私合规的潜在限制。
*   **实时性限制**：虽然管道可自动化，但大规模图谱的完全重建和嵌入重新计算仍具有一定的时间滞后。

（完）
