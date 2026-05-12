---
title: Interpreting Omics Data Analysis with Large Language Models for Disease Target and Drug Discovery
title_zh: 利用大语言模型解释组学数据分析以进行疾病靶点和药物发现
authors: "XU, Z., Chen, W., Ren, W., Xu, T., Amaechin, S., Khan, R., Chen, Y., Province, M., Payne, P., Li, F."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721768v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于解释组学数据和药物发现的大语言模型框架
tldr: 本研究针对生物医学发现中组学数据分析缺乏文献背景、而大语言模型（LLM）缺乏定量证据的问题，提出了一种名为“Text-to-Target”的溯源感知框架。该框架通过模态感知融合步骤，将LLM的多模型检索与数值组学分析相结合，利用拓扑约束生成分阶段假设。在阿尔茨海默病和胰腺癌中的评估显示，该方法能有效识别具有生物学意义的靶点和策略，并确保从检索到验证的全过程可审计，为疾病靶点发现提供了可解释且可重复的新架构。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决LLM在靶点发现中缺乏定量证据以及组学分析缺乏文献机制支持的局限性。
method: 提出Text-to-Target框架，通过模态感知融合将LLM检索与组学数据结合，并利用拓扑约束进行假设生成。
result: 在胰腺癌和阿尔茨海默病中成功识别出受DepMap和CRISPRbrain支持的候选基因及治疗策略，展现了显著的生物学相关性。
conclusion: 该框架通过融合文献与组学证据，为疾病靶点优先排序提供了一种可解释、可审计且可迁移的自动化发现方法。
---

## 摘要
在生物医学科学发现中，综合文献中的先验知识是解释数值组学数据分析以进行疾病靶点识别和药物发现的关键组成部分。仅靠大语言模型（LLMs）可以快速从生物医学文本中检索疾病机制，但如果没有特定队列的定量证据，纯文本输出在靶点和药物优先级排序方面往往过于笼统且不可靠。在此，我们提出了一种出处感知的“文本到靶点”（Text-to-Target）框架，该框架将受模式约束的多模型 LLM 检索与数值组学数据分析相结合。关键设计是一个模态感知融合步骤：将候选对象划分为重叠支持的锚点、仅检索的隐藏枢纽以及网络涌现的新颖节点，然后在拓扑约束下传播到阶段性的假设和策略生成中。我们在阿尔茨海默病（AD）和胰腺导管腺癌（PDAC）中评估了该模型。在 PDAC 中，该工作流产生了一个平衡的 75 基因候选全集和 23 个策略组合，在靶点水平和策略水平上均获得了显著的 DepMap 支持。在 AD 中，更严格的候选控制产生了一个紧凑的 34 基因全集和 14 个策略；在扩展的 CRISPRbrain 注册库下，两个靶点水平轴均具有显著性，且具有较强的策略水平富集。在这两种疾病中，最终策略都保持了对候选池的完整出处闭环，实现了从检索产物到验证输出的端到端可审计性。这些结果支持了一种可迁移的发现架构，其中组学证据约束生物活性，LLM 检索扩展机制搜索空间，而网络感知融合保持了可解释性。该框架为双疾病靶点优先级排序提供了可重复的基础，并激发了通过智能体证据刷新循环实现文献与机制的持续一致性。

## Abstract
In biomedical scientific discovery, synthesizing prior knowledge from the literature is an essential component of interpreting numerical omics data analyses for disease target identification and drug discovery. Large language models (LLMs) alone can rapidly retrieve disease mechanisms from biomedical text, but text-only outputs are general and unreliable for target and drug prioritization without cohort-specific quantitative evidence. Herein, we propose a provenance-aware Text-to-Target framework that couples schema-constrained multi-model LLM retrieval with numeric omics data analysis. The key design is a modality-aware fusion step: candidates are partitioned into overlap-supported anchors, retrieval-only hidden hubs, and network-emergent novelty nodes, then propagated into staged hypothesis and strategy generation under topology constraints. We evaluate the model in Alzheimers disease (AD) and pancreatic ductal adenocarcinoma (PDAC). In PDAC, the workflow produced a balanced 75-gene candidate universe and a 23-strategy portfolio, with significant DepMap support at both target level and strategy level. In AD, stricter candidate controls yielded a compact 34-gene universe and 14 strategies; under an expanded CRISPRbrain registry, both target-level axes were significant, with strong strategy-level enrichment. Across both diseases, final strategies preserved full provenance closure to the candidate pool, enabling end-to-end auditability from retrieval artifacts to validation outputs. These results support a transferable discovery architecture in which omics evidence constrains biological activity, LLM retrieval expands mechanistic search space, and network-aware fusion preserves interpretability. The framework provides a reproducible basis for dual-disease target prioritization and motivates continuous literature-mechanism concordance with agentic evidence-refresh loops.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **Text-to-Target** 的创新框架，旨在通过大语言模型（LLM）与单细胞组学数据的深度融合，加速疾病靶点识别和药物发现。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：生物医学发现面临两大瓶颈：一是组学数据分析（如差异表达分析）虽然能提供定量信号，但缺乏生物学机制的解释，且噪声大；二是 LLM 虽然擅长文献综述，但其输出往往过于笼统，且容易产生“幻觉”，缺乏特定患者队列的定量证据支持。
*   **研究动机**：如何将文献中的语义先验知识与组学中的定量约束有机结合，构建一个既有证据支持、又具备新颖性发现能力，且全过程可审计（Auditable）的自动化发现工作流。

