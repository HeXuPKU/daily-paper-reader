---
title: "The End of Aging Clocks: Training Foundation Models to Reason in Aging and Longevity"
title_zh: 衰老时钟的终结：训练基础模型在衰老与长寿领域进行推理
authors: "Zhavoronkov, A., Aladinskyi, V., Aliper, A., Miftakhutdinov, Z., Reymond, M., Naumov, V., Zagirova, D., Pushkov, S., Sidorenko, D., Shayakhmetov, R., Galkin, F."
date: 2026-03-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.28.714980v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 通过强化学习在基因组和临床数据上微调的基础模型
tldr: 本研究推出了Longevity-LLM v0.1，这是一个基于Qwen3-14B的大语言模型，通过对DNA甲基化、蛋白质组学、临床生物标志物和RNA表达数据进行微调，打破了传统衰老时钟单一模态的局限。该模型在Longevity Bench中表现优异，在表观遗传年龄预测上超越了Horvath时钟，并能执行蛋白质组分析等多种任务，展示了基础模型在长寿研究中的巨大潜力。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-28-714980-v1/fig-001.webp\", \"caption\": \"Figure 1. Longevity-LLM shows competitive performance in a range of Longevity Bench tasks. The tested tasks span the domains of transcriptomics, proteomics, and clinical record. Base Qwen-3 14B failed to produce valid outputs on all tasks.\", \"page\": 6, \"index\": 1, \"width\": 976, \"height\": 471}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-28-714980-v1/fig-002.webp\", \"caption\": \"Figure 2. Longevity-LLM is a language model parsing the aging signal in DNAm profiles.\", \"page\": 7, \"index\": 2, \"width\": 976, \"height\": 306}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-28-714980-v1/fig-003.webp\", \"caption\": \"Figure 3. Longevity-LLM captures age-dependent signal in proteomic data.\", \"page\": 8, \"index\": 3, \"width\": 976, \"height\": 644}]"
motivation: 传统的衰老时钟模型通常局限于单一数据模态且缺乏生物学解释力，需要一种能够整合多模态数据并具备推理能力的基础模型。
method: 基于Qwen3-14B模型，利用监督微调和强化学习技术，在DNA甲基化、蛋白质组、临床指标及RNA表达等多维生物数据上进行训练。
result: 模型在表观遗传年龄预测中达到了4.34年的平均绝对误差，优于Horvath多组织时钟，并在蛋白质组谱生成等任务上显著超过现有前沿大模型。
conclusion: 研究证明了中等规模的LLM可以跨模态匹配甚至取代专门设计的衰老时钟，为药物研发和衰老研究提供了新的多模态AI范式。
---

## 摘要
衰老时钟范式已经产生了数十种专业模型，能够从几乎任何生物数据类型中估算生理年龄或死亡率。然而，每种此类模型都在固定的模态内运行，依赖于预定义的特征集，且产生的生物学解释有限。在此，我们报告了 Longevity-LLM v0.1，这是一个基于 Qwen3-14B 的模型，通过监督学习和强化学习方案在 DNA 甲基化、蛋白质组学、临床生物标志物和 RNA 表达数据上进行了微调。Longevity-LLM 在最近公布的 Longevity Bench 中获得了很高的排名，包括癌症生存率以及基于 RNA 或蛋白质组的年龄预测等任务。经过强化微调后，该模型在表观遗传年龄预测中实现了 4.34 年的平均绝对误差（MAE），超越了 Horvath 多组织时钟。除了年龄预测外，Longevity-LLM 还可以执行许多其他任务，包括蛋白质组图谱生成，在这一任务上它显著优于所有前沿大语言模型（LLMs）。这些结果表明，单个中等规模的 LLM 可以在跨数据模态的情况下匹配或取代专用衰老时钟。这项工作构成了我们科学多模态 AI 健身房（MMAI）初始冲刺阶段的中期报告，该计划致力于构建用于药物研发和衰老研究的基础模型。

## Abstract
The aging clock paradigm has yielded dozens of specialist models that can estimate chronological age or mortality from virtually any biodata type. Yet each such model operates within a fixed modality, relies on a predetermined feature set, and produces limited biological interpretation. Here, we report Longevity-LLM v0.1, a Qwen3-14B model fine-tuned through supervised and reinforcement learning regimes on DNA methylation, proteomics, clinical biomarker, and RNA expression data. Longevity-LLM achieves high ranks in the recently announced Longevity Bench, including such tasks as cancer survival and RNA- or proteome-based age prediction. After reinforcement fine-tuning, the model achieved a 4.34-year MAE in epigenetic age prediction, surpassing the Horvath multi-tissue clock. In addition to age prediction, Longevity-LLM can carry out numerous other tasks, including proteomic profile generation, for which it significantly outperforms all frontier LLMs. These results demonstrate that a single modestly sized LLM can match or replace purpose-built aging clocks across data modalities. This work constitutes an interim report from the initial sprint of our Multi-Modal AI Gym for Science (MMAI), an initiative dedicated to building foundation models for drug discovery and aging research.

---

## 论文详细总结（自动生成）

以下是对论文《The End of Aging Clocks: Training Foundation Models to Reason in Aging and Longevity》的结构化深度总结：

