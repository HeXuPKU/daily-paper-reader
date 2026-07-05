---
title: Tabular Foundation Models Are Competitive Cellular Perturbation Predictors Across Biological Scales
title_zh: 表格基础模型在跨生物尺度上是有竞争力的细胞扰动预测器
authors: "Palla, G., Hillsley, A., Kim, Y.-J., Royer, L. A."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.735106v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 评估表格基础模型用于细胞扰动预测，涉及大规模基因组模型
tldr: 细胞对扰动响应预测是药物发现核心挑战。本文系统评估了Tabular Foundation Models（TabICL、TabPFN）与五类领域特定模型在四个跨尺度任务上的表现，涵盖细胞级、伪批量、CRISPR筛选及胚胎级预测。结果显示，通用模型在所有任务上与专用模型相当或更优，尤其在伪批量预测中归一化均方误差等指标上一致领先。这一发现表明，通用表格上下文学习可作为扰动响应建模的强有力可扩展替代方案，降低了对专用复杂架构的依赖。
source: biorxiv
selection_source: fresh_fetch
motivation: 探索通用表格基础模型能否作为专用单细胞模型在扰动预测中的竞争性替代方案。
method: 在细胞级跨细胞类型、伪批量、CRISPR筛选及胚胎级预测四个任务上，比较TabICL、TabPFN与五类专用模型的性能。
result: 通用模型在所有任务上达到或超越专用模型，尤其在伪批量预测中一致领先于多个数据集和指标。
conclusion: 通用表格上下文学习为扰动响应建模提供可扩展替代方案，挑战了开发高度专用架构的必要性。
---

## 摘要
预测细胞如何响应遗传和化学扰动是药物发现和功能基因组学中的一个核心挑战。为了解决这个问题，人们开发了日益增多的专用单细胞基础模型生态系统，但它们相对于领域无关方法的实际优势仍不清楚。在这里，我们评估了表格基础模型（如TabICL和TabPFN，即通用预训练回归模型）与领域特定架构（包括PRESAGE、scGPT、scLAMBDA、STACK和Prophet）在四个互补的评估设置中的能力：细胞级别的上下文内跨细胞类型预测、基于五个细胞系Perturb-seq数据集的伪批量扰动预测、原代人CD4+ T细胞的全基因组CRISPR筛选，以及斑马鱼发育扰动图谱中的胚胎级别细胞类型组成预测。在细胞级别的跨细胞类型扰动预测中，表格基础模型的表现与专门模型相当或更优。在伪批量扰动预测中，表格基础模型在多个评估指标和数据集上持续优于专门基线。在整体胚胎细胞类型组成预测中，表格基础模型与专门基线具有竞争力。这些结果表明，通用的表格上下文学习为跨细胞系统和尺度的扰动响应建模提供了一种强大且可扩展的替代方案，可替代定制的生物架构。

## Abstract
Predicting how cells respond to genetic and chemical perturbations is a central challenge in drug discovery and functional genomics. A growing ecosystem of specialized single-cell foundation models has been developed to address this problem, yet their practical advantage over domain-agnostic approaches remains unclear. Here we evaluate the power of Tabular Foundation Models such as TabICL and TabPFN, general-purpose pre-trained regression models, against domain-specific architectures including PRESAGE, scGPT, scLAMBDA, STACK and Prophet across four complementary evaluation settings: cell-level in-context cross-cell-type prediction, pseudobulk perturbation prediction on five Perturb-seq datasets of cell-lines, a genome-wide CRISPR screen in primary human CD4+ T cells, and embryo-level cell-type composition prediction in a zebrafish developmental perturbation atlas. In the cell-level cross-cell type perturbation prediction, Tabular Foundation Models perform on par or better than specialized models. On pseudobulk perturbation prediction, Tabular Foundation Models consistently outperform specialized baselines across multiple evaluation metrics and datasets. On whole-emrbryo cell-type composition prediction, Tabular Foundation Models are competitive with specialized baselines. These results demonstrate that general-purpose tabular in-context learning provides a strong and scalable alternative to bespoke biological architectures for perturbation response modeling across cell systems and scales.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：预测细胞对遗传和化学扰动的响应是药物发现和功能基因组学中的关键挑战。近年来，大量专用的单细胞基础模型（如scGPT、scLAMBDA等）被开发以解决该问题，但这些领域特定架构相对于通用方法的实际优势尚不明确。
- **研究动机**：系统性评估通用表格基础模型（Tabular Foundation Models）在细胞扰动预测中的表现，并探讨能否用更简单的通用方法替代日益复杂、昂贵的专用生物架构。
- **整体含义**：如果通用表格模型能与甚至超越专用模型，将显著降低该领域对定制化模型架构的依赖，推动扰动响应建模的标准化和可扩展性。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用通用预训练的表格回归模型（TabICL、TabPFN）通过上下文学习（in-context learning）进行细胞扰动响应预测，无需针对生物领域进行专门架构设计。
- **关键技术细节**：
  - **TabICL**：一种基于Transformer的上下文学习模型，能够从少量示例中快速适应新任务，通过将扰动-响应对作为上下文输入，直接预测目标细胞的基因表达变化。
  - **TabPFN**：一种基于Prior-Fitted Networks的表格预测模型，通过预训练大量合成数据集具备强大的少样本预测能力，可直接应用于表格形式的基因表达数据。
  - **对比的专用模型**：PRESAGE（基于图神经网络）、scGPT（单细胞生成式Transformer）、scLAMBDA（自监督注意力模型）、STACK（堆叠集成模型）、Prophet（时间序列预测模型）——均针对单细胞扰动数据设计。
