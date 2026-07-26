---
title: "Representative vs. Load-bearing Layers: A Dissociation in Genomic Foundation Models"
title_zh: 代表层与承重层：基因组基础模型中的分离现象
authors: "Cho, Y., Kim, M. S., Kim, S."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.16.739040v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 基因组基础模型层分析
tldr: "基因组基础模型的下游使用通常选择特定层或聚合所有层，但未明确分类器实际依赖的层。本文提出无训练标量||Δh_l||2衡量层重要性，发现代表层（单特征性能最佳）与承重层（多特征分类器依赖）存在分离：MLM中承重层浅，CLM中承重层深。这种分离导致MLM中简单中层特征超越全连接最后一层基线，揭示现行层选择策略的缺陷。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1661, \"height\": 658}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 326}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 865, \"height\": 337}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1661, \"height\": 580}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1597, \"height\": 1067}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 168}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 173}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1191, \"height\": 170}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 666, \"height\": 600}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 353}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 821, \"height\": 478}]"
motivation: 基因组基础模型下游应用中层选择缺乏依据，需探明分类器实际依赖的层是否与常用代表层一致。
method: 定义变异token处每层隐藏状态偏移的L2范数作为标量特征，通过单特征AUROC和留一层消融及SHAP值识别代表层与承重层。
result: 在NT-v2（MLM）和Evo 2（CLM混合）上，代表层居中，承重层分别在浅层和深层；MLM中一维中层特征比最后一层均值池化高+0.049 AUROC。
conclusion: 代表层与承重层分离，标准最后一层池化在MLM中浪费信息，需根据模型类型调整层选择策略。
---

## 摘要
基因组基础模型的下游使用遵循三种惯例之一：聚合所有层的表示（Pearce 等，2026）、将最后隐藏状态作为固定特征提取器（Dalla-Torre 等，2024），或通过可解释性机制工具选择单个中间层（Brixi 等，2026）。但这些方法均未考察联合分类器实际依赖的是哪一层。我们通过一个无需训练的最小标量 ||Δh_ℓ||₂（定义为变体位点逐层隐藏状态变化的L2范数）来探究这一问题。我们在NT-v2 500M（Dalla-Torre 等，2024，掩码语言模型MLM）和Evo 2 7B（Brixi 等，2026，有鬣狗/注意力混合的因果语言模型CLM）上对8,008个ClinVar（Landrum 等，2018）单核苷酸变体进行了评估。在两个模型中，具有峰值单特征AUROC的层（代表层）并非联合多层分类器最依赖的层（承重层，通过逐层消融drop识别，并与|SHAP|（Lundberg & Lee, 2017）一致）。在两个模型中，代表层位于网络中部，而承重层深度位于深度轴的两端：MLM中位于中浅层，CLM混合模型中位于深层。这种分离有直接的下游影响。在NT-v2中，一维中层标量比经典的1024维最后一层均值池化基线高出+0.049 AUROC。在Evo 2中，4096维均值池化与联合||Δh_ℓ||₂特征相当，因此标准的最后一层池化仅在基于MLM的流程中未能利用变体相关信号。

## Abstract
Downstream use of genomic foundation models follows one of three conventions: aggregating representations across all layers (Pearce et al., 2026), defaulting to the last hidden state as a fixed feature extractor (Dalla-Torre et al., 2024), or picking a single intermediate layer via mechanistic-interpretability tooling (Brixi et al., 2026). None of these examines which layer a joint classifier actually relies on. We probe this question with a minimal training-free scalar, ||{triangleup}h{ell}||2, defined as the L2 norm of the per-layer hidden-state shift at the variant token. We evaluate it on 8,008 ClinVar (Landrum et al., 2018) single-nucleotide variants in NT-v2 500M (Dalla-Torre et al., 2024), a masked language model (MLM), and Evo 2 7B (Brixi et al., 2026), a causal language model (CLM) with a hyena/attention hybrid. In both models, the layer with peak single-feature AUROC (the representative layer) is not the layer a joint multi-layer classifier most depends on (the load-bearing layer, identified by leave-one-layer-out ablation drop and concordant with |SHAP| (Lundberg & Lee, 2017)). Representative layers sit mid-network in both models, whereas load-bearing depth lies at opposite ends of the depth axis: mid-shallow in the MLM and deep in the CLM hybrid. The dissociation has direct downstream consequences. In NT-v2, a 1-dimensional mid-layer scalar exceeds the canonical 1024-dimensional last-layer mean-pool baseline by +0.049 AUROC. In Evo 2, the 4096-dimensional mean-pool is competitive with the joint ||{triangleup}h{ell}||2 feature, so standard last-layer pooling leaves variant-relevant signal untapped specifically in MLM-based pipelines.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：基因组基础模型（如NT-v2、Evo 2）在下游任务中常用的层选择策略（聚合所有层、默认使用最后一层隐藏状态、或通过可解释性工具选择单个中间层）均未考察联合分类器实际依赖的是哪一层，导致层信息可能被浪费或误用。
- **核心问题**：代表层（单特征性能最佳的层）与承重层（多层分类器最依赖的层）是否存在分离？这种分离对下游任务性能有何影响？
- **整体含义**：揭示现行层选择策略的缺陷，为基因组基础模型的下游应用提供更合理的层选择依据，尤其指出掩码语言模型（MLM）中简单中层特征可超越传统最后一层池化基线。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：无需训练，使用一个最小标量特征 `||Δh_ℓ||₂` 来量化每一层对变异信息的编码能力。
- **关键技术细节**：
  - 定义：对于每个变异位点（如单核苷酸变体），计算模型在该位点处第ℓ层的隐藏状态偏移（变异前后隐藏状态之差）的L2范数。
  - 单特征AUROC：用该标量作为单独特征，评估其对致病性分类的AUROC，峰值对应层称为**代表层**。
  - 承重层识别：通过留一层消融（leave-one-layer-out ablation）和SHAP值分析，找出当移除某一层时对多层联合分类器性能下降最大的层，即**承重层**。
