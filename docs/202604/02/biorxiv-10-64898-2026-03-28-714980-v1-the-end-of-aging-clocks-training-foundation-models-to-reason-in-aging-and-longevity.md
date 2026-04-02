---
title: "The End of Aging Clocks: Training Foundation Models to Reason in Aging and Longevity"
title_zh: 衰老时钟的终结：训练基础模型在衰老与长寿领域进行推理
authors: "Zhavoronkov, A., Aladinskyi, V., Aliper, A., Miftakhutdinov, Z., Reymond, M., Naumov, V., Zagirova, D., Pushkov, S., Sidorenko, D., Shayakhmetov, R., Galkin, F."
date: 2026-03-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.28.714980v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 通过强化学习对多模态生物数据进行微调的基础模型
tldr: 本研究针对传统衰老时钟模型模态单一、解释性差的局限，开发了Longevity-LLM v0.1。该模型基于Qwen3-14B，通过监督微调和强化学习整合了DNA甲基化、蛋白质组学、临床指标及RNA表达等多模态数据。实验表明，Longevity-LLM在年龄预测和癌症生存分析等任务中表现卓越，其表观遗传年龄预测精度超越了经典的Horvath时钟。这证明了通用大模型在跨模态衰老研究和长寿干预领域具有取代专用模型的巨大潜力。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-28-714980-v1/fig-001.webp\", \"caption\": \"Figure 1. Longevity-LLM shows competitive performance in a range of Longevity Bench tasks. The tested tasks span the domains of transcriptomics, proteomics, and clinical record. Base Qwen-3 14B failed to produce valid outputs on all tasks.\", \"page\": 6, \"index\": 1, \"width\": 976, \"height\": 471}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-28-714980-v1/fig-002.webp\", \"caption\": \"Figure 2. Longevity-LLM is a language model parsing the aging signal in DNAm profiles.\", \"page\": 7, \"index\": 2, \"width\": 976, \"height\": 306}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-28-714980-v1/fig-003.webp\", \"caption\": \"Figure 3. Longevity-LLM captures age-dependent signal in proteomic data.\", \"page\": 8, \"index\": 3, \"width\": 976, \"height\": 644}]"
motivation: 传统衰老时钟模型受限于单一模态且缺乏生物学解释力，需要一种通用的基础模型来整合多维生物数据并提升推理能力。
method: 基于Qwen3-14B模型，利用DNA甲基化、蛋白质组、临床标志物和RNA表达数据，通过监督微调和强化学习进行多模态训练。
result: 模型在Longevity Bench多项任务中名列前茅，表观遗传年龄预测误差仅4.34年，优于Horvath时钟，且在蛋白质组谱生成方面显著超越现有大模型。
conclusion: 研究证明了单个中等规模的语言模型能够跨模态匹配甚至取代专门的衰老时钟，开启了利用基础模型进行长寿研究的新范式。
---

## 摘要
衰老时钟范式已产生了数十种专门模型，能够从几乎任何类型的生物数据中估算实足年龄或死亡率。然而，此类模型均在固定模态内运行，依赖预定义的特征集，且产生的生物学解释有限。在此，我们报告了 Longevity-LLM v0.1，这是一个基于 Qwen3-14B 的模型，通过监督学习和强化学习方案，在 DNA 甲基化、蛋白质组学、临床生物标志物和 RNA 表达数据上进行了微调。Longevity-LLM 在最近发布的 Longevity Bench 中名列前茅，涵盖了癌症生存率以及基于 RNA 或蛋白质组的年龄预测等任务。经过强化微调后，该模型在表观遗传年龄预测中实现了 4.34 年的平均绝对误差（MAE），超越了 Horvath 多组织时钟。除了年龄预测，Longevity-LLM 还能执行多项其他任务，包括蛋白质组图谱生成，其表现显著优于所有前沿大语言模型（LLMs）。这些结果表明，单个规模适中的大语言模型即可在跨数据模态的任务中媲美或取代专门构建的衰老时钟。本项工作是我们的“科学多模态 AI 健身房”（MMAI）初始阶段的中期报告，该计划致力于为药物研发和衰老研究构建基础模型。

## Abstract
The aging clock paradigm has yielded dozens of specialist models that can estimate chronological age or mortality from virtually any biodata type. Yet each such model operates within a fixed modality, relies on a predetermined feature set, and produces limited biological interpretation. Here, we report Longevity-LLM v0.1, a Qwen3-14B model fine-tuned through supervised and reinforcement learning regimes on DNA methylation, proteomics, clinical biomarker, and RNA expression data. Longevity-LLM achieves high ranks in the recently announced Longevity Bench, including such tasks as cancer survival and RNA- or proteome-based age prediction. After reinforcement fine-tuning, the model achieved a 4.34-year MAE in epigenetic age prediction, surpassing the Horvath multi-tissue clock. In addition to age prediction, Longevity-LLM can carry out numerous other tasks, including proteomic profile generation, for which it significantly outperforms all frontier LLMs. These results demonstrate that a single modestly sized LLM can match or replace purpose-built aging clocks across data modalities.

This work constitutes an interim report from the initial sprint of our Multi-Modal AI Gym for Science (MMAI), an initiative dedicated to building foundation models for drug discovery and aging research.

---

## 论文详细总结（自动生成）

