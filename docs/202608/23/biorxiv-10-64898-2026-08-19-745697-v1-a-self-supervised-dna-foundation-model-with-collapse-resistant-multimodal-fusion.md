---
title: A self-supervised DNA foundation model with collapse-resistant multimodal fusion
title_zh: 具有抗坍缩多模态融合的自监督DNA基础模型
authors: "Chen, Y."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.19.745697v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 自监督DNA基础模型与抗坍缩多模态融合
tldr: DNA基础模型多只利用序列，缺失染色质可及性等调控信息；现有多模态模型任务特化且异构融合易坍缩。提出自监督DNA多模态基础模型，在共享编码器中融合序列嵌入与局部/全局染色质可及性，用全局归一化抑制坍缩。在调控活性预测、信号排序和峰值检测上优于DNA-only基线，峰值检测AUPRC提升4.6倍，ClinVar等外部验证有效。框架可扩展至更多调控模态，为多模态DNA基础模型提供方法论基础。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1696, \"height\": 969}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1633, \"height\": 1476}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1671, \"height\": 1183}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1677, \"height\": 1509}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1684, \"height\": 1337}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1669, \"height\": 1231}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1728, \"height\": 272}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1740, \"height\": 308}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1743, \"height\": 362}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1742, \"height\": 360}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1733, \"height\": 235}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1746, \"height\": 235}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1740, \"height\": 235}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1716, \"height\": 510}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1715, \"height\": 600}]"
motivation: 序列单模态缺失调控信息，现有多模态模型任务特化，且异构模态融合易坍缩到零解。
method: 提出自监督DNA多模态模型，融合序列嵌入与局部/全局染色质可及性，用全局归一化抗坍缩。
result: 调控活性、信号排序、峰值检测均提升，AUPRC提高4.6倍，外部数据集验证有效。
conclusion: 框架可扩展至更多调控模态，为多模态DNA基础模型提供方法论基础。
---

## 摘要
在DNA序列上预训练的基因组基础模型已在多种任务中取得了优异性能，但仅基于序列的表征无法完全捕捉反映在额外DNA中心模态中的调控信息。现有的多模态基因组模型通常针对特定预测任务进行优化，而非用于学习可跨下游分析复用的嵌入表示。然而，直接融合异质性基因组模态颇具挑战，因为稀疏的峰状调控信号与密集的序列表示具有显著不同的统计结构，使得朴素的多模态对齐容易退化为近零解的坍缩状态。我们提出了一种自监督的DNA中心多模态基础模型来解决这一问题，该模型在共享的多模态编码器中整合DNA序列嵌入与局部和全局染色质可及性，生成可复用的窗口级嵌入，同时支持预训练期间的掩码重建和下游预测任务。我们诊断了这种异质性模态对齐的失败模式，并表明全局归一化能显著缓解坍缩，从而实现跨模态的有效联合学习。所生成的嵌入提升了下游多项调控功能评估，包括调控活性预测、调控信号排序和染色质可及性峰检测，在峰检测中相对于仅DNA基线实现了4.6倍的AUPRC提升，并在ClinVar、GTEx eQTL和PBMC caQTL数据集上的外部验证中进一步改善。该框架可扩展至其他调控模态，为多模态DNA基础模型提供了方法论基础。

## Abstract
Genomic foundation models pretrained on DNA sequence have achieved strong performance across a range of tasks, but sequence-only representations cannot fully capture regulatory information reflected by additional DNA-centric modalities. Existing multimodal genomic models are often optimized for specific prediction tasks rather than for learning reusable embeddings shared across downstream analyses. However, directly fusing heterogeneous genomic modalities is challenging because sparse, peak-shaped regulatory signals and dense sequence representations have markedly different statistical structures, making naive multimodal alignment prone to degenerate near-zero solutions. We present a self-supervised DNA-centric multimodal foundation model that addresses this gap, integrating DNA sequence embeddings with local and global chromatin accessibility in a shared multimodal encoder to produce reusable window-level embeddings that support both masked reconstruction during pre-training and downstream prediction tasks. We diagnose this heterogeneous-modality alignment failure and show that global normalization substantially alleviates collapse, enabling effective joint learning across modalities. The resulting embeddings improve multiple downstream evaluations of regulatory function, including regulatory activity prediction, regulatory signal ranking and chromatin accessibility peak detection, achieving a 4.6-fold AUPRC improvement over the DNA-only baseline in peak detection, and further improving external validation on ClinVar, GTEx eQTL and PBMC caQTL datasets. The framework is extensible to additional regulatory modalities, providing a methodological basis for multimodal DNA foundation models.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：基因组基础模型通常在纯DNA序列上预训练，在多种下游任务中表现优异，但**仅基于序列的表征无法完整捕捉调控信息**（如染色质可及性等调控信号）。
- **核心问题**：现有多模态基因组模型往往针对特定预测任务进行优化，缺乏**可复用的嵌入表示**；同时，直接融合异质性基因组模态（稀疏的峰状调控信号 vs. 密集的序列表示）在统计结构上差异巨大，**朴素的多模态对齐容易退化为近零解的坍缩状态**（representation collapse）。
- **总体含义**：该论文试图构建一个**自监督的DNA多模态基础模型**，通过融合序列信息和染色质可及性信息，学习可迁移、可复用的窗口级嵌入，为多模态基因组基础模型提供方法论基础。

