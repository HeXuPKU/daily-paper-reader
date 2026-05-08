---
title: Interpreting Omics Data Analysis with Large Language Models for Disease Target and Drug Discovery
title_zh: 利用大语言模型解释组学数据分析，助力疾病靶点与药物发现
authors: "XU, Z., Chen, W., Ren, W., Xu, T., Amaechin, S., Khan, R., Chen, Y., Province, M., Payne, P., Li, F."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721768v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 利用大语言模型解释组学数据以进行疾病靶点发现
tldr: 本研究提出Text-to-Target框架，旨在解决生物医学发现中组学数据分析与文献知识整合的难题。该框架将大语言模型（LLM）的检索能力与数值组学分析相结合，通过模态感知融合技术，将候选靶点划分为锚点、隐藏枢纽和新兴节点，并生成受拓扑约束的假设。在阿尔茨海默症和胰腺癌的实验中，该方法显著提升了靶点识别的准确性与可解释性，为药物研发提供了具备端到端审计能力的发现架构。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在克服单纯依靠LLM检索缺乏定量证据以及单纯组学分析缺乏生物学机制解释的局限性。
method: 采用模式约束的多模型LLM检索与组学数据耦合，通过模态感知融合和网络拓扑约束生成候选靶点及治疗策略。
result: 在胰腺癌和阿尔茨海默症中成功识别出具有显著生物学支持的靶点宇宙和策略组合，并获得DepMap等数据库的验证。
conclusion: 该框架证明了组学证据与LLM检索融合在提高疾病靶点优先排序的可解释性和可重复性方面的巨大潜力。
---

## 摘要
在生物医学科学发现中，综合文献中的先验知识是解释数值组学数据分析以进行疾病靶点识别和药物发现的关键组成部分。仅靠大语言模型（LLMs）可以快速从生物医学文本中检索疾病机制，但如果没有特定队列的定量证据，纯文本输出对于靶点和药物优先级排序来说往往过于笼统且不可靠。在此，我们提出了一种具有溯源意识的“文本到靶点”（Text-to-Target）框架，该框架将模式约束的多模型 LLM 检索与数值组学数据分析相结合。关键设计是一个模态感知的融合步骤：候选基因被划分为重叠支持的锚点（anchors）、仅检索到的隐藏枢纽（hidden hubs）以及网络涌现的新颖节点（novelty nodes），然后在拓扑约束下传播到分阶段的假设和策略生成中。我们在阿尔茨海默病（AD）和胰腺导管腺癌（PDAC）中评估了该模型。在 PDAC 中，该工作流产生了一个包含 75 个基因的平衡候选空间和 23 个策略组合，在靶点水平和策略水平上均获得了显著的 DepMap 支持。在 AD 中，更严格的候选控制产生了一个紧凑的 34 基因空间和 14 个策略；在扩展的 CRISPRbrain 注册库下，两个靶点水平轴均具有显著性，且具有较强的策略水平富集。在这两种疾病中，最终策略都保持了对候选池的完整溯源闭环，实现了从检索产物到验证输出的端到端可审计性。这些结果支持了一种可迁移的发现架构，其中组学证据约束生物活性，LLM 检索扩展机制搜索空间，而网络感知融合保留了可解释性。该框架为双疾病靶点优先级排序提供了可重复的基础，并激发了通过智能体证据刷新循环实现文献与机制持续一致性的动力。

## Abstract
In biomedical scientific discovery, synthesizing prior knowledge from the literature is an essential component of interpreting numerical omics data analyses for disease target identification and drug discovery. Large language models (LLMs) alone can rapidly retrieve disease mechanisms from biomedical text, but text-only outputs are general and unreliable for target and drug prioritization without cohort-specific quantitative evidence. Herein, we propose a provenance-aware Text-to-Target framework that couples schema-constrained multi-model LLM retrieval with numeric omics data analysis. The key design is a modality-aware fusion step: candidates are partitioned into overlap-supported anchors, retrieval-only hidden hubs, and network-emergent novelty nodes, then propagated into staged hypothesis and strategy generation under topology constraints. We evaluate the model in Alzheimer's disease (AD) and pancreatic ductal adenocarcinoma (PDAC). In PDAC, the workflow produced a balanced 75-gene candidate universe and a 23-strategy portfolio, with significant DepMap support at both target level and strategy level. In AD, stricter candidate controls yielded a compact 34-gene universe and 14 strategies; under an expanded CRISPRbrain registry, both target-level axes were significant , with strong strategy-level enrichment. Across both diseases, final strategies preserved full provenance closure to the candidate pool, enabling end-to-end auditability from retrieval artifacts to validation outputs. These results support a transferable discovery architecture in which omics evidence constrains biological activity, LLM retrieval expands mechanistic search space, and network-aware fusion preserves interpretability. The framework provides a reproducible basis for dual-disease target prioritization and motivates continuous literature-mechanism concordance with agentic evidence-refresh loops.

---

## 论文详细总结（自动生成）

### 论文总结：利用大语言模型解释组学数据分析，助力疾病靶点与药物发现

