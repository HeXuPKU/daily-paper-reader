---
title: "Representative vs. Load-bearing Layers: A Dissociation in Genomic Foundation Models"
title_zh: 代表性层与承重层：基因组基础模型中的分离现象
authors: "Cho, Y., Kim, M. S., Kim, S."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.16.739040v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 利用ClinVar变异分析基因组基础模型各层的重要性
tldr: "基因组基础模型下游使用通常采用全层聚合、最后隐状态或单中间层，但未探究联合分类器实际依赖的层。本文提出免训练标量||Δh_ℓ||₂（变体token处隐藏状态变化的L2范数），在NT-v2 500M（MLM）和Evo 2 7B（CLM hybrid）上评估8008个ClinVar变异。发现代表性层（单特征AUROC峰值）与负载层（联合分类器依赖层）不一致：MLM中负载层偏中层浅层，CLM hybrid中偏深层。MLM中单中层标量AUROC超最后层平均池化基线+0.049，表明标准最后层池化未充分利用变异信号。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1661, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 865, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1661, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1597, \"height\": 1067, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 168, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1191, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 666, \"height\": 600, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739040-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 821, \"height\": 478, \"label\": \"Table\"}]"
motivation: 现有方法未揭示基因组模型联合分类器实际依赖的层，导致下游使用可能错失关键特征。
method: "定义免训练标量||Δh_ℓ||₂衡量每层隐藏状态变异token处的L2范数，在NT-v2 500M和Evo 2 7B上评估ClinVar变异。"
result: 代表性层与负载层分离；MLM中负载层位于中层浅层，CLM hybrid中位于深层，且MLM中单层特征超越最后层池化基线。
conclusion: 标准最后层池化在MLM中遗漏变异关键信号，需选用负载层特征以提升变异预测性能。
---

## 摘要
基因组基础模型的下游使用遵循三种惯例之一：聚合所有层的表示（Pearce等人，2026）、默认使用最后一个隐藏状态作为固定特征提取器（Dalla-Torre等人，2024）、或通过机械可解释性工具选择单个中间层（Brixi等人，2026）。这些方法都没有检查联合分类器实际依赖的是哪一层。我们使用一个最小化的无需训练的标量||Δh_ℓ||2来探究这个问题，该标量定义为变体标记处逐层隐藏状态变化的L2范数。我们在NT-v2 500M（Dalla-Torre等人，2024，一个掩码语言模型MLM）和Evo 2 7B（Brixi等人，2026，一个具有hyena/注意力混合架构的因果语言模型CLM）上，对8,008个ClinVar（Landrum等人，2018）单核苷酸变体进行了评估。在两个模型中，具有峰值单特征AUROC的层（代表性层）并不是联合多层分类器最依赖的层（承重层，通过逐层剔除的消融下降来识别，并与|SHAP|（Lundberg & Lee，2017）一致）。两个模型中代表性层位于网络中部，而承重层深度位于深度轴的两端：在MLM中位于中浅层，在CLM混合中位于深层。这种分离具有直接的下游影响。在NT-v2中，一个一维的中间层标量比典型的1024维最后一层均值池化基线高出+0.049 AUROC。在Evo 2中，4096维的均值池化与联合||Δh_ℓ||2特征具有竞争力，因此标准的最后一层池化仅在基于MLM的流水线中未能充分利用变体相关信号。

## Abstract
Downstream use of genomic foundation models follows one of three conventions: aggregating representations across all layers (Pearce et al., 2026), defaulting to the last hidden state as a fixed feature extractor (Dalla-Torre et al., 2024), or picking a single intermediate layer via mechanistic-interpretability tooling (Brixi et al., 2026). None of these examines which layer a joint classifier actually relies on. We probe this question with a minimal training-free scalar, ||{triangleup}h{ell}||2, defined as the L2 norm of the per-layer hidden-state shift at the variant token. We evaluate it on 8,008 ClinVar (Landrum et al., 2018) single-nucleotide variants in NT-v2 500M (Dalla-Torre et al., 2024), a masked language model (MLM), and Evo 2 7B (Brixi et al., 2026), a causal language model (CLM) with a hyena/attention hybrid. In both models, the layer with peak single-feature AUROC (the representative layer) is not the layer a joint multi-layer classifier most depends on (the load-bearing layer, identified by leave-one-layer-out ablation drop and concordant with |SHAP| (Lundberg & Lee, 2017)). Representative layers sit mid-network in both models, whereas load-bearing depth lies at opposite ends of the depth axis: mid-shallow in the MLM and deep in the CLM hybrid. The dissociation has direct downstream consequences. In NT-v2, a 1-dimensional mid-layer scalar exceeds the canonical 1024-dimensional last-layer mean-pool baseline by +0.049 AUROC. In Evo 2, the 4096-dimensional mean-pool is competitive with the joint ||{triangleup}h{ell}||2 feature, so standard last-layer pooling leaves variant-relevant signal untapped specifically in MLM-based pipelines.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：基因组基础模型（如NT-v2、Evo 2）在下游任务（如变异致病性预测）中通常采用三种方法之一：聚合所有层的表示、取最后一个隐藏状态作为固定特征提取器、或利用可解释性工具选择单个中间层。但这些方法均未回答一个关键问题：**联合分类器实际依赖的是哪一层？** 同时，现有做法默认将“信号最强的层”（代表性层）等同于“模型最依赖的层”（承重层），这一隐含假设是否成立尚不清楚。

