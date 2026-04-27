---
title: "MetaMuse: A Multi-Agent AI System for Biomedical Metadata Curation and Harmonization"
title_zh: MetaMuse：一种用于生物医学元数据整理与协调的多智能体人工智能系统
authors: "Mittal, E., Litman, E., Myers, T., Agarwal, V., Gopinath, A., Kassis, T."
date: 2026-04-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.12.718044v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用大语言模型的智能体系统，用于生物医学元数据整理
tldr: "MetaMuse是一个多智能体AI框架，旨在解决生物医学数据库（如GEO）中元数据不一致和非结构化的问题。该系统通过提取、逻辑验证和本体映射三个阶段自动处理非结构化数据。实验表明，MetaMuse在关键字段上的准确率超过95%，且能有效避免幻觉，为提高公共数据可发现性和研究可重复性提供了可扩展的解决方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: 公共生物医学数据库中非结构化元数据的不一致性严重限制了数据的可发现性和研究的可重复性。
method: 采用由大语言模型驱动的多智能体架构，通过Curator提取、Arbitrator逻辑校验和Normalizer本体映射三个阶段实现自动化处理。
result: "在GEO金标准数据集上实现了超过95%的整理准确率，并展示了良好的可扩展性和数据完整性保护。"
conclusion: MetaMuse为丰富公共数据仓库和加速数据驱动的科学发现提供了一个可审计、上下文感知且高效的自动化工具。
---

## 摘要
公共生物医学数据库（如 Gene Expression Omnibus, GEO）中不一致且非结构化的元数据严重限制了数据的可发现性和研究的可重复性。为解决这一问题，我们推出了 MetaMuse，这是一个模块化的多智能体人工智能框架，旨在自主提取、验证和标准化非结构化的生物医学元数据。该框架采用基于大语言模型智能体的三阶段架构，通过专门的“整理智能体”（Curator Agents）根据上下文提取特定目标元数据字段的候选值。一个集中的“仲裁智能体”（Arbitrator Agent）负责强制执行跨字段的逻辑一致性，以防止矛盾的注释。最后，“标准化智能体”（Normalizer Agent）利用领域特定的语义搜索模型（SapBERT）将这些自由文本候选值映射到正式的本体术语。我们在人工整理的 GEO 样本金标准数据集上评估了 MetaMuse，在关键目标元数据字段上实现了超过 95% 的整理准确率，并在包含 400 个样本的更广泛数据集上展示了强大的可扩展性。值得注意的是，MetaMuse 通过在证据模糊时默认采取保守的假阴性策略来避免数据幻觉，从而保持严格的数据完整性。通过提供一个完全可审计且具有上下文感知能力的整理流水线，MetaMuse 为丰富公共数据仓库和加速可重复的、数据驱动的科学发现提供了一个可扩展的解决方案。

## Abstract
Inconsistent and unstructured metadata in public biomedical repositories, such as the Gene Expression Omnibus (GEO), severely limits data discoverability and research reproducibility. To address this, we introduce MO_SCPLOWETAC_SCPLOWMO_SCPLOWUSEC_SCPLOW, a modular, multi-agent artificial intelligence framework designed to autonomously extract, validate, and standardize unstructured biomedical metadata. Operating through a three-stage architecture utilizing large language model agents, specialized CO_SCPLOWURATORC_SCPLOWAO_SCPLOWGENTSC_SCPLOW contextually extract candidate values for specific target metadata fields. A centralized AO_SCPLOWRBITRATORC_SCPLOWAO_SCPLOWGENTC_SCPLOW enforces cross-field logical consistency to prevent contradictory annotations. Finally, a NO_SCPLOWORMALIZERC_SCPLOWAO_SCPLOWGENTC_SCPLOW leveraging a domain-specific semantic search model (SapBERT) maps these free-text candidates to formal ontological terms. We evaluated MO_SCPLOWETAC_SCPLOWMO_SCPLOWUSEC_SCPLOW on a gold-standard dataset of manually curated GEO samples, achieving over 95% curation accuracy across key target metadata fields, and demonstrated robust scalability on a broader dataset of 400 samples. Notably, MO_SCPLOWETAC_SCPLOWMO_SCPLOWUSEC_SCPLOW avoids data hallucination by defaulting to conservative false negatives when evidence is ambiguous, thereby preserving strict data integrity. By providing a fully auditable and context-aware curation pipeline, MO_SCPLOWETAC_SCPLOWMO_SCPLOWUSEC_SCPLOW offers a scalable solution for enriching public data repositories and accelerating reproducible, data-driven scientific discovery.

---

## 论文详细总结（自动生成）

### MetaMuse：用于生物医学元数据整理与协调的多智能体 AI 系统总结

