---
title: Canonical self-supervised pretraining paradigm constrains the capacity of genomic language models on regulatory decoding
title_zh: 经典的自监督预训练范式限制了基因组语言模型在调控解码方面的能力
authors: "Liang, Y.-X., Wang, Y., Pan, W.-Y., Chen, Z.-Y., Wei, J.-C., Gao, G."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.13.715198v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 基因组语言模型在调控解码上的评估
tldr: 本研究系统评估了11个代表性基因组语言模型（gLM）在多种调控基因组学应用中的表现，发现当前基于纯序列的自监督预训练范式在解码动态基因调控方面存在局限，效果仅略优于随机基准。研究指出，预训练范式与调控代码的上下文特异性之间存在系统性失配，强调了开发结合生化和调控先验知识的功能导向型预训练策略的必要性。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-13-715198-v1/fig-001.webp\", \"caption\": \"Fig. 1: Evaluation of genomic language models on regulatory-oriented downstream applications. a. The LingoDNABench evaluation suite, comprises four regulatory categories:\", \"page\": 29, \"index\": 1, \"width\": 858, \"height\": 1207}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-13-715198-v1/fig-002.webp\", \"caption\": \"Fig. 2: Genomic language models capture intra- and inter-species mutual information via MLM pretraining objective. a. Masked-token prediction accuracy across different genomic regions (exons versus Alu elements). Statistical significance was assessed using a one-sided Mann– Whitney U test; *** denotes P < 0.001, and “ns” indicates not significant. Effect sizes are reported as rank-biserial correlation (r), with positive values indicating higher predicted probabilities in exonic regions relative to Alu elements. In each boxplot, the lower and upper boundaries of the box represent the first (Q1) and third quartiles (Q3), with the median indicated by a line inside the box.\", \"page\": 31, \"index\": 2, \"width\": 864, \"height\": 1000}]"
motivation: 旨在评估当前基因组语言模型在解码复杂且具有上下文动态特性的基因组调控代码方面的实际效能。
method: 对11个具有代表性的基因组语言模型在多个调控基因组学应用场景下进行了系统的基准测试与分析。
result: 发现现有模型相比随机基准优势有限，主要原因是纯序列预训练范式无法捕捉基因调控的动态与上下文特异性。
conclusion: 基因组模型需要从纯序列预训练转向结合生化与调控先验的功能导向型预训练策略。
---

## 摘要
最近的研究表明，基因组语言模型（gLMs）有助于解码基因组调控密码。在本研究中，我们系统地评估了 11 个具有代表性的 gLM 在多个调控基因组学应用中的表现，发现目前的 gLM 与随机基准相比优势有限。进一步的分析揭示了经典的仅基于序列的自监督预训练范式与基因调控的上下文特异性动态特征之间存在系统性的不匹配，这凸显了开发面向功能的预训练策略的必要性，此类策略应明确整合生化和调控先验知识。

## Abstract
Recent studies suggest that genomic language models (gLMs) could help decode genomic regulatory code. Here, we systematically evaluated 11 representative gLMs across multiple regulatory genomics applications and found that current gLMs offer limited advantages over the random baseline. Further analysis revealed a systematic misalignment between the canonical sequence-only self-supervised pretraining paradigm and the context-specific dynamic nature of gene regulation, highlighting the need for function-oriented pretraining strategies that explicitly incorporate biochemical and regulatory priors.

---

## 论文详细总结（自动生成）

这篇论文对当前基因组语言模型（gLM）在基因调控解码任务中的表现进行了系统性评估和理论反思。以下是详细的结构化总结：

### 1. 核心问题与整体含义
*   **研究动机**：近年来，借鉴自然语言处理（NLP）的自监督预训练范式（如掩码语言模型 MLM）在基因组学中广泛应用。然而，一个核心假设——“仅基于序列的自监督学习足以捕捉基因组序列中蕴含的复杂功能调控逻辑”——从未得到系统验证。
*   **核心问题**：当前的 gLM 是否真的理解了基因调控的“语法”，还是仅仅捕捉了进化保守性或简单的统计规律？