- **核心问题**：在基因组基础模型中，**单层独立解译能力最强的层（代表性层）与联合多层分类器最依赖的层（承重层）是否存在分离？** 这种分离是否具有架构依赖性？对下游应用有何影响？

- **整体含义**：该研究揭示了现有下游协议可能错误地使用了模型内部表示，特别是在掩码语言模型（MLM）中，标准最后的隐藏状态池化会丢失变异关键信号，从而导致性能损失。这为更精确地提取基因组基础模型的特征提供了指导。

### 2. 论文提出的方法论：核心思想、关键技术细节与流程

- **核心思想**：定义一个无需训练的标量探针 $\|\Delta h_{\ell}\|_2$（即变异 token 处逐层隐藏状态变化的 L2 范数），以此衡量每层对序列变异（ref/alt）的敏感性。然后提出两个操作定义：
  - **代表性层（Representative layer）**：单特征（$\|\Delta h_{\ell}\|_2$）在逻辑回归中取得最高 AUROC 的层，回答“信号在哪里”。
  - **承重层（Load-bearing layer）**：在联合多层分类器（将各层 $\|\Delta h_{\ell}\|_2$ 堆叠成 L 维特征）中，逐层剔除（leave-one-layer-out）后 AUROC 下降最大的层，并用 SHAP 值佐证，回答“联合模型依赖什么”。

- **关键技术细节**：
  - 对每个变异，分别用参考序列和替代序列进行一次前向传播，提取每层隐藏状态，计算 $\|\Delta h_{\ell}\|_2 = \|h_{\ell}^{alt}[v] - h_{\ell}^{ref}[v]\|_2$（v 为变异 token 位置）。
  - 将各层标量堆叠为 L 维特征，使用逻辑回归（10 折分层交叉验证）训练分类器，报告 out-of-fold AUROC。
  - 通过逐层消融和 SHAP 识别承重层。
  - 对比三种替代标量（余弦距离、L1 范数、方向投影），确认分离现象一致。

- **算法流程**（文字说明）：
  1. 对每个变异进行参考/替代前向传播。
  2. 对每层 $\ell$ 计算 $\|\Delta h_{\ell}\|_2$。
  3. 单层 AUROC：用 $\|\Delta h_{\ell}\|_2$ 作为唯一特征训练逻辑回归，记录 AUROC，取峰值层为代表性层。
  4. 联合 AUROC：用所有层标量组成的 L 维特征训练逻辑回归，得到基线 AUROC。
  5. 消融：依次剔除一层，用剩余 L-1 层重新训练，计算 AUROC 下降，最大下降对应承重层。
  6. 使用 LightGBM + SHAP 进行一致性验证。

### 3. 实验设计：数据集、场景、基准与方法对比

- **数据集**：**ClinVar**（Landrum 等人，2018）中的 **8,008 个单核苷酸变异**，来自 15 个高外显率癌症相关基因（例如 BRCA1, BRCA2, TP53, EGFR 等）。其中致病/可能致病变异（P/LP）3,514 个，良性/可能良性（B/LB）4,494 个。
- **评估场景**：变异致病性二分类预测（damaging vs. tolerant proxy）。
- **基准（Baselines）**：
  - 对于 NT-v2（MLM）：标准最后层均值池化（1024 维隐藏状态均值），AUROC=0.881。
  - 对于 Evo 2（CLM）：标准最后层均值池化（4096 维），AUROC=0.961。
  - 同时比较了联合多层 $\|\Delta h_{\ell}\|_2$ 特征（L=30 或 32）以及单层峰值特征。
- **对比方法**：
  - 单层特征（不同层的 $\|\Delta h_{\ell}\|_2$）。
  - 联合多层特征（全层堆叠）。
  - 消融实验（leave-one-layer-out）。
  - SHAP 归属分析。
  - 另外对比了三种不同标量还原方法（L1、余弦、方向投影）以验证稳健性。
  - 还引入容量受限的 **HyenaDNA-large**（6.6M 参数）作为第三个控制点。

### 4. 资源与算力

