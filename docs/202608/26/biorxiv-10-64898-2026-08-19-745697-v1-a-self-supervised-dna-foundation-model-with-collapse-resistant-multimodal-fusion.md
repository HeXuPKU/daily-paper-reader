---
title: A self-supervised DNA foundation model with collapse-resistant multimodal fusion
title_zh: 一种具有抗坍塌多模态融合的自监督DNA基础模型
authors: "Chen, Y."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.19.745697v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于大规模基因组建模的自监督DNA基础模型与多模态融合
tldr: DNA序列表示难以捕获染色质调控信息，现有多模态基因组模型多面向特定任务，且异构模态融合易产生退化对齐。本文提出自监督DNA多模态基础模型，将序列嵌入与局部及全局染色质可及性在共享编码器中融合，采用全局归一化有效避免对齐塌缩。生成的窗口级嵌入在调控活性预测、信号排序和峰值检测中均优于DNA-only基线，峰值检测AUPRC提升4.6倍，在ClinVar、GTEx eQTL及PBMC caQTL外部验证中表现优异。框架可扩展至额外调控模态，为多模态DNA基础模型提供方法论基础。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1696, \"height\": 969}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1633, \"height\": 1476}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1671, \"height\": 1183}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1677, \"height\": 1509}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1684, \"height\": 1337}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1669, \"height\": 1231}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1728, \"height\": 272}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1740, \"height\": 308}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1743, \"height\": 362}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1742, \"height\": 360}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1733, \"height\": 235}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1746, \"height\": 235}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1740, \"height\": 235}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1716, \"height\": 510}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1715, \"height\": 600}]"
motivation: 序列-only表示无法充分捕捉调控信息，且异构多模态融合面临塌缩风险。
method: 提出自监督DNA多模态模型，融合序列与局部/全局染色质可及性，用全局归一化抑制对齐塌缩。
result: 在调控活性、信号排序和峰值检测上超越DNA-only，AUPRC提升4.6倍，外部数据集验证有效。
conclusion: 可扩展多模态融合框架，为DNA基础模型提供新方法，支持多种下游任务。
---

## 摘要
基于DNA序列预训练的基因组基础模型在一系列任务中取得了强劲性能，但仅序列表示无法完全捕捉由其他DNA中心模态所反映的调控信息。现有的多模态基因组模型通常针对特定预测任务进行优化，而非用于学习可跨下游分析复用的嵌入表示。然而，直接融合异质性基因组模态具有挑战性，因为稀疏的峰状调控信号与密集的序列表示具有显著不同的统计结构，使得朴素的多模态对齐容易退化为接近零的退化解。我们提出了一种自监督的DNA中心多模态基础模型来解决这一差距，将DNA序列嵌入与局部和全局染色质可及性整合到共享的多模态编码器中，以产生可复用的窗口级嵌入，同时支持预训练期间的掩码重建和下游预测任务。我们诊断了这种异质性模态对齐失败的原因，并表明全局归一化显著缓解了坍塌问题，实现了跨模态的有效联合学习。生成的嵌入改善了下游多个调控功能评估，包括调控活性预测、调控信号排序和染色质可及性峰检测，在峰检测中相较于仅DNA基线实现了4.6倍的AUPRC提升，并在ClinVar、GTEx eQTL和PBMC caQTL数据集上的外部验证中进一步改进。该框架可扩展到其他调控模态，为多模态DNA基础模型提供了方法论基础。

## Abstract
Genomic foundation models pretrained on DNA sequence have achieved strong performance across a range of tasks, but sequence-only representations cannot fully capture regulatory information reflected by additional DNA-centric modalities. Existing multimodal genomic models are often optimized for specific prediction tasks rather than for learning reusable embeddings shared across downstream analyses. However, directly fusing heterogeneous genomic modalities is challenging because sparse, peak-shaped regulatory signals and dense sequence representations have markedly different statistical structures, making naive multimodal alignment prone to degenerate near-zero solutions. We present a self-supervised DNA-centric multimodal foundation model that addresses this gap, integrating DNA sequence embeddings with local and global chromatin accessibility in a shared multimodal encoder to produce reusable window-level embeddings that support both masked reconstruction during pre-training and downstream prediction tasks. We diagnose this heterogeneous-modality alignment failure and show that global normalization substantially alleviates collapse, enabling effective joint learning across modalities. The resulting embeddings improve multiple downstream evaluations of regulatory function, including regulatory activity prediction, regulatory signal ranking and chromatin accessibility peak detection, achieving a 4.6-fold AUPRC improvement over the DNA-only baseline in peak detection, and further improving external validation on ClinVar, GTEx eQTL and PBMC caQTL datasets. The framework is extensible to additional regulatory modalities, providing a methodological basis for multimodal DNA foundation models.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：基于DNA序列预训练的基因组基础模型已在多种下游任务中展现强大性能，但纯序列表示无法充分捕捉由其他DNA中心模态（如染色质可及性）所反映的调控信息。
- **现有方法的不足**：
  - 现有多模态基因组模型往往针对特定预测任务进行优化，而非学习可跨下游分析复用的通用嵌入表示；
  - 异质性基因组模态的直接融合具有天然困难：稀疏峰状调控信号与密集序列表示在统计结构上差异显著，朴素的跨模态对齐极易退化为接近零的退化解（即"对齐塌缩"）。
- **核心问题**：如何构建一个自监督的、可扩展的DNA中心多模态基础模型，既能有效融合序列与调控信号，又能避免模态对齐塌缩，从而生成可复用的窗口级嵌入。
- **整体含义**：该工作为多模态DNA基础模型提供了方法论基础，有望提升调控功能预测、变异解读等下游分析的表现，弥补序列-only表示的信息缺失。