以下是对论文《The End of Aging Clocks: Training Foundation Models to Reason in Aging and Longevity》的结构化深度总结：

### 1. 核心问题与整体含义
*   **研究背景**：自2010年代中期以来，衰老时钟（Aging Clocks）已成为长寿研究的支柱，涵盖DNA甲基化、蛋白质组、临床指标等多种模态。
*   **核心问题**：传统衰老时钟存在三大局限：
    1.  **模态孤立**：每个模型仅限于单一数据类型，无法处理缺失值或跨模态整合。
    2.  **解释性缺失**：模型仅给出数值，无法解释生物学原因。
    3.  **工具碎片化**：现有的AI代理系统仅将LLM作为调度器，而非真正理解生物学的基础模型。
*   **研究意义**：本研究旨在通过“衰老时钟蒸馏”技术，将多种专用时钟的知识内化到一个单一的、具备推理能力的大语言模型（Longevity-LLM v0.1）中，试图终结专用衰老时钟的时代。

### 2. 方法论
*   **核心思想**：将组学数据和衰老知识转化为结构化的文本“痕迹”（Traces），通过监督微调（SFT）和强化微调（RFT）使通用LLM具备处理生物数据的能力。
*   **关键技术流程**：
    *   **基础模型**：选用 Qwen3-14B。
    *   **监督微调 (SFT)**：在包含 38 个任务、10.9 亿 token 的多模态语料库上进行全参数微调。将 DNA 甲基化（CpG 位点 beta 值）、蛋白质浓度等数值转化为文本格式。
    *   **强化微调 (RFT)**：采用 **GRPO (Group Relative Policy Optimization)** 算法。
    *   **奖励函数 (Reward Function)**：
        1.  **格式奖励**：强制模型使用 `<think>` 标签进行链式思考。
        2.  **思考长度奖励**：鼓励模型进行深入推理（最高 5000 字符）。
        3.  **回归准确性奖励**：根据预测值与真实值的平均绝对误差（MAE）计算得分，并进行归一化处理。

### 3. 实验设计
*   **数据集**：
    *   **DNAm**：41.6 万个训练提示词，包含 CpG 位点信息。
    *   **临床数据**：来自 NHANES，包含 22.8 万个样本，涉及死亡率和年龄预测。
    *   **转录组 (RNA)**：来自 GTEx，包含 9.8 万个样本。
    *   **蛋白质组**：来自 Olink 平台，包含 7807 个训练样本。
*   **Benchmark**：使用 **Longevity Bench**（包含癌症生存分析、年龄预测等 7 项任务）。
*   **对比方法**：
    *   **通用模型**：对比了 15 个前沿商用 LLM（如 Gemini 3 Pro 等）。
    *   **专用时钟**：对比了 Horvath 多组织甲基化时钟、PAC 蛋白质组时钟、Proteoclock 等。

### 4. 资源与算力
*   **SFT 阶段**：使用 **24 台 NVIDIA B200 GPU**，训练约 3000 步，全局 Batch Size 约为 157 万 token。
*   **RFT 阶段**：使用 **16 台 NVIDIA A100 80GB GPU**，训练 2000 步。
*   **开发周期**：该模型是“10 天开发冲刺”的产物。

### 5. 实验数量与充分性
*   **实验规模**：涵盖了 4 大生物模态，使用了超过 76 万个训练样本。
*   **验证方法**：采用受试者级别的留出集（Holdout set）防止数据泄露，并使用 Bootstrap 重采样计算置信区间和 p 值。
*   **充分性评价**：实验设计较为客观，不仅对比了通用 LLM，还直接挑战了该领域的“金标准”（Horvath 时钟）。但在蛋白质组学方面，由于样本量相对较小（172 人），其泛化性仍需更大规模数据验证。

### 6. 主要结论与发现
*   **性能卓越**：14B 规模的 Longevity-LLM 在 Longevity Bench 的多项任务中排名第一，超越了参数量大得多的商用模型。
*   **超越专用工具**：在表观遗传年龄预测中，RFT 后的模型 MAE 达到 **4.34 年**，显著优于经典的 Horvath 时钟（4.61 年）。
*   **跨模态生成**：模型能够根据年龄和性别生成生物学上合理的蛋白质组图谱，Jaccard 指数显著高于其他 LLM。
*   **架构潜力**：证明了标准文本 Transformer 架构无需修改（如无需专用 Tokenizer），即可通过微调内化复杂的组学信号。

### 7. 优点
*   **单模型多任务**：一个模型替代了数十个专用时钟，降低了科研成本和部署难度。
*   **推理能力**：通过 RFT 引导模型进行“思考”，使其不仅能给出预测，还具备解释生物学逻辑的潜力。
*   **数据灵活性**：能够处理不完整的观测值和非标准化的提示词格式，比固定特征集的传统模型更鲁棒。

### 8. 不足与局限
*   **数据不平衡**：蛋白质组学数据量远少于甲基化数据，可能导致模型在不同模态间的知识深度不均。
*   **解释性验证不足**：虽然模型被鼓励进行推理，但论文未提供定量的评估来证明其推理过程的生物学准确性（即是否存在“幻觉”）。
*   **应用限制**：目前仍处于 v0.1 阶段，主要在公开数据集上验证，需在临床实际样本和更多样化的种群数据中进一步测试。

（完）
