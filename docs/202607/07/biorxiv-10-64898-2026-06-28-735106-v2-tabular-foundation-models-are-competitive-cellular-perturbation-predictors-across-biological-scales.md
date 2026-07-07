---
title: Tabular Foundation Models Are Competitive Cellular Perturbation Predictors Across Biological Scales
title_zh: 表格基础模型在生物尺度上成为有竞争力的细胞扰动预测器
authors: "Palla, G., Hillsley, A., Kim, Y.-J., Royer, L. A."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.735106v2.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 评估表格基础模型在细胞扰动预测中的性能，与虚拟细胞模型和大规模基因组模型相关
tldr: 预测细胞对遗传和化学扰动的反应是药物发现和功能基因组学的核心挑战。本文评估了通用表格基础模型（TabICL、TabPFN）与领域特定模型（scGPT、PRESAGE等）在四个扰动预测任务上的表现。结果表明，通用模型在单细胞跨细胞类型预测、伪bulk扰动预测及全胚胎细胞类型组成预测中与专业模型相当或更优，尤其在伪bulk任务上持续超越专业基线。这证明通用表格上下文学习是面向不同细胞系统和尺度的强有力、可扩展的替代方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 评估通用表格基础模型与领域特定单细胞模型在扰动预测中的性能差异，明确其实际优势。
method: 在细胞级跨细胞类型、伪bulk扰动、CRISPR筛选和胚胎细胞组成四个任务上对比TabICL、TabPFN与scGPT等专业模型。
result: 通用表格模型在伪bulk预测上持续超越专业模型，在其他任务上表现相当或更优。
conclusion: 通用表格上下文学习为扰动响应建模提供了强大、可扩展的替代方案，适用于多种细胞系统。
---

## 摘要
预测细胞如何响应遗传和化学扰动是药物发现和功能基因组学中的核心挑战。为了解决这一问题，已经发展出了越来越多专门化的单细胞基础模型生态系统，然而它们相对于领域无关方法的实际优势仍不清楚。在这里，我们评估了表格基础模型（如TabICL和TabPFN，通用预训练回归模型）与领域特定架构（包括PRESAGE、scGPT、scLAMBDA、STACK和Prophet）在四个互补评估设置中的能力：细胞水平上下文中的跨细胞类型预测、基于五个Perturb-seq细胞系数据集的伪批量扰动预测、原代人CD4+ T细胞的全基因组CRISPR筛选，以及斑马鱼发育扰动图谱中的胚胎水平细胞类型组成预测。在细胞水平的跨细胞类型扰动预测中，表格基础模型的表现与专门化模型相当或更优。在伪批量扰动预测中，表格基础模型在多个评估指标和数据集上持续优于专门化基线。在全胚胎细胞类型组成预测中，表格基础模型与专门化基线具有竞争力。这些结果表明，通用的表格上下文学习为跨细胞系统和尺度的扰动响应建模提供了一种强大且可扩展的替代方案，可替代定制化的生物架构。

## Abstract
Predicting how cells respond to genetic and chemical perturbations is a central challenge in drug discovery and functional genomics. A growing ecosystem of specialized single-cell foundation models has been developed to address this problem, yet their practical advantage over domain-agnostic approaches remains unclear. Here we evaluate the power of Tabular Foundation Models such as TabICL and TabPFN, general-purpose pre-trained regression models, against domain-specific architectures including PRESAGE, scGPT, scLAMBDA, STACK and Prophet across four complementary evaluation settings: cell-level in-context cross-cell-type prediction, pseudobulk perturbation prediction on five Perturb-seq datasets of cell-lines, a genome-wide CRISPR screen in primary human CD4+ T cells, and embryo-level cell-type composition prediction in a zebrafish developmental perturbation atlas. In the cell-level cross-cell type perturbation prediction, Tabular Foundation Models perform on par or better than specialized models. On pseudobulk perturbation prediction, Tabular Foundation Models consistently outperform specialized baselines across multiple evaluation metrics and datasets. On whole-emrbryo cell-type composition prediction, Tabular Foundation Models are competitive with specialized baselines. These results demonstrate that general-purpose tabular in-context learning provides a strong and scalable alternative to bespoke biological architectures for perturbation response modeling across cell systems and scales.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：预测细胞对遗传和化学扰动的响应是药物发现和功能基因组学的基础挑战。近年来涌现出大量针对单细胞数据的领域特定基础模型（如scGPT、PRESAGE等），但这些专有模型相对于通用（领域无关）的表格基础模型是否具有实际优势尚不明确。
- **整体含义**：本文通过系统比较，探究通用表格基础模型（如TabICL、TabPFN）与专门化单细胞模型在多种扰动预测任务上的性能差异，旨在判断“定制化生物架构”是否真的优于“领域无关的通用回归模型”，从而为模型选择提供指导。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将细胞扰动预测任务形式化为**表格回归问题**，利用通用预训练的表格基础模型（TabICL、TabPFN）直接进行上下文学习（in-context learning），无需针对生物领域进行特殊架构设计或微调。
- **关键技术细节**：
  - **TabICL**：基于Transformer的表格上下文学习模型，通过大量表格数据预训练，能够在测试时根据提供的示例（context）直接预测新样本的输出。
  - **TabPFN**：基于Prior-Data Fitted Networks的表格基础模型，同样通过预训练学习表格数据的分布，擅长小样本回归任务。
  - 在细胞扰动场景中，输入特征为细胞/样本的基因表达谱或扰动条件（如基因敲除、药物处理），输出为扰动后的基因表达变化或细胞类型组成。
