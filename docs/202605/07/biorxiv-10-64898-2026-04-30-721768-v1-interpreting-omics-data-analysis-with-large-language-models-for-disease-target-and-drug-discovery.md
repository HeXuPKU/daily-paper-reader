---
title: Interpreting Omics Data Analysis with Large Language Models for Disease Target and Drug Discovery
title_zh: 利用大语言模型解释组学数据分析以进行疾病靶点和药物发现
authors: "XU, Z., Chen, W., Ren, W., Xu, T., Amaechin, S., Khan, R., Chen, Y., Province, M., Payne, P., Li, F."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721768v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 大语言模型与数值组学数据分析集成用于疾病靶点发现
tldr: 本研究提出Text-to-Target框架，旨在解决生物医学发现中组学数据分析与文献知识整合的难题。该框架通过大语言模型（LLM）检索与数值组学分析的模态感知融合，将候选目标分为锚点、隐藏枢纽和新颖节点，并在拓扑约束下生成假设。在阿尔茨海默症和胰腺癌的验证中，该方法显著提升了靶点识别的准确性与可解释性，为药物研发提供了端到端的可审计路径。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的组学分析缺乏文献背景支持，而纯LLM检索缺乏定量证据，需要结合两者以提高药物靶点发现的准确性。
method: 提出Text-to-Target框架，通过模式约束的多模型LLM检索与组学数据融合，利用拓扑约束进行候选基因分类和策略生成。
result: 在胰腺癌和阿尔茨海默症中成功识别出具有显著生物学支持的候选基因和治疗策略，并实现了全过程的可追溯性。
conclusion: 该框架通过组学证据约束和LLM机制扩展，为疾病靶点优先排序提供了一种可解释、可重复且可审计的自动化发现方法。
---

## 摘要
在生物医学科学发现中，综合文献中的先验知识是解释数值组学数据分析以进行疾病靶点识别和药物发现的关键组成部分。虽然大语言模型（LLMs）能够快速从生物医学文本中检索疾病机制，但如果没有特定队列的定量证据，仅靠文本输出对于靶点和药物的优先级排序往往过于笼统且不可靠。在此，我们提出了一种具有溯源意识的“文本到靶点”（Text-to-Target）框架，该框架将受模式约束的多模型 LLM 检索与数值组学数据分析相结合。其核心设计是一个模态感知的融合步骤：将候选对象划分为重叠支持的锚点（anchors）、仅检索到的隐藏枢纽（hidden hubs）以及网络涌现的新颖节点（novelty nodes），然后在拓扑约束下将其传播到分阶段的假设和策略生成中。我们在阿尔茨海默病（AD）和胰腺导管腺癌（PDAC）中对该模型进行了评估。在 PDAC 中，该工作流产生了一个包含 75 个基因的平衡候选空间和 23 个策略组合，在靶点水平和策略水平上均获得了显著的 DepMap 支持。在 AD 中，更严格的候选控制产生了一个包含 34 个基因的紧凑空间和 14 个策略；在扩展的 CRISPRbrain 注册库下，两个靶点水平轴均具有显著性，且具有较强的策略水平富集。在这两种疾病中，最终策略都保持了对候选池的完整溯源闭环，实现了从检索产物到验证输出的端到端可审计性。这些结果支持了一种可迁移的发现架构，其中组学证据约束了生物活性，LLM 检索扩展了机制搜索空间，而网络感知融合保留了可解释性。该框架为双疾病靶点优先级排序提供了可重复的基础，并激发了通过智能体证据刷新循环实现文献与机制持续一致性的动力。

## Abstract
In biomedical scientific discovery, synthesizing prior knowledge from the literature is an essential component of interpreting numerical omics data analyses for disease target identification and drug discovery. Large language models (LLMs) alone can rapidly retrieve disease mechanisms from biomedical text, but text-only outputs are general and unreliable for target and drug prioritization without cohort-specific quantitative evidence. Herein, we propose a provenance-aware Text-to-Target framework that couples schema-constrained multi-model LLM retrieval with numeric omics data analysis. The key design is a modality-aware fusion step: candidates are partitioned into overlap-supported anchors, retrieval-only hidden hubs, and network-emergent novelty nodes, then propagated into staged hypothesis and strategy generation under topology constraints. We evaluate the model in Alzheimer's disease (AD) and pancreatic ductal adenocarcinoma (PDAC). In PDAC, the workflow produced a balanced 75-gene candidate universe and a 23-strategy portfolio, with significant DepMap support at both target level and strategy level. In AD, stricter candidate controls yielded a compact 34-gene universe and 14 strategies; under an expanded CRISPRbrain registry, both target-level axes were significant , with strong strategy-level enrichment. Across both diseases, final strategies preserved full provenance closure to the candidate pool, enabling end-to-end auditability from retrieval artifacts to validation outputs. These results support a transferable discovery architecture in which omics evidence constrains biological activity, LLM retrieval expands mechanistic search space, and network-aware fusion preserves interpretability. The framework provides a reproducible basis for dual-disease target prioritization and motivates continuous literature-mechanism concordance with agentic evidence-refresh loops.

---

## 论文详细总结（自动生成）