#### 1. 核心问题与整体含义（研究动机和背景）
论文针对生物医学发现中的一个关键瓶颈：**如何将海量的数值组学数据（如单细胞测序）转化为具有生物学机制解释的治疗靶点和药物策略**。
*   **研究动机**：目前的精准医学工作流在“定量分析（组学）”与“定性解释（文献综述）”之间存在断层。专家手动查阅文献速度慢且易遗漏，而单纯使用大语言模型（LLM）检索知识虽然快，但容易产生“幻觉”，且缺乏特定患者队列的定量证据支持。
*   **核心目标**：开发一个名为 **Text-to-Target** 的框架，将 LLM 的语义先验知识与组学数据的定量约束相结合，构建一个可审计、可解释且具有溯源能力的自动化发现流程。

#### 2. 方法论：核心思想与技术细节
该框架采用分阶段的集成策略，核心流程如下：
*   **双分支提取**：
    *   **语言分支（LLM Engine）**：使用 GPT-5、Gemini 2.5-pro 和 DeepSeek-r1 等模型，通过模式约束（Schema-constrained）的提示词，检索特定细胞类型的靶点、通路和机制，生成结构化表格。
    *   **组学分支（Omics Engine）**：利用 **PathFinder**（一种图变换器模型）将单细胞差异表达信号转化为加权的生物信号网络，识别关键的信号路径。
*   **象限融合（Quadrant Fusion）**：将候选基因分为四类：
    *   **Q1 (Anchors)**：LLM 检索与网络分析共同支持的锚点。
    *   **Q2 (Hidden Hubs)**：仅由 LLM 检索到但在当前网络中未显现的隐藏枢纽。
    *   **Q3 (Novelty)**：仅由网络发现的新颖节点，作为连接锚点的“桥梁”。
*   **假设升级与策略生成**：LLM 首先基于 Q1 和 Q2 构建基础机制，随后在网络拓扑约束下引入 Q3 节点进行“机制升级”，最后生成包含 2-4 个靶点的联合治疗策略。
*   **溯源闭环**：所有输出均带有溯源标签（Provenance tags），确保从最终药物策略可以追溯到具体的文献引用和组学证据。

#### 3. 实验设计
研究在两种极具挑战性的疾病模型上进行了验证：
*   **胰腺导管腺癌 (PDAC)**：代表高对比度的恶性肿瘤模型。
    *   **数据集**：整合了 HCA、GEO 等单细胞/单细胞核资源，对比恶性上皮细胞与正常腺泡细胞。
    *   **Benchmark**：使用 **DepMap** 数据库进行靶点选择性脆弱性和依赖性验证。
*   **阿尔茨海默病 (AD)**：代表低对比度、高度异质性的神经退行性疾病模型。
    *   **数据集**：涵盖星形胶质细胞、小胶质细胞和神经元的疾病 vs 正常状态对比。
    *   **Benchmark**：使用 **CRISPRbrain** 注册库进行功能性筛选验证。
*   **对比逻辑**：通过置换检验（Permutation Testing，5000次抽样）评估生成的靶点集和策略集是否显著优于随机组合。

#### 4. 资源与算力
*   **模型参数**：PathFinder 模型配置为 6 层 Transformer、8 个注意力头、隐藏层维度 16。
*   **训练细节**：学习率 $1 \times 10^{-5}$，Batch Size 为 4，训练 25 个 Epoch。
*   **算力说明**：文中**未明确说明**具体的 GPU 型号和数量，但提到了使用了多种前沿商用及开源 LLM API（如 GPT-5 等）。

#### 5. 实验数量与充分性
*   **实验规模**：针对两种疾病分别构建了候选靶点宇宙（PDAC 75个基因，AD 34个基因），并生成了数十种治疗策略（PDAC 23条，AD 14条）。
*   **充分性**：实验涵盖了从单靶点到多靶点组合的验证，并进行了跨疾病的鲁棒性测试。
*   **客观性**：通过与独立第三方实验数据库（DepMap, CRISPRbrain）对比，并使用严格的统计学显著性检验（p值和z-score），证明了结果的非随机性。

#### 6. 主要结论与发现
*   **PDAC 发现**：识别出 EGFR-STAT3 等关键轴，56.5% 的生成策略在 DepMap 中具有显著的统计学支持。
*   **AD 发现**：在复杂的神经炎症背景下，识别出以 STAT3 为核心的胶质细胞状态转换机制，策略集在 CRISPRbrain 验证中表现出极强的富集信号。
*   **框架有效性**：证明了“组学约束生物活性、LLM 扩展搜索空间”的协同模式优于单一模态。

#### 7. 优点
*   **端到端可审计性**：解决了 LLM 在科学发现中“黑箱”输出的问题，每一步都有据可查。
*   **拓扑感知**：LLM 的推理受到生物网络拓扑的物理约束，减少了虚假关联。
*   **跨领域迁移**：同一套框架能同时适用于肿瘤和神经退行性疾病，展示了极强的通用性。
*   **药物关联**：直接生成带有证据极性（支持/矛盾）的靶点-药物网络，具有临床转化潜力。

#### 8. 不足与局限
*   **数据模态局限**：目前主要依赖转录组数据，尚未充分整合蛋白质组学、代谢组学或空间组学信息。
*   **因果性缺失**：虽然识别了关联，但尚未能完全建立靶点间的因果充分性。
*   **LLM 偏见**：存在“共识惯性”，即 LLM 倾向于保留文献中广泛讨论的基序，可能忽略某些极具前沿性但讨论较少的机制。
*   **动态更新需求**：生物医学文献更新极快，框架需要更高效的实时智能体（Agentic）循环来保持证据的时效性。

（完）
