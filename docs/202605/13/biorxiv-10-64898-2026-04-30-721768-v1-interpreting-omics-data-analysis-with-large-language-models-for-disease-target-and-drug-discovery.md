---
title: Interpreting Omics Data Analysis with Large Language Models for Disease Target and Drug Discovery
title_zh: 利用大语言模型解释组学数据分析以进行疾病靶点和药物发现
authors: "XU, Z., Chen, W., Ren, W., Xu, T., Amaechin, S., Khan, R., Chen, Y., Province, M., Payne, P., Li, F."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721768v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 大语言模型用于解释组学数据和疾病靶点发现
tldr: 本研究针对生物医学发现中组学数据分析与文献知识整合的难题，提出了Text-to-Target框架。该框架将大语言模型（LLM）的文本检索能力与数值组学分析相结合，通过模态感知融合技术，将候选目标划分为锚点、隐藏枢纽和新兴节点。在胰腺癌和阿尔茨海默症的评估中，该模型不仅生成了具有显著实验支持的靶点和策略组合，还确保了从检索到验证的全程可追溯性，为药物研发提供了高效且可解释的新路径。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在克服LLM检索缺乏定量证据以及纯组学分析缺乏生物学机制解释的局限性。
method: 开发了一种结合模式约束LLM检索与组学数据分析的Text-to-Target框架，并采用模态感知融合策略进行候选目标分类与传播。
result: 在PDAC和AD模型中识别出的靶点和策略在DepMap和CRISPRbrain等数据库中获得了显著的验证支持，并实现了端到端的审计追踪。
conclusion: 该框架证明了结合文献机制与组学证据的自动化架构在提高疾病靶点发现的可解释性和准确性方面的巨大潜力。
---

## 摘要
在生物医学科学发现中，综合文献中的先验知识是解释数值组学数据分析以进行疾病靶点识别和药物发现的重要组成部分。仅靠大语言模型（LLMs）可以快速从生物医学文本中检索疾病机制，但如果没有特定队列的定量证据，纯文本输出对于靶点和药物优先级排序来说过于笼统且不可靠。在此，我们提出了一种出处感知的“文本到靶点”（Text-to-Target）框架，该框架将模式约束的多模型 LLM 检索与数值组学数据分析相结合。关键设计是一个模态感知融合步骤：将候选对象划分为重叠支持的锚点（anchors）、仅检索的隐藏枢纽（hidden hubs）以及网络涌现的新颖节点（novelty nodes），然后在拓扑约束下传播到分阶段的假设和策略生成中。我们在阿尔茨海默病（AD）和胰腺导管腺癌（PDAC）中评估了该模型。在 PDAC 中，该工作流产生了一个平衡的 75 基因候选全集和 23 个策略组合，在靶点水平和策略水平上均获得了显著的 DepMap 支持。在 AD 中，更严格的候选控制产生了一个紧凑的 34 基因全集和 14 个策略；在扩展的 CRISPRbrain 注册库下，两个靶点水平轴均具有显著性，且具有很强的策略水平富集。在这两种疾病中，最终策略都保持了对候选池的完整出处闭环，实现了从检索产物到验证输出的端到端可审计性。这些结果支持了一种可迁移的发现架构，其中组学证据约束生物活性，LLM 检索扩展机制搜索空间，而网络感知融合保持了可解释性。该框架为双疾病靶点优先级排序提供了可重复的基础，并激发了通过智能体证据刷新循环实现文献与机制的持续一致性。

## Abstract
In biomedical scientific discovery, synthesizing prior knowledge from the literature is an essential component of interpreting numerical omics data analyses for disease target identification and drug discovery. Large language models (LLMs) alone can rapidly retrieve disease mechanisms from biomedical text, but text-only outputs are general and unreliable for target and drug prioritization without cohort-specific quantitative evidence. Herein, we propose a provenance-aware Text-to-Target framework that couples schema-constrained multi-model LLM retrieval with numeric omics data analysis. The key design is a modality-aware fusion step: candidates are partitioned into overlap-supported anchors, retrieval-only hidden hubs, and network-emergent novelty nodes, then propagated into staged hypothesis and strategy generation under topology constraints. We evaluate the model in Alzheimers disease (AD) and pancreatic ductal adenocarcinoma (PDAC). In PDAC, the workflow produced a balanced 75-gene candidate universe and a 23-strategy portfolio, with significant DepMap support at both target level and strategy level. In AD, stricter candidate controls yielded a compact 34-gene universe and 14 strategies; under an expanded CRISPRbrain registry, both target-level axes were significant, with strong strategy-level enrichment. Across both diseases, final strategies preserved full provenance closure to the candidate pool, enabling end-to-end auditability from retrieval artifacts to validation outputs. These results support a transferable discovery architecture in which omics evidence constrains biological activity, LLM retrieval expands mechanistic search space, and network-aware fusion preserves interpretability. The framework provides a reproducible basis for dual-disease target prioritization and motivates continuous literature-mechanism concordance with agentic evidence-refresh loops.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **Text-to-Target** 的创新框架，旨在通过大语言模型（LLM）与单细胞组学数据的深度融合，加速疾病靶点识别和药物发现。以下是对该论文的结构化总结：

