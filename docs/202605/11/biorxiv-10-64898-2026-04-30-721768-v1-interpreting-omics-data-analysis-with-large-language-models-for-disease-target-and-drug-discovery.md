---
title: Interpreting Omics Data Analysis with Large Language Models for Disease Target and Drug Discovery
title_zh: 利用大语言模型解释组学数据分析以进行疾病靶点和药物发现
authors: "XU, Z., Chen, W., Ren, W., Xu, T., Amaechin, S., Khan, R., Chen, Y., Province, M., Payne, P., Li, F."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721768v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 大语言模型用于疾病靶点发现和数值组学数据分析
tldr: 本研究针对生物医学发现中组学数据分析缺乏文献背景、而大语言模型（LLM）缺乏定量证据的问题，提出了一种名为“Text-to-Target”的溯源感知框架。该框架通过模态感知融合步骤，将LLM的多模型检索与数值组学分析相结合，通过拓扑约束生成分阶段假设。在阿尔茨海默病和胰腺癌中的评估显示，该方法能有效识别具有生物学意义的靶点和策略，并确保从检索到验证的全过程可审计，为疾病靶点发现提供了可解释且可重复的新架构。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决LLM在靶点发现中缺乏定量证据以及组学分析缺乏文献机制支持的局限性。
method: 提出Text-to-Target框架，通过模态感知融合将LLM检索与组学数据结合，并利用拓扑约束进行假设生成。
result: 在胰腺癌和阿尔茨海默病中成功识别出受DepMap和CRISPRbrain支持的候选基因及治疗策略。
conclusion: 该框架通过融合文献检索与组学证据，为疾病靶点优先排序提供了一种可解释、可审计且可迁移的发现架构。
---

## 摘要
在生物医学科学发现中，综合文献中的先验知识是解释数值组学数据分析以进行疾病靶点识别和药物发现的重要组成部分。仅靠大语言模型（LLMs）可以快速从生物医学文本中检索疾病机制，但如果没有特定队列的定量证据，纯文本输出对于靶点和药物优先级排序来说过于笼统且不可靠。在此，我们提出了一种出处感知的“文本到靶点”（Text-to-Target）框架，该框架将模式约束的多模型 LLM 检索与数值组学数据分析相结合。关键设计是一个模态感知融合步骤：将候选对象划分为重叠支持的锚点（anchors）、仅检索的隐藏枢纽（hidden hubs）以及网络涌现的新颖节点（novelty nodes），然后在拓扑约束下传播到分阶段的假设和策略生成中。我们在阿尔茨海默病（AD）和胰腺导管腺癌（PDAC）中评估了该模型。在 PDAC 中，该工作流产生了一个平衡的 75 基因候选全集和 23 个策略组合，在靶点水平和策略水平上均获得了显著的 DepMap 支持。在 AD 中，更严格的候选控制产生了一个紧凑的 34 基因全集和 14 个策略；在扩展的 CRISPRbrain 注册库下，两个靶点水平轴均具有显著性，且具有很强的策略水平富集。在这两种疾病中，最终策略都保持了对候选池的完整出处闭环，实现了从检索产物到验证输出的端到端可审计性。这些结果支持了一种可迁移的发现架构，其中组学证据约束生物活性，LLM 检索扩展机制搜索空间，而网络感知融合保持了可解释性。该框架为双疾病靶点优先级排序提供了可重复的基础，并激发了通过智能体证据刷新循环实现文献与机制的持续一致性。

## Abstract
In biomedical scientific discovery, synthesizing prior knowledge from the literature is an essential component of interpreting numerical omics data analyses for disease target identification and drug discovery. Large language models (LLMs) alone can rapidly retrieve disease mechanisms from biomedical text, but text-only outputs are general and unreliable for target and drug prioritization without cohort-specific quantitative evidence. Herein, we propose a provenance-aware Text-to-Target framework that couples schema-constrained multi-model LLM retrieval with numeric omics data analysis. The key design is a modality-aware fusion step: candidates are partitioned into overlap-supported anchors, retrieval-only hidden hubs, and network-emergent novelty nodes, then propagated into staged hypothesis and strategy generation under topology constraints. We evaluate the model in Alzheimers disease (AD) and pancreatic ductal adenocarcinoma (PDAC). In PDAC, the workflow produced a balanced 75-gene candidate universe and a 23-strategy portfolio, with significant DepMap support at both target level and strategy level. In AD, stricter candidate controls yielded a compact 34-gene universe and 14 strategies; under an expanded CRISPRbrain registry, both target-level axes were significant, with strong strategy-level enrichment. Across both diseases, final strategies preserved full provenance closure to the candidate pool, enabling end-to-end auditability from retrieval artifacts to validation outputs. These results support a transferable discovery architecture in which omics evidence constrains biological activity, LLM retrieval expands mechanistic search space, and network-aware fusion preserves interpretability. The framework provides a reproducible basis for dual-disease target prioritization and motivates continuous literature-mechanism concordance with agentic evidence-refresh loops.

---

## 论文详细总结（自动生成）