## 2. 论文提出的方法论

- **核心思想**：将DNA序列嵌入与局部/全局染色质可及性信号整合到共享多模态编码器中，在预训练阶段支持掩码重建，同时产出可复用的窗口级嵌入以支持下游预测。
- **关键技术创新**：
  - **多模态融合架构**：设计共享编码器，同时接收DNA序列嵌入和染色质可及性（包括局部与全局两个尺度）特征，在统一表示空间中进行联合学习。
  - **全局归一化（Global Normalization）策略**：诊断了异质性模态对齐失败的原因，指出朴素对齐因模态统计差异而趋于退化解；通过在融合过程中引入全局归一化，显著缓解了对齐塌缩，使跨模态联合学习真正生效。
  - **自监督预训练范式**：采用掩码重建作为预训练目标，使模型不依赖任务特定标签即可学习多模态表示。
- **算法流程（文字说明）**：
  1. 输入窗口级DNA序列，通过序列编码器获得密集嵌入；
  2. 同时输入对应区域的局部与全局染色质可及性信号，经处理后得到调控信号表示；
  3. 将序列嵌入与调控信号表示在共享多模态编码器中进行融合（融合时使用全局归一化抑制塌缩）；
  4. 预训练阶段通过掩码重建优化模型参数；
  5. 下游应用中，直接使用学习到的窗口级嵌入适配具体预测任务。

## 3. 实验设计

- **数据集 / 场景**：
  - **主要评估任务**：调控活性预测、调控信号排序、染色质可及性峰检测；
  - **外部验证数据集**：ClinVar（致病变异相关）、GTEx eQTL（表达数量性状位点）、PBMC caQTL（染色质可及性数量性状位点）。
- **Benchmark 对比**：主要对比的是**仅DNA序列（DNA-only）基线模型**，评估多模态融合带来的增益。
- **评估指标**：关键指标包括AUPRC（精确率-召回率曲线下面积）等，用于衡量峰值检测等任务的性能。
- **主要结果**：
  - 峰检测任务中，多模态模型较DNA-only基线实现**4.6倍AUPRC提升**；
  - 在调控活性预测和调控信号排序上也一致优于DNA-only基线；
  - 在ClinVar、GTEx eQTL和PBMC caQTL外部数据集上进一步验证了嵌入的泛化优势。

## 4. 资源与算力

- 论文提供的摘要文本**未明确说明**具体算力配置，包括GPU型号、GPU数量、预训练与微调时长等。
- 若需评估训练成本与可复现性，建议查阅论文正文中关于实验设置的详细信息。

## 5. 实验数量与充分性

- **实验规模**：覆盖了三个主要下游任务（调控活性预测、调控信号排序、峰检测）和三个外部验证数据集（ClinVar、GTEx eQTL、PBMC caQTL），并包含DNA-only基线对比，实验场景较丰富。
- **主观评价**：
  - **优点**：多任务评估 + 外部数据集泛化验证的设计提升了结论的可信度；峰检测上的AUPRC大幅提升是该方法的亮点证据。
  - **不足**：摘要中未提及详尽的消融实验（除全局归一化的诊断外），也未报告统计显著性检验、多细胞类型/多组织覆盖、不同模态组合的扩展实验；因此实验的全面性和公平性需以正文为准。

## 6. 论文的主要结论与发现

- 自监督DNA多模态融合的基础模型是可行且有效的，能够学习到可复用的窗口级嵌入。
- **全局归一化**是缓解异质性模态对齐塌缩的关键技术，直接影响跨模态联合学习的成效。
- 多模态融合带来的嵌入在**调控活性预测、调控信号排序和染色质可及性峰检测**中均一致优于DNA-only基线，峰检测AUPRC提升达**4.6倍**。
- 外部验证（ClinVar、GTEx eQTL、PBMC caQTL）进一步表明所学表示具有良好的泛化能力。
- 框架具有**可扩展性**，可推广到其他调控模态，为多模态DNA基础模型奠定方法论基础。

## 7. 优点

- **问题选材有针对性**：精准识别了序列-only表示的局限和多模态融合的塌缩风险，填补了通用多模态DNA基础模型的空白。
- **方法设计有创新**：将自监督预训练与多模态融合结合，并针对异构模态特有难题提出全局归一化解决方案，有明确的技术贡献。
- **实验结果有说服力**：多个下游任务和外部数据集上的一致提升，尤其是峰检测4.6倍AUPRC增益，提供了较强的实证支撑。
- **框架可扩展**：不局限于染色质可及性，可推广至更多调控模态，具有较大的应用潜力。

## 8. 不足与局限

- **信息透明度不足**：摘要未提供算力配置、训练细节、超参数选择和消融实验的完整信息，难以全面评估方法的可复现性与计算成本。
- **实验覆盖有限**：外部验证虽涉及ClinVar、eQTL、caQTL等数据集，但未说明覆盖的细胞类型/组织种类和疾病范围；对不同物种的泛化性能也未提及。
- **潜在偏差风险**：仅与DNA-only基线对比而不报告与其他多模态方法的对比，或使性能优势的解读不够全面；全局归一化的适用边界（如不同模态组合、不同归一化选择）也需进一步探讨。
- **应用限制**：预印本阶段，结论尚未经同行评审；窗口级嵌入的生物学可解释性和对单碱基分辨率任务（如精细变异效应预测）的适用性有待更深入验证。

（完）