### 1. 核心问题与研究动机
*   **核心问题**：在生物医学发现中，如何有效地将“数值型组学分析结果”与“文本型文献先验知识”整合。
*   **研究动机**：
    *   **组学分析的局限**：虽然能识别差异表达信号，但难以直接转化为具有生物学机制解释的优先靶点。
    *   **LLM 的局限**：虽然检索速度快，但容易产生幻觉，且缺乏针对特定患者队列的定量证据支持。
    *   **流程断层**：目前的精准医疗工作流在“计算分析”与“专家人工解释”之间存在严重的脱节，难以标准化且易遗漏关键信息。

### 2. 方法论：Text-to-Target 框架
该框架采用分阶段的集成循环，核心思想是“用组学证据约束生物活性，用 LLM 检索扩展机制空间”。
*   **双路提取**：
    *   **语言分支**：使用 GPT-5、Gemini 2.5-pro 和 DeepSeek-r1 等模型，通过模式约束（Schema-constrained）的提示词检索特定细胞类型的靶点、通路和机制。
    *   **组学分支**：利用 **PathFinder**（一种基于图变换器的网络推理引擎）将单细胞差异表达（DEG）信号转化为加权的生物信号图。
*   **模态感知融合（象限构造）**：将候选基因分为三个象限：
    *   **Q1 (Anchors)**：LLM 检索与网络分析共同支持的锚点。
    *   **Q2 (Hidden Hubs)**：仅由 LLM 检索支持的隐藏枢纽。
    *   **Q3 (Novelty)**：仅由网络分析涌现的新颖节点，通过计算其与 Q1 的“桥接”能力进行排序。
*   **假设与策略生成**：
    *   **机制升级**：LLM 首先基于 Q1 和 Q2 构建基础机制，随后在显式拓扑约束下插入 Q3 节点，形成升级后的机制序列。
    *   **策略设计**：从机制序列中选择 2-4 个靶点组合，生成具有协同效应的药物策略。

### 3. 实验设计
*   **测试场景**：
    *   **胰腺导管腺癌 (PDAC)**：高对比度基准，关注恶性上皮细胞与微环境的信号。
    *   **阿尔茨海默病 (AD)**：低对比度基准，关注神经免疫耦合和胶质细胞状态转换。
*   **基准测试 (Benchmark)**：
    *   **PDAC 验证**：使用 **DepMap** 依赖性数据，评估靶点和策略的脆弱性得分。
    *   **AD 验证**：使用 **CRISPRbrain** 筛选注册库，评估基因在神经变性背景下的功能影响。
*   **对比方法**：主要通过与随机生成的同等规模基因集进行**置换检验 (Permutation Testing)** 来评估显著性。

### 4. 资源与算力
*   **模型参数**：PathFinder 使用了 6 层 Transformer、8 个注意力头，隐藏层维度为 16。
*   **训练细节**：学习率 $1 \times 10^{-5}$，Batch Size 为 4，训练 25 个 Epoch。
*   **算力说明**：论文**未明确说明**具体的 GPU 型号和数量，但提到使用了多个前沿 LLM 家族（GPT、Gemini、DeepSeek）的 API 进行检索和推理。

### 5. 实验数量与充分性
*   **实验规模**：
    *   在 PDAC 中生成了 75 个候选基因和 23 个策略。
    *   在 AD 中生成了 34 个候选基因和 14 个策略。
*   **充分性评价**：实验设计较为充分。通过双疾病模型测试了框架的可迁移性；使用了大规模的独立功能基因组学数据库（DepMap, CRISPRbrain）进行验证；采用了严格的统计学置换检验（5000 次抽样）来确保结果的非随机性。

### 6. 主要结论与发现
*   **验证结果**：在 PDAC 中，策略水平的验证达到了极高的显著性（$p = 0.00019996$），56.5% 的策略具有局部显著性。在 AD 中，扩展后的验证同样显示出显著的策略富集。
*   **机制发现**：识别了 PDAC 中的 EGFR-STAT3 轴和 AD 中的 STAT3-C3 轴等关键控制骨架，这些发现与最新的独立研究高度一致。
*   **可追溯性**：证明了从最初的文献检索到最终的验证输出，整个过程具有完整的“出处闭环”（Provenance Closure），实现了端到端的可审计性。

### 7. 优点与亮点
*   **出处感知 (Provenance-aware)**：每个生成的策略都能追溯到具体的组学证据或文献来源，解决了 AI 发现中的“黑箱”问题。
*   **新颖性挖掘**：通过 Q3 象限和桥接分析，系统性地引入了文献中未直接提及但组学数据支持的新靶点。
*   **交互式可视化**：提供了药物使能的 concordance 网络，将信号通路、定量权重和药物证据集成在可交互的界面中。

### 8. 不足与局限
*   **模态局限**：目前主要依赖转录组数据，尚未充分整合蛋白质组学、代谢组学或空间组学信息。
*   **因果性验证**：虽然有统计学关联，但尚未在湿实验中直接验证生成策略的因果效应。
*   **“共识惯性” (Canonical Inertia)**：LLM 倾向于保留广泛认可的基序，可能会忽略特定治疗压力下发生的上下文相关重连（如耐药机制中的旁路激活）。
*   **动态更新风险**：自动化循环可能引入检索噪声或引用泄露，需要更严格的治理和版本控制策略。

（完）