这篇论文提出了一种名为 **“Text-to-Target”** 的溯源感知框架，旨在通过大语言模型（LLM）与数值组学数据的深度融合，解决生物医学发现中“数据缺乏机制解释”与“模型缺乏定量证据”的双重难题。

以下是对该论文的结构化深入总结：

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：在疾病靶点和药物发现中，传统的**数值组学分析**（如差异表达分析）虽然能提供定量证据，但往往缺乏文献背景支持，难以解释生物学机制；而**大语言模型（LLM）**虽然能快速检索文献知识，但其输出往往过于笼统、存在幻觉，且缺乏特定患者队列的定量数据支持。
*   **研究动机**：建立一种能够将“文献驱动的定性知识”与“组学驱动的定量证据”有机结合的架构，实现可解释、可审计且具有生物学意义的靶点优先级排序。

### 2. 论文提出的方法论：Text-to-Target 框架
该框架的核心思想是通过**模态感知融合**和**拓扑约束**来生成假设。
*   **多模型 LLM 检索**：利用多个 LLM（如 GPT-4 等）在模式约束（Schema-constrained）下从生物医学文本中提取疾病相关的分子机制。
*   **数值组学分析**：对特定疾病队列的组学数据进行处理，识别具有统计学意义的差异表达基因或蛋白。
*   **模态感知融合（关键步骤）**：将候选基因划分为三类：
    *   **锚点（Anchors）**：组学证据与 LLM 检索共同支持的节点。
    *   **隐藏枢纽（Hidden Hubs）**：仅由 LLM 检索提供，但在生物网络中起到关键连接作用。
    *   **新颖节点（Novelty Nodes）**：通过网络拓扑结构涌现出的、可能具有潜在价值的新节点。
*   **分阶段假设生成**：在拓扑约束下，将上述节点传播并转化为分阶段的生物学假设和治疗策略。
*   **出处感知（Provenance-aware）**：确保从最初的检索产物到最终的验证输出，每一步都有据可查，实现端到端的审计。

### 3. 实验设计
*   **应用场景**：选择了两种极具挑战性的疾病进行验证：**胰腺导管腺癌（PDAC）**和**阿尔茨海默病（AD）**。
*   **验证基准（Benchmark）**：
    *   **PDAC**：使用 **DepMap**（癌细胞依赖性图谱）数据验证候选基因的必需性。
    *   **AD**：使用 **CRISPRbrain** 注册库验证基因在神经元中的功能影响。
*   **对比维度**：在靶点水平（单个基因）和策略水平（药物-靶点组合）上分别评估富集显著性和生物学相关性。

### 4. 资源与算力
*   **算力说明**：论文摘要和提取文本中**未明确说明**具体的 GPU 型号、数量或训练时长。
*   **技术栈暗示**：由于采用了“多模型 LLM 检索”，推测主要依赖于现有商业或开源大模型的 API 调用（如 OpenAI 或 Anthropic 的模型），而非从头训练大型基础模型。

### 5. 实验数量与充分性
*   **实验规模**：
    *   在 **PDAC** 中生成了 75 个候选基因和 23 个策略组合。
    *   在 **AD** 中生成了 34 个候选基因和 14 个策略。
*   **充分性评价**：实验覆盖了癌症和神经退行性疾病两大领域，展示了框架的**可迁移性**。通过与 DepMap 和 CRISPRbrain 等独立第三方实验数据库对比，验证了结果的客观性。通过将候选池分类（锚点、枢纽、新颖节点）并进行消融式分析，证明了融合模态的必要性。

### 6. 论文的主要结论与发现
*   **有效性**：Text-to-Target 框架能有效识别受实验数据支持的候选靶点。在 PDAC 和 AD 中，最终生成的策略在靶点和策略水平均表现出显著的生物学富集。
*   **可审计性**：实现了从文献检索到验证输出的完整“出处闭环”，解决了 LLM 在科学发现中“黑盒化”的问题。
*   **机制扩展**：LLM 检索成功扩展了机制搜索空间（隐藏枢纽），而组学证据则有效约束了生物活性范围，防止了搜索空间的盲目扩张。

### 7. 优点（亮点）
*   **双向约束**：巧妙地用组学数据“锚定”LLM 的发散性，同时用 LLM “激活”组学数据的静态关联。
*   **拓扑感知**：引入网络拓扑约束，使得发现过程不仅仅是简单的交集运算，而是具有系统生物学深度的推理。
*   **端到端可审计**：在严谨的生物医学领域，这种可追溯性对于药物研发的决策至关重要。

### 8. 不足与局限
*   **依赖先验知识**：LLM 的检索质量受限于现有文献的覆盖范围，对于完全未被报道的极新机制可能仍存在局限。
*   **验证库限制**：虽然使用了 DepMap 和 CRISPRbrain，但这些基准数据库本身也存在细胞系局限性或组织特异性偏差。
*   **实时性挑战**：论文提到了“智能体证据刷新循环”，但在实际应用中，如何实时同步最新的科研进展与组学发现仍具有工程难度。

（完）
