---
title: "CROssBARv2: A Unified Computational Framework for Heterogeneous Biomedical Data Representation and LLM-Driven Exploration"
title_zh: CROssBARv2：一种用于异构生物医学数据表示和 LLM 驱动探索的统一计算框架
authors: "Sen, B., Ulusoy, E., Darcan, M., Ergun, M., Lobentanzer, S., Rifaioglu, A. S., Turei, D., Saez-Rodriguez, J., Dogan, T."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.12.718028v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 异构生物医学数据和LLM驱动探索的统一框架
tldr: CROssBARv2是一个统一的生物医学数据集成平台，旨在解决数据碎片化和元数据不均的问题。它通过构建包含本体、元数据和深度学习嵌入的大规模知识图谱，整合了异构生物医学资源。该平台集成了CROssBAR-LLM，利用知识图谱增强大模型问答的准确性并减少幻觉，支持药物重定位和蛋白质功能预测等任务，为生物医学发现提供了可扩展且AI就绪的基础设施。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-001.webp\", \"caption\": \"Figure 1. Overview of the CROssBARv2 workflow. (a) Integration of data from 34 well-established sources covering various biomedical domains. (b) Automatic retrieval, standardisation, and integration of source data using modular adapter scripts. (c) CROssBARv2 KG schema, comprising 14 node types and 51 edge types. (d) Storage of the KG in a Neo4j graph database, along with rich metadata and node embeddings computed using deep learning-based methods. (e) Execution of the CROssBAR-LLM workflow, which translates natural language queries into Cypher, executes the queries on KG, and synthesizes structured results into natural language responses; also supports vector-based similarity search.\", \"page\": 6, \"index\": 1, \"width\": 890, \"height\": 1158}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-002.webp\", \"caption\": \"Figure 2. Exploration of the CROssBARv2 KG through three complementary interfaces. a) Natural language querying via the CROssBAR-LLM tool enables users to interact with the KG through questions written in plain language, supported by a backend that connects large language models with the Neo4j database (https://crossbarv2.hubiodatalab.com/llm). b) Programmatic access\", \"page\": 7, \"index\": 2, \"width\": 875, \"height\": 1252}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-003.webp\", \"caption\": \"Figure 5. CROssBAR-LLM benchmarking performance results on Cypher query generation and biomedical question answering tasks. (a) The number of correct Cypher queries produced by various LLMs utilised in CROssBAR-LLM (out of 50 cases). (b) The numbers of correct answers for standalone LLMs (striped bars) and CROssBAR-LLMs (solid bars) when answering in-house curated\", \"page\": 18, \"index\": 3, \"width\": 888, \"height\": 777}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-718028-v1/fig-004.webp\", \"caption\": \"Figure 6. Deep learning-based utilization of CROssBARv2 for biological relationship prediction. (a) Overview of Heterogeneous Graph Transformer (HGT) based ProtHGT model and its training on the CROssBARv2 knowledge graph for protein function prediction. (b) Protein function prediction performance evaluated on the DeepHGAT Human dataset using Fmax scores. ProtHGT models that utilise ESM2 and ProtT5 protein language models achieved top performance in all categories.\", \"page\": 20, \"index\": 4, \"width\": 888, \"height\": 1196}]"
motivation: 针对生物医学数据存储碎片化、模态特定且元数据不统一导致的集成分析与重复性难题。
method: 构建了一个富含溯源信息的知识图谱，结合标准化本体、向量嵌入及基于检索增强生成的CROssBAR-LLM问答系统。
result: 通过问答基准测试和蛋白质功能预测实验，证明了该框架在减少LLM幻觉和提升预测建模性能方面的有效性。
conclusion: CROssBARv2为假设生成和转化研究提供了一个用户友好、可扩展且支持AI驱动探索的统一计算框架。
---

