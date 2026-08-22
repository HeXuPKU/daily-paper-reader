---
title: A self-supervised DNA foundation model with collapse-resistant multimodal fusion
title_zh: 一种具有抗塌缩多模态融合的自监督DNA基础模型
authors: "Chen, Y."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.19.745697v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 自监督DNA基础模型与多模态融合，是大规模基因组模型的核心
tldr: 现有DNA基础模型仅用序列预训练，难以捕捉调控等DNA模态信息。本文提出自监督多模态DNA基础模型，将序列嵌入与局部/全局染色质可及性联合建模，并发现全局归一化能有效防止异质模态对齐坍缩。模型生成的窗口级嵌入在下游调控任务中表现优异，峰检测AUPRC较仅序列基线提升4.6倍，外部数据集验证亦改善。该框架可扩展至更多调控模态，为多模态DNA基础模型奠定方法论。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1696, \"height\": 969, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1633, \"height\": 1476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1671, \"height\": 1183, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1677, \"height\": 1509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1684, \"height\": 1337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1669, \"height\": 1231, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1728, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1740, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1743, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1742, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1733, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1746, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1740, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1716, \"height\": 510, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1715, \"height\": 600, \"label\": \"Table\"}]"
motivation: 仅DNA序列难以捕捉完整调控信息，而现有多模态基因组模型多为任务定制，异质融合易坍缩为零解。
method: 提出自监督DNA多模态编码器，融合序列与局部/全局染色质可及性，用全局归一化缓解对齐坍缩。
result: 峰检测AUPRC较仅DNA基线提升4.6倍，调控活性预测和信号排名改善，ClinVar等外部验证也提升。
conclusion: 框架可扩展至更多调控模态，为多模态DNA基础模型提供通用方法基础。
---

## 摘要
基于DNA序列预训练的基因组基础模型在多项任务中表现出色，但仅凭序列表示无法完全捕捉由其他DNA中心模态反映的调控信息。现有的多模态基因组模型通常针对特定预测任务进行优化，而非用于学习可跨下游分析复用的嵌入表示。然而，直接融合异质性基因组模态颇具挑战性，因为稀疏的峰状调控信号与稠密的序列表示具有显著不同的统计结构，使得朴素的多模态对齐容易退化为接近零的退化解。我们提出了一种自监督的DNA中心多模态基础模型来解决这一问题，该模型在共享多模态编码器中整合DNA序列嵌入与局部及全局染色质可及性，生成可复用的窗口级嵌入，既支持预训练期间的掩码重建，也支持下游预测任务。我们诊断了这种异质性模态对齐失败的原因，并表明全局归一化能显著缓解塌缩，从而实现跨模态的有效联合学习。生成的嵌入提升了对调控功能的多个下游评估，包括调控活性预测、调控信号排序和染色质可及性峰检测，在峰检测中相比仅基于DNA的基线实现了4.6倍的AUPRC提升，并在ClinVar、GTEx eQTL和PBMC caQTL数据集上的外部验证中进一步改善。该框架可扩展至其他调控模态，为多模态DNA基础模型提供了方法论基础。

## Abstract
Genomic foundation models pretrained on DNA sequence have achieved strong performance across a range of tasks, but sequence-only representations cannot fully capture regulatory information reflected by additional DNA-centric modalities. Existing multimodal genomic models are often optimized for specific prediction tasks rather than for learning reusable embeddings shared across downstream analyses. However, directly fusing heterogeneous genomic modalities is challenging because sparse, peak-shaped regulatory signals and dense sequence representations have markedly different statistical structures, making naive multimodal alignment prone to degenerate near-zero solutions. We present a self-supervised DNA-centric multimodal foundation model that addresses this gap, integrating DNA sequence embeddings with local and global chromatin accessibility in a shared multimodal encoder to produce reusable window-level embeddings that support both masked reconstruction during pre-training and downstream prediction tasks. We diagnose this heterogeneous-modality alignment failure and show that global normalization substantially alleviates collapse, enabling effective joint learning across modalities. The resulting embeddings improve multiple downstream evaluations of regulatory function, including regulatory activity prediction, regulatory signal ranking and chromatin accessibility peak detection, achieving a 4.6-fold AUPRC improvement over the DNA-only baseline in peak detection, and further improving external validation on ClinVar, GTEx eQTL and PBMC caQTL datasets. The framework is extensible to additional regulatory modalities, providing a methodological basis for multimodal DNA foundation models.