这篇论文提出了一种名为 **Text-to-Target** 的创新框架，旨在通过大语言模型（LLM）与数值组学数据的深度融合，提升疾病靶点识别和药物发现的准确性与可解释性。以下是对该论文的结构化总结：

### 1. 论文的核心问题与整体含义（研究动机和背景）
在生物医学研究中，研究者面临两个主要挑战：
*   **组学数据的局限性：** 纯数值组学分析（如转录组学）虽然能提供特定队列的定量证据，但往往缺乏生物学机制的上下文解释，难以直接转化为临床靶点。
*   **LLM 的局限性：** 虽然 LLM 能够快速检索海量文献知识，但其输出往往过于笼统，且在缺乏定量证据支持时容易产生“幻觉”或给出不可靠的建议。
*   **核心动机：** 建立一种能够将“文献先验知识”与“实验定量证据”无缝整合的自动化路径，实现可审计、高置信度的靶点优先级排序。

### 2. 论文提出的方法论：Text-to-Target 框架
该框架的核心思想是**“模态感知融合”**与**“拓扑约束生成”**，具体流程如下：
*   **模式约束的多模型检索：** 使用多个 LLM（如 GPT-4 等）在预定义的生物医学模式（Schema）约束下，从文献中提取与疾病相关的机制和候选基因。
*   **数值组学分析：** 对特定疾病的组学数据进行差异表达、网络分析等常规处理。
*   **模态感知融合（核心步骤）：** 将候选基因划分为三类：
    1.  **锚点（Anchors）：** 文献支持且组学数据显著的基因。
    2.  **隐藏枢纽（Hidden Hubs）：** 仅由文献检索到，但在生物网络中处于关键位置的基因。
    3.  **新颖节点（Novelty Nodes）：** 仅由组学数据驱动或通过网络拓扑涌现出的新基因。
*   **拓扑约束下的假设生成：** 在生物分子网络的拓扑约束下，利用 LLM 生成分阶段的生物学假设和治疗策略。
*   **溯源意识（Provenance-aware）：** 确保从最初的检索条目到最终的验证输出，每一步都有据可查，形成闭环审计路径。

### 3. 实验设计
论文在两种截然不同的疾病模型上验证了框架的通用性：
*   **胰腺导管腺癌（PDAC）：** 侧重于肿瘤学，利用 **DepMap**（癌细胞系依赖性图谱）作为金标准来验证识别出的靶点是否对癌细胞生存至关重要。
*   **阿尔茨海默病（AD）：** 侧重于神经退行性疾病，利用 **CRISPRbrain** 数据库作为基准，验证靶点在神经元功能中的作用。
*   **对比维度：** 评估了靶点水平（Target-level）的准确性和策略水平（Strategy-level）的富集程度。

### 4. 资源与算力
*   **算力说明：** 论文中未明确详细列出具体的 GPU 型号、数量或训练时长。
*   **资源使用：** 框架主要依赖于现有的预训练大语言模型（通过 API 或本地部署）以及标准的生物信息学处理流程。其核心贡献在于算法架构和多模态数据的整合逻辑，而非从头训练大型模型。

### 5. 实验数量与充分性
*   **实验覆盖：** 涵盖了癌症（PDAC）和神经系统疾病（AD）两大领域，证明了框架的跨学科迁移能力。
*   **数据规模：** 在 PDAC 中生成了 75 个候选基因和 23 个策略组合；在 AD 中生成了 34 个基因和 14 个策略。
*   **充分性评价：** 实验设计较为充分，通过与 DepMap 和 CRISPRbrain 等独立第三方大规模实验数据库对比，提供了客观的统计学支持（显著性分析），证明了结果并非偶然。

### 6. 论文的主要结论与发现
*   **高准确性：** 在 PDAC 和 AD 中，识别出的靶点均获得了显著的实验数据支持。
*   **发现新机制：** 框架不仅找回了已知的“锚点”基因，还通过“隐藏枢纽”和“新颖节点”发现了潜在的新治疗路径。
*   **端到端可审计性：** 成功实现了从文献检索到策略生成的全过程溯源，解决了 LLM 在科学发现中“黑盒”输出的问题。
*   **协同效应：** 证明了组学证据能有效约束 LLM 的搜索空间，而 LLM 能显著扩展组学数据的解释深度。

### 7. 优点（亮点）
*   **分类精细：** 将候选基因分为锚点、隐藏枢纽和新颖节点，这种分类方法非常符合生物医学专家的直觉。
*   **可解释性强：** 强调溯源（Provenance），使得 AI 生成的假设可以被人类科学家审核和验证。
*   **框架通用：** 不局限于特定疾病，展示了在肿瘤和神经科学领域的双重有效性。

### 8. 不足与局限
*   **LLM 依赖性：** 结果的质量高度依赖于底层 LLM 的性能和所使用的文献数据库的覆盖面。
*   **文献偏差：** 如果某些罕见疾病的文献极少，LLM 检索部分可能会失效，导致框架退化为纯组学分析。
*   **动态更新挑战：** 虽然提到了智能体证据刷新循环，但在如何实时处理最新发表的相互矛盾的文献方面，仍有待进一步探索。
*   **实验验证：** 虽然有数据库支持，但缺乏针对新发现靶点的直接湿实验（In vitro/In vivo）验证。

（完）