## 摘要
生物医学发现受到碎片化、特定模态的存储库以及不均衡元数据的阻碍，这限制了综合分析、可访问性和可重复性。为了应对这些挑战，我们提出了 CROssBARv2，这是一个具有丰富溯源信息的生物医学数据与知识集成平台，它将异构来源统一为一个可维护、可扩展的系统。通过将多种数据类型整合到一个由标准化本体、丰富元数据和基于深度学习的向量嵌入所增强的广泛知识图谱中，CROssBARv2 减轻了研究人员在多个孤岛式数据库中检索的需求，并能促进包括预测建模和机制推理在内的下游任务，从而实现药物重定位和蛋白质功能预测等应用。该平台通过 CROssBAR-LLM 提供交互式图探索和基于嵌入的语义搜索，CROssBAR-LLM 是一个直观的自然语言问答系统，它将大语言模型（LLM）的输出锚定在底层知识图谱中，以缓解幻觉问题。我们通过以下方式评估了 CROssBARv2：(i) 多项用例分析，以测试生物学一致性和关系有效性；(ii) 知识增强的生物医学问答基准测试，将 CROssBAR-LLM 与通用 LLM 进行对比；以及 (iii) 利用 CROssBARv2 的异构结构进行蛋白质功能预测的深度学习预测建模实验。总的来说，CROssBARv2 提供了一个可扩展、AI 就绪且用户友好的基础，促进了假设生成、知识发现和转化研究。

## Abstract
Biomedical discovery is hindered by fragmented, modality-specific repositories and uneven metadata, limiting integrative analysis, accessibility, and reproducibility. To address these challenges, we present CROssBARv2, a provenance-rich biomedical data-and-knowledge integration platform that unifies heterogeneous sources into a maintainable, scalable system. By consolidating diverse data types into an extensive knowledge graph enriched with standardised ontologies, rich metadata, and deep learning based vector embeddings, CROssBARv2 alleviates the need for researchers to navigate multiple siloed databases and can facilitate downstream tasks, including predictive modelling and mechanistic reasoning, enabling applications such as drug repurposing and protein function prediction. The platform offers interactive graph exploration and embedding-based semantic search with CROssBAR-LLM, an intuitive natural language question-answering system that grounds large language model (LLM) outputs in the underlying knowledge graph to mitigate hallucinations. We assess CROssBARv2 through (i) multiple use-case analyses to test biological coherence and relational validity; (ii) knowledge-augmented biomedical question-answering benchmarks comparing CROssBAR-LLM against generalist LLMs; and (iii) a deep learning based predictive modelling experiment for protein function prediction leveraging the heterogeneous structure of CROssBARv2. Collectively, CROssBARv2 provides a scalable, AI-ready, and user-friendly foundation that facilitates hypothesis generation, knowledge discovery, and translational research.

---

## 论文详细总结（自动生成）

### CROssBARv2：异构生物医学数据表示与 LLM 驱动探索的统一计算框架总结

#### 1. 核心问题与整体含义（研究动机和背景）
生物医学发现目前面临的主要障碍是**数据碎片化**。生物知识散落在模态各异、元数据标准不一的孤岛式数据库中，导致集成分析困难、可重复性差。此外，虽然大语言模型（LLM）在生物医学领域展现了潜力，但其**幻觉问题**（生成虚假信息）和缺乏对专业结构化数据库的直接访问限制了其在严谨科研中的应用。CROssBARv2 旨在构建一个可维护、可扩展且富含溯源信息的集成平台，通过知识图谱（KG）统一异构数据，并利用 LLM 驱动直观的知识探索。

#### 2. 方法论：核心思想与关键技术
*   **核心思想**：将 34 个生物医学数据源整合为一个包含 14 种节点和 51 种边缘类型的异构知识图谱，并结合深度学习嵌入（Embeddings）实现语义搜索与图遍历的“混合搜索”。
*   **关键技术细节**：
    *   **数据集成流水线**：使用 `Pypath` 进行自动化数据检索，通过 `BioCypher` 框架确保符合 FAIR 原则（可查找、可访问、可互操作、可重用），最终存储于 `Neo4j` 图数据库。
    *   **多模态嵌入**：集成多种 SOTA 模型生成节点属性，如蛋白质（ESM2, ProtT5）、小分子（SELFormer）、基因（Nucleotide Transformer）、表型（node2vec）等。
    *   **CROssBAR-LLM**：采用 **Text-to-Cypher** 流程。用户输入自然语言问题，系统通过 Prompt Engineering 驱动 LLM 生成 Cypher 查询语句，在 Neo4j 中执行后，将结构化结果反馈给 LLM 总结为自然语言回答。
    *   **元数据增强**：每个边缘都包含来源、证据代码、置信度得分等属性，支持高可靠性的过滤分析。