### 1. 论文的核心问题与整体含义
*   **研究动机**：传统的“衰老时钟”（Aging Clocks）虽然在预测生理年龄方面表现出色，但存在三大局限：
    1.  **模态单一**：每个模型仅限于特定的生物数据（如仅DNA甲基化或仅蛋白质组），无法处理缺失数据或跨模态整合。
    2.  **解释性差**：模型通常是“黑盒”，无法解释为何某人的生物年龄高于实际年龄。
    3.  **工具碎片化**：研究者需要维护多个专用模型，导致药物研发流程割裂。
*   **核心目标**：通过将衰老生物学知识和多种衰老时钟的预测能力“蒸馏”到一个大语言模型（LLM）中，构建一个能够跨模态推理、预测并具备生物学理解力的通用基础模型 **Longevity-LLM v0.1**。

### 2. 论文提出的方法论
*   **核心思想**：放弃为每种数据建立专用架构，而是将组学数据（Omics）转化为结构化的文本追踪（Traces），利用 LLM 的上下文学习和推理能力处理生物信号。
*   **关键技术流程**：
    1.  **监督微调 (SFT)**：在包含 76.6 万个样本（10.9 亿 token）的语料库上训练。任务涵盖 DNA 甲基化（DNAm）、临床指标、转录组和蛋白质组。引入了自动生成的推理链（Reasoning Traces）来增强模型的逻辑性。
    2.  **强化微调 (RFT)**：基于 SFT 后的模型，使用 **GRPO（群组相对策略优化）** 算法。
        *   **奖励函数设计**：包含**格式奖励**（确保输出符合 `<think>` 标签）、**思考长度奖励**（鼓励深入推理）和**回归准确性奖励**（基于预测值与真实值的绝对误差）。
        *   **KL 散度约束**：防止模型在强化学习过程中发生策略坍塌。

### 3. 实验设计
*   **数据集**：
    *   **DNAm**：来自多个公开时钟的 CpG 位点数据。
    *   **临床数据**：NHANES 数据库（包含年龄、死亡率、生存时间）。
    *   **转录组**：GTEx Portal 的基因表达数据。
    *   **蛋白质组**：Olink Explore 3072 平台数据。
    *   **癌症数据**：TCGA 的癌症生存对比数据。
*   **Benchmark**：主要使用 **Longevity Bench**（包含 7 项长寿相关任务）。
*   **对比方法**：
    *   **LLM 对比**：与 GPT-4o、Gemini 1.5 Pro、Claude 3.5 Sonnet 等 15 个前沿商用模型对比。
    *   **专用模型对比**：在 DNAm 预测上对比 **Horvath 多组织时钟**；在蛋白质组预测上对比 **PAC** 和 **Proteoclock**。

### 4. 资源与算力
*   **SFT 阶段**：使用 **24 张 NVIDIA B200 GPU**，训练约 3000 个优化步，消耗约 45 亿 token。
*   **RFT 阶段**：使用 **16 张 NVIDIA A100 80GB GPU**，训练 2000 步。
*   **开发周期**：该模型是在一个为期 **10 天** 的快速开发冲刺（Sprint）中完成的。

### 5. 实验数量与充分性
*   **实验规模**：涵盖了 4 大主要生物模态，共 38 个子任务。
*   **客观性与公平性**：
    *   采用了**受试者级别（Subject-level）**的数据划分，确保训练集和测试集没有重叠，防止数据泄露。
    *   在对比 Horvath 时钟时，使用了 1436 个双方均未见过的独立样本进行测试。
    *   使用了自助法（Bootstrap）计算置信区间和 p 值，确保统计学意义。
*   **充分性**：虽然蛋白质组样本量较小（约 7800 个），但 DNAm 和临床数据的规模较大，整体实验设计较为严谨。

### 6. 主要结论与发现
*   **超越专用模型**：Longevity-LLM 在 RFT 后，表观遗传年龄预测的 MAE 达到 **4.34 年**，显著优于经典的 Horvath 时钟（4.61 年）。
*   **Longevity Bench 领先**：在 7 项任务中的 4 项排名第一，尤其在 RNA 癌症预后和 NHANES 死亡率预测上表现突出。
*   **生成能力**：在根据年龄和性别生成蛋白质组图谱的任务中，Longevity-LLM 显著超过了所有前沿商用 LLM，证明其内部化了蛋白质组的动态变化规律。
*   **架构通用性**：证明了标准的文本 Transformer 架构无需修改即可处理复杂的数值型组学数据。

### 7. 优点
*   **多模态统一**：打破了“一个模态一个模型”的僵局，实现了单一模型处理多种生物数据。
*   **高性能与轻量化**：仅用 14B 参数的模型，通过针对性微调，在特定领域击败了参数量大得多的通用模型（如 GPT-4）。
*   **推理潜力**：通过 RFT 引入思考过程，为未来实现“可解释的衰老生物学”奠定了基础。

### 8. 不足与局限
*   **数据稀缺性**：蛋白质组等某些模态的数据量相对较小，可能限制了模型在这些领域的泛化上限。
*   **推理深度**：目前版本（v0.1）虽然引入了思考标签，但其生成的生物学逻辑是否完全符合真实生化机制仍需进一步验证。
*   **应用限制**：目前主要处于预测和关联阶段，尚未完全展示其在干预措施发现（如药物筛选）中的直接因果推理能力。
*   **中期报告性质**：作为初步冲刺成果，更广泛的跨模态泛化假设（如用 DNAm 知识辅助蛋白质组预测）尚未进行深入的消融实验。

（完）