## 2. 论文提出的方法论：核心思想与关键技术细节

- **核心思想**：采用共享的多模态编码器（shared multimodal encoder），整合三种信息源：
  - DNA序列嵌入（dense sequence embeddings）
  - 局部染色质可及性（local chromatin accessibility）
  - 全局染色质可及性（global chromatin accessibility）
- **预训练任务**：掩码重建（masked reconstruction），学习窗口级嵌入（window-level embeddings），这些嵌入同时支持预训练阶段的重建目标和下游预测任务。
- **针对坍缩问题的关键设计**：
  - 作者诊断了异质性模态对齐的失败模式（failure mode），指出**稀疏的峰状信号与密集的序列表示统计结构不匹配**是导致坍缩的根源；
  - 提出**全局归一化（global normalization）** 方法，显著缓解了模态坍缩，实现跨模态的有效联合学习。
- **可扩展性**：框架设计为可扩展至其他调控模态，不局限于染色质可及性。
- 注意：由于无法获取论文全文，具体公式和算法流程细节未能在此展开。

## 3. 实验设计：数据集、场景与对比方法

- **下游任务**（三个评估维度）：
  1. **调控活性预测**（regulatory activity prediction）
  2. **调控信号排序**（regulatory signal ranking）
  3. **染色质可及性峰检测**（chromatin accessibility peak detection）
- **对比基线**：主要与**仅DNA序列的模型（DNA-only baseline）** 进行对比，强调多模态融合带来的增益。
- **外部验证数据集**：
  - **ClinVar**（临床变异注释数据）
  - **GTEx eQTL**（基因表达数量性状位点）
  - **PBMC caQTL**（外周血单核细胞染色质可及性QTL）
- **主要性能指标**：AUPRC（精确率-召回率曲线下面积）。
- 注意：由于全文不可获取，具体的训练集规模、数据来源（如ENCODE等）、与更多SOTA模型（如Enformer、Borzoi等）的对比细节无法确认。

## 4. 资源与算力

- **未明确说明**：提供的摘要和元数据中**未提及GPU型号、数量、训练时长、参数量或能耗等算力信息**。
- 建议：如需了解算力细节，需查阅论文全文或补充材料中的实验设置部分。

## 5. 实验数量与充分性

- **已有实验**：
  - 3个核心下游任务评估（调控活性、信号排序、峰值检测）；
  - 3个外部验证数据集（ClinVar、GTEx eQTL、PBMC caQTL）；
  - 对坍缩失败模式的诊断实验；
  - 全局归一化的消融/对比效果分析。
- **充分性与客观性评价**：
  - **充分性**：覆盖了从核心任务到外部迁移验证的完整链条，任务类型多样（分类/排序/检测），外部验证增强了泛化说服力；但缺乏与当前主流基因组多模态模型的系统横向对比，可能削弱先进性论证的强度。
  - **公平性**：与DNA-only基线对比公平（控制变量验证模态增益）；但单作者预印本，未经同行评审，需谨慎对待结论声明。

## 6. 论文的主要结论与发现

- 全局归一化能**显著缓解异质性模态融合中的坍缩问题**，实现有效的多模态联合学习；
- 多模态嵌入在**调控活性预测、调控信号排序和峰检测**等多个下游任务中整体优于DNA-only基线；
- 在**峰检测任务中实现4.6倍AUPRC提升**，是最大的性能增益；
- 在**ClinVar、GTEx eQTL和PBMC caQTL**三个外部数据集中得到验证，说明嵌入具有良好的可迁移性；
- 框架**可扩展至更多调控模态**，为多模态DNA基础模型提供了方法学层面的新思路。

## 7. 优点

- **问题定位精准**：针对性的指出了多模态基因组融合中独特且关键的**坍缩问题**，而非简单堆叠多模态数据；
- **方法设计优雅**：共享编码器+全局归一化的方案简洁，适用于异构模态统计结构差异大的场景；
- **可复用性**：目标是生成窗口级嵌入而非任务特化模型，更符合“基础模型”定位；
- **验证链条完整**：从内部任务到外部真实生物数据集（ClinVar、eQTL、caQTL），增强了结果的实用价值；
- **可扩展性好**：框架不局限于当前两种模态，可推广到其他调控数据类型。

## 8. 不足与局限

- **算力信息缺失**：未报告模型参数、GPU资源配置与训练成本，可复现性和实用性评估受限；
- **数据集细节不明**：预训练数据规模、来源、物种范围等未在摘要中说明；
- **竞争对比不足**：未在摘要层面显示与Enformer、Borzoi等强基线模型的对比，优势评估不完整；
- **图谱信息有限**：本文分析仅基于摘要和元数据，全文的图表、表格细节无法访问和深入解读；
- **预印本阶段**：未经同行评审，结论（尤其是4.6倍AUPRC提升）需进一步验证；
- **模态覆盖有限**：当前仅融合序列+染色质可及性，对于甲基化、TF结合、Hi-C等其他重要调控模态的适用性有待实证。

---

（完）