#### 3. 实验设计：数据集、Benchmark 与对比方法
*   **生物学有效性验证**：使用 `metapath2vec` 算法在 KG 上进行随机游走，验证蛋白质家族、药物-疾病关联和通路同义性的聚类效果，并与 `Bioteque` 资源进行对比。
*   **LLM 基准测试**：
    *   **Cypher 生成**：测试了 50 个复杂查询（含多跳查询），对比了 GPT-4o、Claude 3.5、DeepSeek R1、Llama 3.1 等模型。
    *   **问答准确性**：使用 100 个内部策划的真/假问题和 50 个来自 `GeneTuring` 的外部基准问题，对比了独立 LLM、联网搜索 LLM（如 Perplexity Sonar）与 CROssBAR-LLM。
*   **预测建模**：开发了基于异构图变换器（HGT）的 `ProtHGT` 模型，在 `DeepHGAT` 人类数据集上进行蛋白质功能预测（GO 条目预测），对比了 `DeepHGAT`、`PSPGO` 等方法。

#### 4. 资源与算力
*   **算力说明**：论文提到系统部署在配备 Docker 容器化的虚拟专用服务器（VPS）上。
*   **具体细节**：文中**未明确列出**训练 `ProtHGT` 或运行 LLM 推理的具体 GPU 型号、数量及总训练时长。但提到了使用了参数量达 30 亿（3B）的 ESM2 模型和 25 亿（2.5B）的 Nucleotide Transformer 生成嵌入，这暗示了在预处理阶段使用了高性能计算资源。

#### 5. 实验数量与充分性
*   **实验规模**：涵盖了从图结构验证、LLM 性能评估到下游深度学习预测的多个维度。
*   **充分性评价**：实验设计较为全面。通过 34 个数据源的集成确保了数据的广度；通过与多种主流 LLM 和 SOTA 预测模型的对比确保了竞争力的客观性。特别是针对“多跳查询”的消融式分析，证明了大型模型在处理复杂逻辑时的优势。

#### 6. 主要结论与发现
*   **知识增强显著提升准确性**：在生物医学问答中，CROssBAR-LLM 的表现远超独立 LLM（准确率从随机水平提升至 90% 以上），有效抑制了幻觉。
*   **异构性助力预测**：利用 KG 的异构结构（通路、领域、相互作用），`ProtHGT` 在蛋白质功能预测的 Fmax 指标上达到了 SOTA 水平。
*   **混合搜索的威力**：通过向量相似性搜索，系统能为数据库中不存在的 *de novo*（新设计）分子找到潜在的生物学机制和靶点。

#### 7. 优点
*   **易用性高**：为非编程背景的生物学家提供了自然语言接口和交互式可视化浏览器。
*   **溯源严谨**：丰富的元数据和置信度得分解决了生物医学数据中常见的“不可信”问题。
*   **AI 就绪**：预计算的嵌入使得该 KG 可以直接作为机器学习模型的输入特征。

#### 8. 不足与局限
*   **标识符映射挑战**：不同数据库间的交叉引用不完整或不一致，可能导致部分数据在集成时丢失。
*   **疾病粒度差异**：不同本体（如 Mondo, KEGG）对疾病的分类粒度不同，可能影响复杂查询的精确度。
*   **实时性限制**：虽然有自动化流水线，但 KG 的更新仍依赖于定期重新构建，而非完全实时的动态更新。
*   **LLM 依赖**：Text-to-Cypher 的成功高度依赖于底层 LLM 的逻辑推理能力，对于极度复杂的长链条推理仍存在失败风险。

（完）
