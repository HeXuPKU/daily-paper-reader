---
title: Interpreting Omics Data Analysis with Large Language Models for Disease Target and Drug Discovery
title_zh: 利用大语言模型解读组学数据分析以进行疾病靶点和药物发现
authors: "XU, Z., Chen, W., Ren, W., Xu, T., Amaechin, S., Khan, R., Chen, Y., Province, M., Payne, P., Li, F."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721768v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 将大语言模型与数值组学数据分析结合用于疾病靶点发现
tldr: 该研究提出了一种名为 Text-to-Target 的框架，旨在解决大语言模型在生物医学发现中缺乏定量证据的问题。通过将多模型 LLM 检索与数值组学数据分析相结合，并利用模态感知融合技术（锚点、隐藏枢纽、新颖节点），该框架能生成具有高度可追溯性的疾病靶点和药物策略。在阿尔茨海默病和胰腺癌的评估中，该方法展现了显著的验证支持和端到端的可审计性，为药物研发提供了可重复的发现架构。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决纯文本 LLM 在靶点发现中缺乏定量证据，以及组学分析难以有效整合海量文献知识的挑战。
method: 提出一种来源感知的 Text-to-Target 框架，通过模式约束的 LLM 检索与组学数据融合，并利用拓扑约束进行分阶段假设生成。
result: 在胰腺癌和阿尔茨海默病中成功识别了关键基因和策略组合，并获得了 DepMap 和 CRISPRbrain 等数据库的显著验证支持。
conclusion: 该框架通过组学证据约束生物活性并利用 LLM 扩展搜索空间，实现了可解释且具有证据闭环的疾病靶点优先排序。
---

## 摘要
在生物医学科学发现中，综合文献中的先验知识是解读数值型组学数据分析以进行疾病靶点识别和药物发现的关键组成部分。仅靠大语言模型（LLMs）可以从生物医学文本中快速检索疾病机制，但如果没有特定队列的定量证据，仅文本输出对于靶点和药物优先级排序来说过于笼统且不可靠。在此，我们提出了一种具有溯源意识的 Text-to-Target 框架，该框架将模式约束的多模型 LLM 检索与数值型组学数据分析相结合。其核心设计是一个模态感知融合步骤：将候选对象划分为重叠支持的锚点（anchors）、仅检索的隐藏枢纽（hidden hubs）以及网络涌现的新颖节点（novelty nodes），然后在拓扑约束下传播到阶段性的假设和策略生成中。我们在阿尔茨海默病（AD）和胰腺导管腺癌（PDAC）中对该模型进行了评估。在 PDAC 中，该工作流产生了一个包含 75 个基因的平衡候选空间和 23 个策略组合，在靶点水平和策略水平上均获得了显著的 DepMap 支持。在 AD 中，更严格的候选筛选产生了一个包含 34 个基因的紧凑空间和 14 个策略；在扩展的 CRISPRbrain 注册库下，两个靶点水平轴均具有显著性，且具有较强的策略水平富集。在这两种疾病中，最终策略都保持了对候选池的完整溯源闭环，实现了从检索产物到验证输出的端到端可审计性。这些结果支持了一种可迁移的发现架构，其中组学证据约束生物活性，LLM 检索扩展机制搜索空间，而网络感知融合则保留了可解释性。该框架为双疾病靶点优先级排序提供了可重复的基础，并通过智能体证据刷新循环促进了文献与机制的持续一致性。

## Abstract
In biomedical scientific discovery, synthesizing prior knowledge from the literature is an essential component of interpreting numerical omics data analyses for disease target identification and drug discovery. Large language models (LLMs) alone can rapidly retrieve disease mechanisms from biomedical text, but text-only outputs are general and unreliable for target and drug prioritization without cohort-specific quantitative evidence. Herein, we propose a provenance-aware Text-to-Target framework that couples schema-constrained multi-model LLM retrieval with numeric omics data analysis. The key design is a modality-aware fusion step: candidates are partitioned into overlap-supported anchors, retrieval-only hidden hubs, and network-emergent novelty nodes, then propagated into staged hypothesis and strategy generation under topology constraints. We evaluate the model in Alzheimer's disease (AD) and pancreatic ductal adenocarcinoma (PDAC). In PDAC, the workflow produced a balanced 75-gene candidate universe and a 23-strategy portfolio, with significant DepMap support at both target level and strategy level. In AD, stricter candidate controls yielded a compact 34-gene universe and 14 strategies; under an expanded CRISPRbrain registry, both target-level axes were significant , with strong strategy-level enrichment. Across both diseases, final strategies preserved full provenance closure to the candidate pool, enabling end-to-end auditability from retrieval artifacts to validation outputs. These results support a transferable discovery architecture in which omics evidence constrains biological activity, LLM retrieval expands mechanistic search space, and network-aware fusion preserves interpretability. The framework provides a reproducible basis for dual-disease target prioritization and motivates continuous literature-mechanism concordance with agentic evidence-refresh loops.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **Text-to-Target** 的创新框架，旨在通过整合大语言模型（LLM）的语义先验知识与单细胞组学数据的定量证据，加速疾病靶点识别和药物发现。

