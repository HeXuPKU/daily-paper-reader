---
title: "The End of Aging Clocks: Training Foundation Models to Reason in Aging and Longevity"
title_zh: 衰老时钟的终结：训练基础模型在衰老与长寿领域进行推理
authors: "Zhavoronkov, A., Aladinskyi, V., Aliper, A., Miftakhutdinov, Z., Reymond, M., Naumov, V., Zagirova, D., Pushkov, S., Sidorenko, D., Shayakhmetov, R., Galkin, F."
date: 2026-03-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.28.714980v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 通过强化学习在多模态生物数据上微调的基础模型
tldr: 针对传统衰老时钟模型在多模态和生物学解释上的局限性，研究者开发了Longevity-LLM v0.1。该模型基于Qwen3-14B，通过监督学习和强化学习在DNA甲基化、蛋白质组学、临床生物标志物和RNA表达数据上进行微调。它在Longevity Bench中表现优异，在表观遗传年龄预测上超越了Horvath时钟，并能生成蛋白质组谱，证明了单一基础模型在衰老研究中替代专用时钟的潜力。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-28-714980-v1/fig-001.webp\", \"caption\": \"Figure 1. Longevity-LLM shows competitive performance in a range of Longevity Bench tasks. The tested tasks span the domains of transcriptomics, proteomics, and clinical record. Base Qwen-3 14B failed to produce valid outputs on all tasks.\", \"page\": 6, \"index\": 1, \"width\": 976, \"height\": 471}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-28-714980-v1/fig-002.webp\", \"caption\": \"Figure 2. Longevity-LLM is a language model parsing the aging signal in DNAm profiles.\", \"page\": 7, \"index\": 2, \"width\": 976, \"height\": 306}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-28-714980-v1/fig-003.webp\", \"caption\": \"Figure 3. Longevity-LLM captures age-dependent signal in proteomic data.\", \"page\": 8, \"index\": 3, \"width\": 976, \"height\": 644}]"
motivation: 传统衰老时钟模型受限于固定模态和特征集，且缺乏深入的生物学解释能力。
method: 基于Qwen3-14B模型，利用多模态生物数据通过监督微调和强化学习构建了Longevity-LLM。
result: 模型在表观遗传年龄预测中超越了Horvath时钟，并在蛋白质组谱生成等任务中显著优于现有前沿大模型。
conclusion: 研究证明了单一基础模型能够跨模态取代专用衰老时钟，开启了衰老研究与药物发现的新范式。
---

## 摘要
衰老时钟范式已经产生了数十种专业模型，能够从几乎任何生物数据类型中估算生理年龄或死亡率。然而，每种此类模型都在固定的模态内运行，依赖于预定义的特征集，且产生的生物学解释有限。在此，我们报告了 Longevity-LLM v0.1，这是一个基于 Qwen3-14B 的模型，通过监督学习和强化学习方案在 DNA 甲基化、蛋白质组学、临床生物标志物和 RNA 表达数据上进行了微调。Longevity-LLM 在最近公布的 Longevity Bench 中获得了很高的排名，包括癌症生存率以及基于 RNA 或蛋白质组的年龄预测等任务。经过强化微调后，该模型在表观遗传年龄预测中实现了 4.34 年的平均绝对误差（MAE），超越了 Horvath 多组织时钟。除了年龄预测外，Longevity-LLM 还可以执行许多其他任务，包括蛋白质组图谱生成，在这一任务上它显著优于所有前沿大语言模型（LLMs）。这些结果表明，单个中等规模的 LLM 可以在跨数据模态的情况下匹配或取代专用衰老时钟。这项工作构成了我们科学多模态 AI 健身房（MMAI）初始冲刺阶段的中期报告，该计划致力于构建用于药物研发和衰老研究的基础模型。

## Abstract
The aging clock paradigm has yielded dozens of specialist models that can estimate chronological age or mortality from virtually any biodata type. Yet each such model operates within a fixed modality, relies on a predetermined feature set, and produces limited biological interpretation. Here, we report Longevity-LLM v0.1, a Qwen3-14B model fine-tuned through supervised and reinforcement learning regimes on DNA methylation, proteomics, clinical biomarker, and RNA expression data. Longevity-LLM achieves high ranks in the recently announced Longevity Bench, including such tasks as cancer survival and RNA- or proteome-based age prediction. After reinforcement fine-tuning, the model achieved a 4.34-year MAE in epigenetic age prediction, surpassing the Horvath multi-tissue clock. In addition to age prediction, Longevity-LLM can carry out numerous other tasks, including proteomic profile generation, for which it significantly outperforms all frontier LLMs. These results demonstrate that a single modestly sized LLM can match or replace purpose-built aging clocks across data modalities. This work constitutes an interim report from the initial sprint of our Multi-Modal AI Gym for Science (MMAI), an initiative dedicated to building foundation models for drug discovery and aging research.

---

## 论文详细总结（自动生成）

这是一份关于论文《衰老时钟的终结：训练基础模型在衰老与长寿领域进行推理》（*The End of Aging Clocks: Training Foundation Models to Reason in Aging and Longevity*）的结构化总结：