### 2. 方法论：核心思想与关键技术
该框架采用分阶段的集成循环，核心步骤如下：
*   **双分支提取**：
    *   **语言分支（LLM Engine）**：使用 GPT-5、Gemini 2.5-pro 和 DeepSeek-r1 等前沿模型，通过受模式约束（Schema-constrained）的提示词，检索特定细胞类型的靶点、通路及文献引用。
    *   **组学分支（Omics Engine）**：利用 **PathFinder**（一种基于图变换器 Graph Transformer 的推理引擎），将单细胞差异表达信号转化为加权的生物信号网络。
*   **模态感知融合（象限划分）**：将候选基因分为四个象限（重点关注前三个）：
    *   **Q1 (Anchors)**：文献与组学共同支持的锚点。
    *   **Q2 (Hidden Hubs)**：仅文献支持但组学未直接体现的隐藏枢纽。
    *   **Q3 (Novelty)**：组学网络中涌现、但文献未直接提及的新颖节点（通过桥接分析排序）。
*   **假设升级与策略生成**：
    *   首先利用 Q1 和 Q2 构建基础机制。
    *   随后在拓扑约束下，将 Q3 节点插入信号流中，生成升级版的机制假设。
    *   最后基于这些机制设计多靶点联合治疗策略。
*   **溯源闭环**：所有输出均带有溯源标签，可追溯至具体的检索文献或网络拓扑证据。

### 3. 实验设计
*   **应用场景**：选择了两种极具代表性的疾病作为测试床：
    *   **胰腺导管腺癌 (PDAC)**：高对比度场景（恶性细胞 vs 正常导管细胞）。
    *   **阿尔茨海默病 (AD)**：低对比度、高度异质性场景（神经元与胶质细胞的复杂交互）。
*   **数据集**：来自 OmniCellTOSG 生态系统，包含 HCA、GEO 等单细胞/单细胞核测序资源。
*   **Benchmark（验证基准）**：
    *   **PDAC**：使用 **DepMap** 癌症依赖性图谱进行功能性验证。
    *   **AD**：使用 **CRISPRbrain** 筛选注册库进行验证。
*   **对比与评估**：通过置换检验（Permutation Testing）评估生成的靶点集和策略集是否比随机选择的基因集具有更显著的生物学效应。

### 4. 资源与算力
*   **算力说明**：论文提到了 PathFinder 模型的训练参数（6层 Transformer、8个注意力头、25个 Epoch、Batch Size 为 4 等），但**未明确说明具体的 GPU 型号、数量或总训练时长**。
*   **模型使用**：使用了多种商业和开源的前沿 LLM 接口进行集成检索。

### 5. 实验数量与充分性
*   **实验规模**：
    *   在 PDAC 中生成了 75 个候选基因和 23 个治疗策略。
    *   在 AD 中生成了 34 个候选基因和 14 个治疗策略。
*   **充分性评价**：实验设计较为充分。作者不仅在两种截然不同的疾病模型上验证了框架的迁移性，还进行了靶点水平和策略水平的双重统计验证。通过置换检验（通常进行 5000 次抽样）确保了结果的统计学意义，实验过程客观且具有说服力。

### 6. 主要结论与发现
*   **验证结果显著**：在 PDAC 中，生成的策略在 DepMap 验证中表现出极强的选择性脆弱性（p < 0.0002）。在 AD 中，扩展后的验证集也显示出显著的靶点富集。
*   **新颖性发现**：框架成功识别了如 MAX、MAZ 等在文献中未被广泛讨论但在组学网络中具有核心拓扑地位的新颖靶点。
*   **可审计性**：证明了端到端的溯源闭环是可行的，研究人员可以清晰地看到每一个治疗建议背后的文献依据和数值证据。

### 7. 优点
*   **证据融合创新**：通过象限法解决了文献先验与数据实证之间的冲突与互补问题。
*   **拓扑约束推理**：LLM 生成假设时受到 PathFinder 网络拓扑的严格约束，有效减少了幻觉。
*   **端到端溯源**：为 AI 辅助的科学发现提供了极高的透明度和可解释性，符合临床转化需求。
*   **可视化工具**：提供了交互式的证据网络图，方便研究人员进行直观的证据分级和筛选。

### 8. 不足与局限
*   **数据模态限制**：目前主要依赖转录组学（RNA-seq），尚未充分整合蛋白质组学、代谢组学或空间组学数据。
*   **“共识惯性”风险**：LLM 检索可能倾向于高频引用的经典机制，虽然通过 Q3 象限有所缓解，但仍可能存在对新兴、非共识机制的覆盖不足。
*   **因果性验证**：虽然有 DepMap 等支持，但框架本身生成的仍是关联性假设，最终仍需湿实验验证其因果效应。
*   **实时性挑战**：虽然提出了 7x24 小时智能体循环的设想，但目前文献更新与证据刷新的自动化程度仍有提升空间。

（完）