### 2. 方法论
*   **LingoDNABench 评测基准**：构建了一个涵盖全调控层级的基准套件，包括：
    *   **染色质图谱**（DNA 可及性、组蛋白修饰、甲基化）。
    *   **转录调节**（TF 结合位点、启动子/增强子/沉默子识别、CRE 活性、长程相互作用）。
    *   **转录后调节**（剪接位点、外显子跳跃、内含子保留、多聚腺苷酸信号等）。
    *   **基因表达预测**（Bulk RNA-seq）。
*   **轻量化适配器微调（Adapter Fine-tuning）**：为了公平评估预训练模型提取的特征表示，研究者冻结了模型骨干，仅使用轻量级适配器进行微调，确保性能差异源于预训练捕获的信息而非下游架构。
*   **信息论框架**：从信息论角度提出，MLM 预训练本质上是在最大化掩码 token 与上下文之间的互信息（包含种内统计相关性和种间进化约束），这解释了模型为何偏向于捕捉重复序列和保守区域。

### 3. 实验设计
*   **评估对象**：11 个代表性 gLM（包括 Caduceus, HyenaDNA, DNABERT-2, Nucleotide Transformer, Evo2 等），涵盖了不同的架构（Transformer, Mamba, Hyena）、参数规模（1.9M 到 7B）和预训练数据。
*   **基准对比（Baselines）**：
    *   **Non-gLM 基准**：针对特定任务训练的传统 CNN 模型（如 Basset）。
    *   **RandomWeight 基准**：参数完全随机初始化、未经任何训练的 BERT 模型，用于衡量预训练带来的真实增益。
*   **变异效应预测（VEP）**：对比了受进化保守性驱动的 ClinVar 数据集和受生化机制驱动的 eQTL/MPRA 数据集。

### 4. 资源与算力
*   **算力设备**：使用了 **NVIDIA Tesla A100 GPU** 集群。
*   **训练细节**：研究者自行预训练了两个模型作为对照：人类基因组模型（Model H）和多物种模型（Model M）。Model M 使用了 7 个物种的基因组，训练步数达 2,000,000 步，Model M 的 batch size 为 64。

### 5. 实验数量与充分性
*   **实验规模**：在 23 个下游任务上对 11 个模型进行了全面测试。
*   **纵向分析**：通过跟踪预训练过程中的中间检查点（Checkpoints），分析了预训练损失（Loss）与下游任务性能之间的相关性。
*   **客观性**：引入随机权重模型作为基准，揭示了许多 gLM 的所谓“高性能”实际上很大程度上归功于下游微调架构，而非预训练学到的生物学知识。实验设计严谨，对比维度全面。

### 6. 主要结论与发现
*   **性能平庸**：在大多数调控任务中，gLM 相比随机基准（RandomWeight）仅有微弱提升，且往往不如针对特定任务设计的传统 CNN 模型。
*   **目标失配**：预训练损失的降低并不总能转化为下游调控预测性能的提升，表明 MLM 目标与动态调控解码之间存在系统性失配。
*   **保守性偏见**：gLM 的优势主要集中在受进化保守性约束的任务（如疾病相关变异预测），而在捕捉生化驱动的动态调控效应（如 eQTL）方面表现极差。
*   **上下文缺失**：基因调控是高度动态且具有细胞特异性的，而当前的纯序列预训练范式无法捕捉这种超越序列本身的上下文信息。

### 7. 优点与亮点
*   **基准全面性**：LingoDNABench 是目前最完整的基因组调控解码评测集之一。
*   **深刻的理论剖析**：不仅指出了模型“不行”，还通过信息论和纵向实验解释了“为什么不行”。
*   **揭示行业幻觉**：通过 RandomWeight 基准，有力地挑战了当前基因组大模型领域盲目追求“规模定律（Scaling Law）”的倾向。

### 8. 不足与局限
*   **数据瓶颈**：虽然提出了“功能导向型预训练”的建议，但高质量、跨细胞类型的生化实验数据（如大规模 MPRA 或表观基因组数据）仍然稀缺且分布不均。
*   **模型覆盖**：虽然评估了 11 个模型，但随着领域快速发展，新的架构（如更长上下文的模型）可能需要持续更新评估。
*   **应用限制**：研究主要集中在人类基因组调控，对于非模式生物或其他复杂基因组结构的适用性讨论较少。

（完）