以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心挑战**：生物医学发现面临“数据丰富但解释贫乏”的困境。组学数据能揭示表达差异，但难以直接转化为可测试的机制；而 LLM 虽然擅长文献综述，但容易产生幻觉，且缺乏针对特定患者队列的定量支持。
*   **研究动机**：目前的精准医疗工作流在“计算分析”与“专家人工解释”之间存在断层。作者希望建立一个自动化的、具有**来源感知（Provenance-aware）**能力的管道，将文本知识与数值证据无缝融合，生成可审计、高置信度的治疗策略。

### 2. 方法论
该框架由三个核心阶段组成：
*   **双模态提取**：
    *   **语言分支**：使用多模型集成（如 GPT-5、Gemini 2.5-pro、DeepSeek-r1），通过模式约束（Schema-constrained）的提示词，按细胞类型检索靶点、通路和机制。
    *   **组学分支**：利用 **PathFinder**（一种图变换器模型）分析单细胞/元细胞（Meta-cell）数据，将差异表达（DEG）信号转化为加权信号网络。
*   **象限候选融合（Candidate Fusion）**：
    将候选基因分为四个象限以保留证据来源：
    *   **Q1 (Anchors)**：LLM 检索与组学网络重叠的基因（双重支持）。
    *   **Q2 (Hidden Hubs)**：仅 LLM 检索到的基因（潜在的背景依赖靶点）。
    *   **Q3 (Novelty)**：仅组学网络发现的基因（通过“桥接分析”评估其与 Q1 的拓扑联系，挖掘新颖性）。
*   **分阶段假设生成**：
    先由 LLM 构建基础机制序列，再根据网络拓扑约束插入 Q3 新颖节点，最后生成多靶点组合策略（Strategy Portfolio）。

### 3. 实验设计
*   **测试场景**：
    *   **胰腺导管腺癌 (PDAC)**：高对比度基准，关注恶性上皮细胞与微环境的相互作用。
    *   **阿尔茨海默病 (AD)**：低对比度基准，关注神经胶质细胞状态转换和细胞间通讯。
*   **基准测试（Benchmark）**：
    *   **PDAC 验证**：使用 **DepMap** 依赖性数据，评估靶点的选择性脆弱性和依赖性。
    *   **AD 验证**：使用 **CRISPRbrain** 注册库，对比 AD 相关与非相关筛选的基因得分。
*   **对比方法**：主要通过**置换检验（Permutation Testing）**，将生成的策略与同等规模的随机基因组进行对比，以证明其统计显著性。

### 4. 资源与算力
*   **模型配置**：PathFinder 使用了 6 层 Transformer、8 个注意力头，隐藏层维度为 16。
*   **训练细节**：学习率 $1 \times 10^{-5}$，L2 权重衰减 $3 \times 10^{-7}$，训练 25 个 epoch。
*   **算力说明**：文中**未明确说明**具体的 GPU 型号、数量或总训练时长，但提到了使用了 GPT-5、Gemini 等商业 API 以及本地运行的图神经网络模型。

### 5. 实验数量与充分性
*   **实验规模**：针对两种截然不同的疾病（癌症与神经退行性疾病）进行了完整验证。
*   **充分性**：
    *   在 PDAC 中生成了 75 个候选基因和 23 个策略；在 AD 中生成了 34 个基因和 14 个策略。
    *   进行了 5000 次随机置换检验以确保显著性。
    *   **客观性**：通过双疾病模型测试了框架的可迁移性和边界条件，实验设计较为客观，涵盖了从靶点水平到多靶点策略水平的深度验证。

### 6. 主要结论与发现
*   **验证成功**：PDAC 策略在 DepMap 中表现出极强的显著性（$p < 0.0002$），AD 策略在扩展的 CRISPRbrain 筛选中也达到了显著水平。
*   **新颖靶点**：识别出如 MAX、MAZ 等在 PDAC 中具有高度拓扑中心性的新颖桥接节点。
*   **可审计性**：所有最终生成的药物策略均能追溯到具体的文献引用、组学权重和网络路径，实现了“证据闭环”。
*   **药物一致性**：通过构建药物-网络一致性图谱，成功将识别出的靶点与现有或在研药物（如 EGFR 抑制剂、STAT3 抑制剂）关联。

### 7. 优点
*   **来源透明**：解决了 LLM “黑箱”输出的问题，每一项建议都有据可查。
*   **拓扑约束**：不只是简单的列表交集，而是利用图神经网络的拓扑结构来约束 LLM 的推理，减少了生物学上的不合理性。
*   **多模型集成**：使用多种前沿 LLM 减少了单一模型的偏见和幻觉。

### 8. 不足与局限
*   **数据模态单一**：目前主要依赖转录组学，尚未充分整合蛋白质组学、代谢组学或空间组学数据。
*   **因果性限制**：转录组信号更多是关联性的，不能完全确立因果关系。
*   **文献惯性**：LLM 倾向于保留广泛认可的经典基序（如 IL6-STAT3），可能漏掉在特定治疗压力下新出现的重构路径。
*   **验证依赖**：验证效果高度依赖于现有功能筛选数据库（如 DepMap）的覆盖范围。

（完）