### 1. 论文的核心问题与整体含义
*   **研究动机**：传统的“衰老时钟”模型（Aging Clocks）虽然在预测生理年龄方面表现出色，但存在三大局限：1) **模态单一**，每个模型仅针对特定数据（如DNA甲基化或蛋白质组）；2) **特征固定**，无法处理缺失数据或新特征；3) **缺乏解释性**，无法解释为何某人的生物年龄高于生理年龄。
*   **核心目标**：开发一个通用的基础模型（Longevity-LLM），通过将多模态生物数据转化为文本形式进行训练，使其能够跨模态理解衰老生物学，并取代零散的专用衰老时钟。

### 2. 核心方法论
*   **基础架构**：基于 **Qwen3-14B** 开源大模型。
*   **核心思想**：采用“衰老时钟蒸馏”策略，将组学数据和已知时钟的知识转化为结构化的推理轨迹（Reasoning Traces），直接对 LLM 进行微调。
*   **关键技术流程**：
    1.  **监督微调 (SFT)**：在包含 76.6 万个样本（10.9 亿 Token）的多任务语料库上训练，涵盖 DNA 甲基化（DNAm）、蛋白质组、转录组和临床指标。数据被转化为文本格式（如 CpG 位点的 Beta 值）。
    2.  **强化微调 (RFT)**：使用 **GRPO（群组相对策略优化）** 算法。
        *   **奖励函数设计**：包含格式奖励（确保输出推理标签）、思考长度奖励（鼓励深度推理）和**回归准确性奖励**（根据预测值与真实值的绝对误差进行评分）。
    3.  **推理链**：模型在输出预测前会生成 ` <think> ` 标签内的推理内容，分析生物标志物与衰老的联系。

### 3. 实验设计
*   **数据集**：
    *   **DNAm**：来自多个公开时钟的 CpG 位点数据。
    *   **临床数据**：NHANES 数据集（包含死亡率和生存时间）。
    *   **转录组**：GTEx 门户的基因表达数据。
    *   **蛋白质组**：Olink Explore 3072 平台数据。
    *   **癌症生存**：TCGA 数据库。
*   **Benchmark（基准）**：
    *   **Longevity Bench**：包含 7 项长寿相关任务。
    *   **专用模型对比**：Horvath 多组织表观遗传时钟、PAC 和 Proteoclock 蛋白质组时钟。
    *   **LLM 对比**：与 15 个前沿商业大模型（如 Gemini 3 Pro 等）进行对比。

### 4. 资源与算力
*   **SFT 阶段**：使用 **24 台 NVIDIA B200 GPU**。训练消耗约 45 亿 Token，执行 3000 个优化步骤，全局 Batch Size 约为 157 万 Token。
*   **RFT 阶段**：使用 **16 台 NVIDIA A100 (80GB) GPU**。执行 2000 个步骤，上下文窗口为 16k。

### 5. 实验数量与充分性
*   **实验规模**：涵盖 4 大主要模态、38 个子任务。
*   **验证严谨性**：
    *   采用**受试者级（Subject-level）**的数据划分，严格防止训练集与测试集之间的数据泄露。
    *   使用了 1438 个独立样本验证 DNAm 预测，94 个样本验证蛋白质组预测。
    *   通过 Bootstrap 重采样计算置信区间和 p 值，确保统计显著性。
*   **充分性评价**：实验设计较为全面，不仅对比了通用 LLM，还直接挑战了该领域的“金标准”专用模型（如 Horvath 时钟），具有较强的说服力。

### 6. 主要结论与发现
*   **超越专用模型**：经过 RFT 后，Longevity-LLM 在表观遗传年龄预测上的 MAE（平均绝对误差）达到 **4.34 年**，显著优于经典的 Horvath 时钟（4.61 年）。
*   **多模态全能**：在 Longevity Bench 的 7 项任务中，该模型在 4 项中排名第一，包括癌症生存预测和死亡率分类。
*   **生成能力**：模型能够根据年龄和性别生成生物学上合理的蛋白质组谱，表现远超其他前沿 LLM。
*   **架构潜力**：证明了标准文本 Transformer 架构无需修改（如增加预测头），仅通过文本化生物数据即可处理复杂的组学回归任务。

### 7. 优点与亮点
*   **范式突破**：提出了“单体式（Monolithic）”模型路径，避免了多智能体系统中工具间逻辑不一致的问题。
*   **跨模态一致性**：模型内部形成了对衰老生物学的统一表征，能够利用一种模态的知识辅助另一种模态的推理。
*   **强化学习应用**：成功将 RFT 应用于科学回归任务，通过奖励机制显著提升了数值预测的精度。

### 8. 不足与局限
*   **中期报告性质**：目前为 v0.1 版本，模型在阐述底层分子特征到高层表型解释的逻辑链条上仍有提升空间。
*   **数据规模限制**：蛋白质组学等部分模态的训练数据量相对较小（仅 7807 个样本），可能限制了其在这些领域的泛化上限。
*   **生物系统复杂性**：相比化学领域，生物系统的奖励函数更难定义，模型在处理极端复杂的生物背景时可能存在偏差。

（完）