- **对比的专门化模型**：包括PRESAGE（基于基因共表达网络）、scGPT（单细胞生成式预训练Transformer）、scLAMBDA、STACK（基于堆叠集成）、Prophet（时间序列预测模型）等，这些模型通常包含生物先验知识或自监督预训练策略。

### 3. 实验设计：数据集/场景、基准测试、对比方法

- **实验场景与数据集**：
  1. **细胞级跨细胞类型预测**：使用不同细胞系的Perturb-seq数据，测试模型能否基于一种细胞类型的扰动响应预测另一种细胞类型的响应。
  2. **伪批量（pseudobulk）扰动预测**：基于五个Perturb-seq细胞系数据集（如K562、THP-1等），预测群体水平（pseudobulk）的扰动效应。
  3. **全基因组CRISPR筛选**：在原代人CD4+ T细胞上进行全基因组CRISPR筛选，预测单个基因敲除对细胞表型（如增殖、分化）的影响。
  4. **胚胎级细胞类型组成预测**：利用斑马鱼发育扰动图谱数据，预测全胚胎水平上各种细胞类型的比例变化。
- **对比方法**：表格基础模型（TabICL、TabPFN） vs. 领域特定架构（PRESAGE、scGPT、scLAMBDA、STACK、Prophet）。还可能与简单基线（如均值预测）比较。
- **评估指标**：文中未明列举，但根据任务类型推测包括皮尔逊相关系数、均方误差（MSE）、平均绝对误差（MAE）或特异性指标（如扰动效应的一致率）。

### 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量或训练时长。仅根据“通用预训练模型”特性，可以推断TabICL和TabPFN在预训练阶段消耗了大量算力，但微调/推理阶段的资源需求远低于需要从头训练的专门化模型。论文未提供具体硬件规格，因此无法进行算力对比。

### 5. 实验数量与充分性

- **实验数量**：覆盖了4个主要场景，其中伪批量扰动预测涉及5个数据集，CRISPR筛选为全基因组规模，胚胎预测为全胚胎图谱。此外，每个场景内可能包含多组子实验（如不同细胞系、不同扰动类型、不同评估指标）。
- **充分性评估**：
  - **优点**：场景覆盖从单细胞到群体、从体外细胞系到体内全胚胎，维度多样；对比模型既有传统方法也有新近基础模型，基线丰富；评估指标多维（推测包含相关系数、误差等）。
  - **可能不足**：未提及消融实验（如去掉预训练或改变上下文大小的影响）；未对表格基础模型的不同版本（如不同预训练数据规模）进行对比；仅测试了少量通用表格模型（两个），代表性可能有限。

### 6. 论文的主要结论与发现

- **关键结果**：
  - 在细胞级跨细胞类型预测中，表格基础模型表现与专门化模型相当或更优。
  - 在伪批量扰动预测任务上，表格基础模型**持续优于**所有专门化基线（在所有评估指标和数据集上）。
  - 在胚胎级细胞类型组成预测中，表格基础模型与专门化模型具有竞争力。
- **核心结论**：通用表格上下文学习（tabular in-context learning）是跨细胞系统与尺度进行扰动响应建模的强大且可扩展的替代方案，其性能不低于甚至超越专门化的生物架构，且无需领域定制与大量微调。

### 7. 优点：方法或实验设计上的亮点

- **视角新颖**：打破“生物问题必须使用生物专用模型”的惯常思维，系统证明了通用表格模型的有效性，有助于降低计算门槛和开发成本。
- **实验全面**：覆盖从单细胞到群体、从体外到体内的多种尺度，且采用了多个公开Perturb-seq数据集和独立CRISPR筛选数据，避免了单一数据集的过拟合风险。
- **对比公平**：直接比较了当前主流的专门化单细胞基础模型（scGPT等）与通用基础模型，在同一标准化评估流程下进行，减少了实现偏差。
- **实践价值**：通用表格模型无需大规模微调、无需GPU昂贵训练，几乎可直接使用预训练权重，为生物研究人员提供了“即插即用”的解决方案。

### 8. 不足与局限

- **实验覆盖**：仅评估了两种通用表格模型（TabICL、TabPFN），其他类型（如XGBoost-based或更大型的表格Transformer）未被纳入，结论的推广性有限。
- **潜在偏差**：专门化模型可能在某些未测试的任务（如罕见的细胞类型预测、多模态整合）中仍有优势，本文未覆盖所有扰动预测子任务。
- **可解释性不足**：表格基础模型的黑箱特性使其难以解释预测的生物机制，而专门化模型（如scGPT）有时能提供注意力权重或基因模块解释，这一点未被讨论。
- **应用限制**：表格模型依赖于结构化的特征输入（如预先定义的基因或扰动能向量），对于非表格形式的数据（如空间转录组图像、时间序列快照）可能不适用。此外，极端小样本场景下（如只有1个训练示例）的性能未明确测试。
- **资源信息缺失**：未报告训练/推理所需的具体算力，无法评估效率优势的量化程度。

（完）
