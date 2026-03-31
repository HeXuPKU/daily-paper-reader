---
title: Pan-Pharmacological Drug-Target Interaction Prediction with 3D-Informed Protein Encoding at Scale
title_zh: 大规模基于3D信息蛋白质编码的全药理学药物-靶点相互作用预测
authors: "Kawaharada, A., Ito, T., Shimizu, H."
date: 2026-03-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.27.714727v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于药物-靶点相互作用预测的多任务深度学习
tldr: 针对药物-靶点相互作用预测中结构信息利用与计算效率的权衡难题，本文提出OmniBind多任务框架。该模型通过将蛋白质三维结构编码为离散标记，并结合氨基酸序列特征，实现了对四种药理学指标的同步预测。在BindingDB大规模数据集上训练后，OmniBind在多个基准测试中超越现有SOTA模型，展现出卓越的泛化能力、生物学可解释性及全蛋白质组筛选潜力。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714727-v1/fig-001.webp\", \"caption\": \"Table 1: Effect of protein input representation and fusion strategy on 1012 drug-target interaction prediction performance 1013\", \"page\": 43, \"index\": 1, \"width\": 979, \"height\": 1251}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714727-v1/fig-002.webp\", \"caption\": \"Figure 5: Proteome–wide off–target profiling of clozapine and 1104 clomipramine by OmniBind 1105\", \"page\": 47, \"index\": 2, \"width\": 975, \"height\": 1068}]"
motivation: 旨在解决现有深度学习方法在预测多药理指标时，难以兼顾蛋白质结构信息整合与大规模计算吞吐量的问题。
method: 提出OmniBind框架，通过门控融合机制整合蛋白质三维结构的离散标记与氨基酸序列特征，实现多指标同步预测。
result: 在对抗性和时间基准测试中表现优于现有架构，并成功识别关键结合位点残基及在全蛋白质组筛选中准确找回临床靶点。
conclusion: OmniBind为多指标药物-靶点相互作用预测提供了一个准确、具备结构感知力且可解释的高效平台。
---

## 摘要
跨多个药理学终点准确预测药物-靶点结合亲和力仍具挑战性，因为大多数深度学习方法侧重于单一指标，且在整合结构信息与计算吞吐量之间面临权衡。在此，我们提出了 OmniBind，这是一个多任务框架，通过将蛋白质三级结构编码为离散的 token 序列，并通过门控融合机制将其与氨基酸序列特征整合，从而解决了这两个限制。OmniBind 在来自 BindingDB 的超过 200 万个化合物-蛋白质对上进行了训练，可在单次前向传播中同时预测四个药理学终点，为每个化合物-靶点对提供跨多个亲和力终点的全药理学图谱。在对抗性和时间基准测试中，OmniBind 始终优于最先进的架构，证明了结构编码捕捉的是物理化学相互作用原理，而非配体-蛋白质的共现模式。注意力分析揭示了具有生物学意义的结合位点识别，模型能够选择性地加权 ABL1 门控残基 T315，并对其耐药突变 T315I 做出响应。作为实际应用价值的展示，对 20,421 种人类蛋白质进行的蛋白质组范围筛选在排名前 200 的预测中找回了 85.7% 的氯氮平（clozapine）已知临床靶点，尽管其与氯米帕明（clomipramine）结构相似，但仍正确解析了其药理学图谱。OmniBind 为多终点药物-靶点相互作用预测提供了一个准确、具有结构信息且可解释的平台，可应用于先导化合物优化、脱靶安全性评估和药物重定位。

## Abstract
Accurate prediction of drug-target binding affinity across multiple pharmacological endpoints remains challenging, as most deep learning methodologies focus on a single metric and face a trade-off between incorporating structural information and computational throughput. Here we present OmniBind, a multitask framework that resolves both constraints by encoding protein tertiary structures as discrete token sequences and integrating them with amino acid sequence features through a gated fusion mechanism. Trained on over two million compound-protein pairs from BindingDB, OmniBind simultaneously predicts four pharmacological endpoints in a single forward pass, providing a pan-pharmacological profile across multiple affinity endpoints for each compound-target pair. Across adversarial and temporal benchmarks, OmniBind consistently outperforms state-of-the-art architectures, demonstrating that structural encoding captures physicochemical interaction principles rather than ligand-protein co-occurrence patterns. Attention analysis reveals biologically meaningful binding site recognition, with the model selectively weighting the ABL1 gatekeeper residue T315 and responding to its drug-resistance mutation T315I. As a demonstration of practical utility, proteome-wide screening of 20,421 human proteins recovered 85.7% of known clinical targets of clozapine within the top 200 predictions, correctly resolving its pharmacological profile despite structural similarity to clomipramine. OmniBind provides an accurate, structurally informed, and interpretable platform for multi-endpoint drug-target interaction prediction, with applications to lead optimization, off-target safety assessment, and drug repositioning.

---

## 论文详细总结（自动生成）

# 论文总结：OmniBind —— 大规模基于3D信息蛋白质编码的全药理学药物-靶点相互作用预测

### 1. 核心问题与整体含义（研究动机和背景）
药物研发面临极高的失败率和成本，核心挑战在于如何在超大规模的化学空间和蛋白质组空间中，准确预测化合物与靶点的结合亲和力。
*   **现有局限**：
    *   **结构与效率的权衡**：传统的分子对接（Docking）精度高但速度慢；深度学习方法虽快，但往往只利用一维序列，忽略了关键的三维结构信息。
    *   **单一指标局限**：多数模型仅预测单一指标（如 $IC_{50}$），无法提供临床相关的全药理学图谱（包括 $K_i, K_d, IC_{50}, EC_{50}$）。
    *   **泛化能力不足**：模型容易产生“配体偏见”，即通过记忆化合物特征而非理解物理化学相互作用来进行预测。