---

## 论文详细总结（自动生成）

```markdown
# 论文详细中文总结

**论文标题**：A self-supervised DNA foundation model with collapse-resistant multimodal fusion（一种具有抗塌缩多模态融合的自监督DNA基础模型）
**作者**：Chen, Y.
**来源**：bioRxiv（预印本），2026-08-20

---

## 1. 核心问题与整体含义（研究动机与背景）

- **背景**：基于DNA序列预训练的基因组基础模型已在多种任务上表现优异，但**仅依靠序列信息不足以完整捕捉调控信息**——基因调控还体现在染色质可及性等DNA中心（DNA-centric）模态中。
- **现存问题**：
  - 现有**多模态基因组模型多为任务定制**，针对特定预测任务优化，而非学习可跨下游分析复用的通用嵌入表示，限制了其作为基础模型的泛化能力。
  - 直接融合异质性基因组模态极具挑战：**稀疏的峰状调控信号**（如ATAC-seq）与**稠密的序列表示**统计结构差异显著，朴素的模态对齐容易**退化为接近零的解**（degenerate near-zero solutions），即模态塌缩。
- **核心价值**：提出一个**自监督的DNA中心多模态基础模型**，通过抗塌缩的多模态融合策略，学习可复用的窗口级嵌入，为多模态DNA基础模型提供方法论基础。

---

## 2. 方法论：核心思想、技术细节与算法流程

### 核心思想
- 将**DNA序列嵌入**与**局部及全局染色质可及性**信号整合进一个**共享多模态编码器**，生成**窗口级嵌入**。该嵌入既服务于预训练阶段的**掩码重建**任务，也用于下游预测任务，实现单一模型多任务复用。
- 关键创新在于**诊断异质模态对齐失败的原因**，并提出**全局归一化（global normalization）** 策略，显著缓解模态塌缩，实现跨模态有效联合学习。

### 技术细节（基于摘要信息）
- **模态组成**：
  - DNA序列模态：通过序列嵌入捕捉碱基层面的编码信息。
  - 染色质可及性模态：包含**局部**与**全局**两个粒度的染色质可及性信号，反映调控元件的开放性和活性。
- **融合策略**：序列嵌入与染色质可及性信号在共享编码器中对齐融合。朴素融合易产生近零退化解，作者通过**全局归一化**对异质模态特征进行尺度校正，避免稀疏峰状信号被稠密序列表示“淹没”或主导。
- **训练目标**：自监督预训练采用**掩码重建**（masked reconstruction）——掩码部分输入并重建缺失模态或序列片段，迫使模型学习跨模态联合表示。
- **输出形式**：可复用的**窗口级嵌入**（window-level embeddings），直接支撑下游各类任务。

> 注：由于本文以预印本摘要形式提供，文中未展示具体公式与网络结构细节，以上为根据摘要信息的合理转述。

---

## 3. 实验设计：数据集、基准与对比方法

### 下游评估任务与数据集
1. **调控活性预测（regulatory activity prediction）**
2. **调控信号排名（regulatory signal ranking）**
3. **染色质可及性峰检测（chromatin accessibility peak detection）**
   - 相比仅用DNA序列的基线，**AUPRC 提升 4.6 倍**。
4. **外部验证数据集（external validation）**：
   - **ClinVar**（临床变异注释）
   - **GTEx eQTL**（表达数量性状位点）
   - **PBMC caQTL**（染色质可及性数量性状位点）

### 对比方法
- 主要对比基线为**仅基于DNA序列的模型（DNA-only baseline）**，以此来验证多模态融合带来的增益。

---

## 4. 资源与算力

- **文中未明确说明**所用的GPU型号、数量、训练时长或总体算力消耗。
- 由于论文以预印本摘要形式提供，完整的实验设置、超参和硬件配置信息目前不可得。

---

## 5. 实验数量与充分性

### 实验数量
- 涉及 **3 项主要下游任务**（调控活性预测、调控信号排名、峰检测）。
- 包含 **3 个外部验证数据集**（ClinVar、GTEx eQTL、PBMC caQTL）。
- 从摘要看，还有对模态融合失败机制的**诊断实验**（验证全局归一化对防止塌缩的作用）。

### 充分性与客观性评价
- **优点**：任务覆盖了从序列层面（峰检测）到功能层面（调控活性、信号排名），再到临床变异（ClinVar）和人群遗传学（eQTL/caQTL）的多层次验证，评估维度较全面，且外部数据验证增强了结论的可信度。
- **不足之处**：
  - 摘要中未展示**消融实验**的具体数量（如：是否对全局归一化做了逐步消融、是否对比不同归一化策略）。
  - 仅对比了DNA-only基线，**未提及与其他多模态基因组模型**或传统峰检测工具（如MACS2）的对比，当前证据强度有限。
  - 由于是预印本阶段，缺少详细的统计显著性检验说明。

---

## 6. 主要结论与发现

- **全局归一化有效缓解异质模态塌缩**：这是本文的方法论核心——通过归一化处理使稀疏调控信号与稠密序列特征可对齐联合学习。
- **多模态嵌入提升调控功能预测**：生成的窗口级嵌入在多种下游任务上优于仅序列基线。
- **峰检测增益显著**：染色质可及性峰检测的AUPRC较DNA-only基线提升4.6倍。
- **外部验证一致改善**：在ClinVar、GTEx eQTL和PBMC caQTL上均有改进，表明表示的可泛化性。
- **框架可扩展**：该方法不限于染色质可及性，可扩展至其他调控模态，为多模态DNA基础模型提供了通用方法论基础。

---

## 7. 优点（方法与实验亮点）

1. **问题定位精准**：明确指出现有多模态基因组模型的局限——任务定制而非学习可复用嵌入，将"基础模型"思维引入基因组多模态领域。
2. **诊断驱动设计**：不回避模态融合失败问题，而是系统诊断塌缩原因，并提出针对性的全局归一化策略，方法论思路清晰。
3. **自监督范式**：通过掩码重建进行预训练，无需大量标注数据即可学习多模态联合表示，符合基因组数据标注稀缺的现实。
4. **统一嵌入支持多任务**：单一窗口级嵌入既可服务预训练又可服务下游任务，具备基础模型的复用性。
5. **多层验证体系**：从任务性能到外部临床/功能基因组数据集验证，评估体系较完善，尤其是4.6倍AUPRC提升这一量化结果具有较强说服力。
6. **可扩展性**：框架设计上预留了其他调控模态的接入空间，具有生态延展潜力。

---

## 8. 不足与局限

1. **信息完整度受限**：当前为预印本摘要形式，缺乏网络结构、超参设置、训练细节的具体描述，无法完全评估实现的可复现性。
2. **实验对比不够广泛**：
   - 只对比DNA-only基线，**缺少与其他多模态方法或传统峰值检测工具的对比**，"多模态优于单模态"的结论虽然成立，但未验证"该方法优于其他多模态方案"。
   - 未报告跨细胞类型、跨组织泛化能力（如是否在多种细胞类型的ATAC数据上验证）。
3. **仅覆盖一种调控模态**：虽然框架声称可扩展，但实证部分仅涉及染色质可及性，未包含组蛋白修饰、甲基化、3D基因组等多模态组合的验证。
4. **塌缩缓解机制的解释深度未知**：摘要提到全局归一化有效，但未提供该策略为何有效、在何种条件下失效的理论分析或边界条件。
5. **算力与效率未报告**：缺少推理/训练成本信息，难以评估其实际应用门槛。
6. **外部验证范围有限**：ClinVar、eQTL、caQTL的改善幅度未给出具体数值，且未验证这些提升是否在统计上显著、在不同基因组区域（如增强子、启动子）是否一致。

---

**（完）**
```