#### 1. 核心问题与整体含义
*   **研究动机**：生物医学研究面临严重的“可重复性危机”，其中一个关键原因是公共数据库（如 GEO）中的元数据质量参差不齐。
*   **核心问题**：大量的实验描述隐藏在非结构化的自由文本中，缺乏统一的标准和逻辑一致性（例如，性别字段可能被标记为“M”、“male”或“1”），导致数据难以被系统性检索、比较和重用。
*   **整体含义**：MetaMuse 旨在通过自动化框架，将这些杂乱的非结构化信息转化为符合 FAIR（可发现、可访问、互操作、可重用）原则的标准化本体术语，从而加速科学发现。

#### 2. 方法论
MetaMuse 采用了一个三阶段的模块化多智能体架构：
*   **数据摄取（Data Intake）**：从 GEO 和 PubMed 提取样本（GSM）、系列（GSE）和摘要信息，剔除无关字段（如联系方式），构建证据边界。
*   **预处理（Preprocessing）**：使用 **CuratorAgent**（基于 Gemini-2.5-flash）判断样本类型（原代样本 vs 细胞系），以确定后续需要提取的目标字段。
*   **条件处理（Conditional Processing）**：
    *   **提取（CuratorAgent）**：为每个元数据字段（如疾病、组织、治疗）分配专门的专家智能体，从原始文本中提取候选值，并提供选择理由。
    *   **仲裁（ArbitratorAgent）**：核心创新点。该智能体审查所有字段的逻辑一致性（例如，防止出现“肺癌细胞系”与“肝病”这种矛盾组合），通过迭代循环（最多 3 次）修正错误。
    *   **标准化（NormalizerAgent）**：利用 **SapBERT** 模型进行语义搜索，将自由文本映射到正式本体（如 MONDO, UBERON, ChEMBL）。

#### 3. 实验设计
*   **数据集**：
    *   **金标准验证集**：随机抽取 100 个 GEO 样本进行人工标注和对比。
    *   **扩展数据集**：400 个样本，用于评估系统的可扩展性。
*   **Benchmark（基准）**：以人工专家整理的结果为金标准。
*   **对比维度**：评估了整理准确率（Curation Accuracy）、标准化准确率（Normalization Accuracy）以及错误类型分布（假阳性 vs 假阴性）。

#### 4. 资源与算力
*   **模型使用**：主要依赖 Google 的 **Gemini-2.5-pro**（用于复杂推理）和 **Gemini-2.5-flash**（用于快速任务）。
*   **算力细节**：文中提到语义搜索部分使用了 **FAISS** 向量索引，并在有硬件支持时进行 **GPU 加速**。但未明确给出具体的 GPU 型号、数量或总训练/推理时长。

#### 5. 实验数量与充分性
*   **实验规模**：共对 500 个样本进行了深度评估。
*   **充分性**：实验覆盖了疾病、组织、生物体、性别、年龄等 10 多个关键生物医学字段。
*   **客观性**：通过对错误类型的细分（如区分“幻觉”和“漏检”），展示了系统在处理模糊证据时的保守策略。虽然 500 个样本相对于 GEO 百万级的规模较小，但作为框架验证已具备较强的代表性和说服力。

#### 6. 主要结论与发现
*   **高准确率**：在关键字段的整理上实现了 **>95%** 的准确率。
*   **拒绝幻觉**：系统表现出保守性，错误多为“假阴性”（未检出），极少出现“假阳性”（幻觉），这对于维护科学数据诚信至关重要。
*   **瓶颈所在**：实验发现，从文本提取信息（整理）相对容易，但将提取的信息准确映射到复杂的本体 ID（标准化）仍是主要挑战（如组织字段的标准化准确率从 97% 降至 66%）。
*   **可审计性**：系统为每个决策提供了完整的推理链和证据日志。

#### 7. 优点
*   **多智能体协作**：引入仲裁机制，解决了单模型难以处理的跨字段逻辑矛盾问题。
*   **上下文感知**：能够区分“研究背景中提到的疾病”与“样本实际患有的疾病”。
*   **透明度高**：提供全流程审计追踪，符合可重复科学的要求。
*   **模块化设计**：允许在不重新训练模型的情况下更换底层本体或 LLM。

#### 8. 不足与局限
*   **标准化难题**：对于高度专业化或复合型的术语（如特定的细胞亚型），现有的语义搜索模型（SapBERT）仍存在映射偏差。
*   **源数据依赖**：如果原始上传的元数据过于稀疏或缺乏关联论文，系统性能会受限。
*   **应用范围**：目前仅针对 GEO 进行了深度优化，适配其他数据库（如 SRA 或 ENA）可能需要额外的调整。

（完）