**OmniBind** 旨在建立一个既能利用蛋白质3D结构信息，又具备极高计算吞吐量，且能同时预测多种药理指标的统一深度学习框架。

### 2. 方法论：核心思想与关键技术
OmniBind 采用多模态融合与多任务学习的架构：
*   **蛋白质编码（双模态）**：
    *   **序列编码**：使用 Transformer 编码器处理氨基酸序列。
    *   **结构编码**：利用 **ProstT5** 模型将蛋白质三级结构转化为离散的 **3Di token 序列**（20个结构字母表）。这种方式将复杂的3D几何信息压缩为1D序列，使计算效率保持在毫秒级。
*   **门控融合机制（Gated Fusion）**：
    *   不采用简单的拼接或相加，而是通过可学习的 **Sigmoid 门控单元** 动态调整序列特征和结构特征的权重。公式逻辑为：融合特征 = (序列权重 ⊙ 序列特征) + (结构权重 ⊙ 结构特征)。
*   **化合物编码**：使用单层 **图卷积网络（GCN）** 提取分子图特征，并引入“虚拟原子”节点以捕获全局分子上下文。
*   **交互与预测**：
    *   **Transformer Decoder**：通过交叉注意力机制（Cross-Attention）模拟化合物原子与蛋白质残基之间的相互作用。
    *   **多任务输出**：在单次前向传播中并行输出 $pK_i, pK_d, pIC_{50}, pEC_{50}$ 四个预测值。

### 3. 实验设计
*   **数据集**：主要使用 **BindingDB**。
    *   训练集：2023年5月版（约228万对相互作用）。
    *   时间验证集：2024年11月版中新增的、且化合物和蛋白均未在训练集中出现的记录（约42万对）。
*   **基准测试（Benchmark）**：
    1.  **标签反转测试（Label Reversal Test）**：通过故意反转训练/测试集中的活性标签，检测模型是否过度依赖配体结构。
    2.  **时间验证（Temporal Validation）**：模拟真实的新药研发场景。
    3.  **消融实验**：对比仅用序列、仅用3Di、简单相加及门控融合的效果。
*   **对比方法**：TransformerCPI2.0、DTI-LM 等当前最先进（SOTA）的序列模型。
*   **应用场景**：FDA批准药物的重定位（针对 PDE5, KLKB1, SIRT3）、全蛋白质组（20,421个蛋白）脱靶筛选。

### 4. 资源与算力
*   **硬件**：使用了 **8张 NVIDIA A100 (40 GB)** GPU。
*   **框架**：基于 PyTorch 和 Horovod 分布式训练。
*   **时长**：训练 100 个 epoch 耗时约 **60 小时**。
*   **效率**：推理速度极快，单对预测仅需毫秒级，支持单次运行完成全蛋白质组筛选。

### 5. 实验数量与充分性
*   **实验规模**：基于超过 200 万个样本的大规模训练，涵盖了多样化的化学和蛋白空间。
*   **充分性**：
    *   进行了 **5次独立运行**（不同随机种子）并报告均值和标准差，确保结果的统计可靠性。
    *   通过消融实验证明了 3Di 结构信息和门控融合的必要性。
    *   对抗性实验（标签反转）有力地证明了模型学习的是物理化学原理而非统计相关性。
    *   实验设计严谨，严格过滤了数据泄露（如时间分割、严格的蛋白/化合物去重）。

### 6. 主要结论与发现
*   **性能领先**：在所有评估指标（RMSE, C-index, AUROC, AUPRC）上，OmniBind 均显著优于 TransformerCPI2.0 和 DTI-LM。
*   **结构感知的价值**：3Di 编码能有效捕捉局部生物物理环境，门控融合显著提升了预测精度。
*   **生物学可解释性**：注意力分析显示，模型能准确识别 ABL1 激酶的门控残基 T315，并能感知 T315I 这一临床关键耐药突变导致的信号变化。
*   **实际应用潜力**：在氯氮平的全蛋白组筛选中，前 200 个预测结果找回了 **85.7%** 的已知临床靶点，并能区分结构相似但药理图谱不同的化合物。

### 7. 优点
*   **高效整合结构信息**：通过 3Di token 巧妙避开了 3D 几何网络的高昂计算成本，实现了“结构精度”与“序列速度”的结合。
*   **全药理学视野**：多任务学习不仅提高了预测效率，还通过指标间的关联增强了模型的鲁棒性。
*   **强大的泛化与抗偏见能力**：在对抗性测试中表现稳健，证明其具有真正的分子识别能力。
*   **端到端可解释性**：Decoder 的注意力权重可直接映射回蛋白质残基，辅助理解结合机制。

### 8. 不足与局限
*   **数据偏差风险**：模型性能仍受限于 BindingDB 的数据质量和覆盖范围，对于某些罕见蛋白家族或新型化学支架可能存在预测偏差。
*   **静态结构限制**：虽然引入了 3Di 信息，但主要基于静态预测结构，尚未考虑蛋白质的构象动态（Dynamics）、变构效应（Allosteric effects）或后翻译修饰。
*   **依赖外部预测工具**：3Di 序列的质量依赖于 ProstT5 和 Foldseek 等工具的准确性。
*   **体内环境缺失**：模型预测的是体外结合亲和力，无法直接反映复杂的体内药代动力学（PK）过程。

（完）