- **论文未明确说明使用的 GPU 型号、数量及训练时长**。文中仅提及模型是冻结的（frozen），只进行推理提取隐藏状态和训练简单的逻辑回归，计算开销较小。Evo 2 推理使用 bfloat16，NT-v2 使用 float32。对于 8,008 个变异、两个模型的全层提取，实际算力需求可能在几个 GPU 小时内完成，但具体资源未披露。

### 5. 实验数量与充分性

- **实验组数**：
  - 核心实验：在 NT-v2 和 Evo 2 上逐层 AUROC 曲线（各 30/32 层），联合 AUROC，消融 AUROC 下降，SHAP 重要性。
  - 消融实验：leave-one-layer-out 进行 L 次（NT-v2 30 次，Evo 2 32 次）。
  - 稳健性检验：三种其他标量还原（余弦、L1、方向投影）重复分析，得到一致分离结果。
  - 控制实验：
    - 置换检验：1000 次单特征 null 分布，200 次联合 null 分布。
    - 基因平衡子采样：50 次试验。
    - 替代物分层：12 种有序替代分类分别计算 AUROC。
    - 留一基因（LOGO）分析：NT-v2 上每基因单独左出评估。
    - HyenaDNA 大模型（容量受限）作为第三个架构控制点。
  - 统计检验：1000 次 bootstrap 置信区间、DeLong 检验、Mann-Whitney U、Cohen's d。
- **充分性判断**：实验设计较为全面，覆盖了主效应、消融、替代指标、混淆因素控制、统计显著性检验。但缺少**干净因果分离实验**（如相同架构、不同目标、相同数据）来归因架构差异。作者也承认了这一局限。整体而言，实验在给定范围内是充分且客观的。

### 6. 论文的主要结论与发现

1. **分离现象成立**：在 NT-v2（MLM）和 Evo 2（CLM 混合）中，代表性层（单特征 AUROC 峰值）与承重层（联合分类器最依赖的层）不一致。  
   - NT-v2：代表性层 L15（AUROC 0.930），承重层 L9（消融下降最大）。
   - Evo 2：代表性层 L8（AUROC 0.855），承重层 L29（消融下降最大）。
2. **跨架构深度差异**：代表性层在两个模型中均位于网络中部（相对深度 0.52 和 0.25），但承重层深度相反——MLM 中偏早（相对深度 0.31），CLM 混合中偏晚（相对深度 0.91）。HyenaDNA（容量小）承重层退化为输入嵌入层（L0）。
3. **下游影响**：MLM 中标准最后层均值池化（AUROC 0.881）被简单的 1 维中间层标量（AUROC 0.930）超越，表明 MLM 流水线浪费了变异信号。而 Evo 2 的最后层均值池化已经很强（0.961），因此该问题仅限于 MLM。
4. **抑制层现象**：部分层单特征 AUROC 高，但在联合分类器中系数为负，起抵消替代偏置的作用。

### 7. 优点

- **方法简洁高效**：$\|\Delta h_{\ell}\|_2$ 是免训练、旋转不变的标量，计算成本极低，且能揭示模型内部表示结构。
- **操作定义清晰**：将“代表性”与“承重性”分离，避免了传统单层探针的混淆，提供了可复制的分析方法。
- **跨架构系统性分析**：涵盖 MLM、CLM 混合、纯 Hyena 架构（容量小），显示了分离现象的普遍性和架构依赖性。
- **充分的稳健性检验**：包括多种标量还原、置换检验、基因平衡、替代物分层、Bootstrap 和 DeLong 检验，结果可信度高。
- **实践意义明确**：指出 MLM 下游使用应优先选择中间层而非最后层，直接指导实际应用。

### 8. 不足与局限

- **实验覆盖有限**：仅评估一个任务（变异致病性预测）和两个主要模型（加一个容量控制），未在其他任务（如表达预测、染色质状态）或其他模型（如 DNABERT、Enformer）上验证。
- **跨架构因果归因不足**：NT-v2 与 Evo 2 在目标函数、容量、架构、分词、数据等多方面不同，无法将承重层深度差异归因于单一因素。作者承认是观察性结果。
- **读出头仅用线性模型**：使用逻辑回归可能无法挖掘更复杂的非线性关系，但作者逻辑是保持分析简单以聚焦于表示本身。
- **最终层崩溃的解释推测性**：NT-v2 最后层 AUROC 接近随机且部分基因符号颠倒，作者解释为 MLM 最终层旋转到重建子空间所致，但缺乏直接的激活修补实验验证。
- **计算资源未报告**：虽然推理成本低，但未披露 GPU 型号、时间等，对可重复性略有影响（但代码已开源）。
- **局限总结**：论文明确指出这些限制不影响内部模型分离现象的稳健性，但跨架构结论需谨慎推广。

（完）