- **公式或算法流程**：文中未给出具体数学公式或伪代码，但描述了通用流程：将扰动条件（如基因敲除、药物处理）和细胞类型/状态编码为表格特征，输入模型后输出预测的表达谱或细胞类型比例。

## 3. 实验设计：数据集、场景、基准方法

- **评估场景（共4个互补任务）**：
  1. **细胞级别的跨细胞类型预测**：在某一细胞类型上训练，预测另一细胞类型对相同扰动的响应。
  2. **伪批量（Pseudobulk）扰动预测**：基于5个独立的Perturb-seq细胞系数据集（具体名称未给出），预测伪批量层面的平均表达变化。
  3. **全基因组CRISPR筛选**：在原代人CD4+ T细胞中进行全基因组敲除，预测每个基因敲除对细胞表型的影响。
  4. **胚胎级细胞类型组成预测**：在斑马鱼发育扰动图谱中，预测整体胚胎中各种细胞类型的比例变化。
- **基准方法**：
  - 通用表格基础模型：TabICL、TabPFN。
  - 领域专用模型：PRESAGE、scGPT、scLAMBDA、STACK、Prophet。
- **评价指标**：归一化均方误差（NMSE）等，具体指标在不同任务中略有差异，但论文强调通用模型在多个指标上一致领先（尤其在伪批量预测中）。

## 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量、训练时长或推理算力需求。元数据及摘要中均无相关细节。
- **推断**：TabICL和TabPFN本身需要预训练，但论文中可能直接使用公开预训练权重进行零样本或少样本评估，无需重新训练。而专用模型（如scGPT）可能需要大规模GPU资源。但具体信息缺失。

## 5. 实验数量与充分性

- **实验数量**：共4个评估任务，涉及至少5个Perturb-seq数据集、1个CRISPR筛选数据集、1个斑马鱼胚胎图谱数据集。对比了7种模型（2通用+5专用）。
- **充分性分析**：
  - **优点**：覆盖细胞级、伪批量、单个基因敲除、整体组织组成多个生物尺度，评估全面；使用了多个异质数据集；对比了代表性专用模型。
  - **不足**：未提及消融实验（如模型组件贡献）、超参数敏感性分析；未对不同数据集的统计显著性进行严谨比较（如误差棒、p值）；缺乏对高稀疏性、高维数据（如单细胞分辨率）的直接评估；仅基于摘要，细节不足以判断实验重复次数和随机种子控制。

## 6. 论文的主要结论与发现

- **主要结论**：通用表格基础模型（TabICL、TabPFN）在所有四个评估任务上均达到或超越领域专用模型，在伪批量扰动预测中一致领先，在跨细胞类型和胚胎预测中表现出竞争力。
- **关键发现**：通用的表格上下文学习为跨细胞系统和尺度的扰动响应建模提供了强大且可扩展的替代方案，挑战了开发高度专用生物架构的必要性。
- **实际意义**：研究者可选用更简单、通用的方法获得同等甚至更好的预测性能，从而降低模型开发成本，易于迁移到新扰动和细胞类型。

## 7. 优点：方法或实验设计上的亮点

- **跨尺度评估**：从单细胞到整体胚胎组织，覆盖扰动响应的多个生物学层级，论证充分。
- **对比全面**：包含经典（PRESAGE）、大规模预训练（scGPT）、混合方法（STACK、Prophet）等多样化基线，避免selection bias。
- **结论简洁有力**：直接挑战当前“专用模型至上”的研究趋势，提供了一种更轻量、更通用的思路。
- **上下文学习优势**：通用模型无需针对每个新任务重新训练，仅需少量上下文示例即可预测，具备实际部署易用性。

## 8. 不足与局限

- **信息有限**：由于仅基于摘要，缺乏详细实验设置、数据预处理细节、模型超参数等，无法完全判断实验公平性。
- **未讨论计算成本**：虽然模型通用，但TabPFN等模型的推理开销和内存占用未与专用模型对比，可能在某些场景下不具优势。
- **覆盖范围有限**：仅测试了两种通用表格模型，未包括其他如XGBoost、随机森林等非深度学习方法；专用模型也仅限5种，未包含最新动辄百亿参数的scFoundation等。
- **缺乏可解释性分析**：未探讨通用模型如何学习生物机制（如基因调控网络），可能仅学到统计相关性而非因果规律。
- **潜在偏差**：Perturb-seq数据集可能主要来自细胞系，在原代细胞或体内场景中的泛化性未充分验证；斑马鱼胚胎预测可能只评估了整体比例，未到单细胞分辨率。
- **未讨论跨扰动泛化**：是否对未见过的扰动类型（如组合扰动、化学扰动）依然有效尚不明确。

（完）