- **公式或算法流程**（文字说明）：
  1. 输入变异序列，前向传播获取每层隐藏状态。
  2. 计算每个变异token在参考和替代等位基因下的隐藏状态向量，取L2范数差值作为该层标量。
  3. 对每一层，单独用该标量训练逻辑回归分类器，计算AUROC，选择最高AUROC的层为代表层。
  4. 构建包含所有层标量的联合逻辑回归模型，逐层移除并计算AUROC下降幅度，以及SHAP值，确定对模型贡献最大的层为承重层。
  5. 对比代表层与承重层在深度轴上的位置。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集**：ClinVar（Landrum et al., 2018）中的8,008个单核苷酸变体（SNV）。
- **模型**：
  - NT-v2 500M（掩码语言模型，MLM）
  - Evo 2 7B（因果语言模型，CLM，含鬣狗/注意力混合架构）
- **基准（benchmark）**：经典做法——使用最后一层均值池化（1024维或4096维）作为特征训练逻辑回归分类器的AUROC。
- **对比方法**：
  - 单层标量 `||Δh_ℓ||₂` 作为一维特征。
  - 多层联合 `||Δh_ℓ||₂` 特征。
  - 逐层消融实验。
  - SHAP值分析。

## 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点。

- **未明确说明**：论文中未提及具体的GPU型号、数量或训练时长。由于方法本身无需训练（仅需前向传播和简单逻辑回归），算力需求较低，但具体资源未列出。

## 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平

- **实验数量**：
  - 两个模型（NT-v2和Evo 2）上均进行了单特征AUROC分析、留一层消融实验、SHAP值分析。
  - 对NT-v2还比较了一维中层标量与最后一层均值池化基线的性能。
  - 对Evo 2比较了4096维均值池化与联合特征性能。
  - 包含多个表格和图表（6个表、5张图），提供定量结果。
- **充分性评估**：
  - 实验覆盖了两种主流预训练范式（MLM和CLM），具有一定代表性。
  - 消融实验和SHAP值交叉验证，增强了结论的可靠性。
  - 但仅使用一个数据集（ClinVar），未在更多下游任务（如基因调控、剪接预测等）上验证，可能影响泛化性。
  - 未进行不同模型大小或不同预训练数据多样性的对比。

## 6. 论文的主要结论与发现

- **代表层与承重层分离**：在两个模型中，代表层均位于网络中部，而承重层位置相反——MLM（NT-v2）中位于中浅层，CLM混合（Evo 2）中位于深层。
- **下游影响**：
  - 在NT-v2中，一维中层 `||Δh_ℓ||₂` 标量比传统1024维最后一层均值池化基线高出+0.049 AUROC，说明标准做法浪费了变体相关信号。
  - 在Evo 2中，4096维均值池化与联合 `||Δh_ℓ||₂` 特征性能相当，因此最后一层池化在MLM中表现不佳，但在CLM中可行。
- **核心启示**：应根据模型类型调整层选择策略，MLM应优先考虑中层特征而非最后一层。

## 7. 优点：方法或实验设计上有哪些亮点

- **方法简洁高效**：无需训练，仅用L2范数作为标量特征，计算成本极低。
- **新颖视角**：首次系统区分“代表层”与“承重层”，揭示了深度轴上的分离现象，具有理论价值。
- **实验设计严谨**：同时使用留一层消融和SHAP两种方法确认承重层，避免单一指标偏差。
- **直接下游影响验证**：通过实际对比一维中层特征与经典基线，直观展示策略改进空间。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **数据单一**：仅使用ClinVar SNV数据集，未涉及其他基因组任务（如功能元件预测、蛋白质编码效应等），结论的泛化性存疑。
- **模型覆盖有限**：仅测试了一个MLM和一个CLM混合模型，未包括其他架构（如纯Transformer、CNN混合等）或不同规模。
- **特征定义局限**：标量 `||Δh_ℓ||₂` 仅捕获隐藏状态变化的大小，忽略方向信息，可能遗漏部分区分性信号。
- **分类器简单**：仅使用逻辑回归，未尝试更复杂的分类器（如MLP、GNN），承重层分析可能受线性可分性限制。
- **未讨论层间交互**：联合分类器可能依赖层间交互，留一层消融可能低估多层协同效应。
- **实际应用限制**：结论高度依赖模型类型，用户需针对具体模型重新分析层重要性，增加使用复杂度。

（完）
