---
title: A self-supervised DNA foundation model with collapse-resistant multimodal fusion
title_zh: 一种具有抗坍缩多模态融合的自监督DNA基础模型
authors: "Chen, Y."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.19.745697v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 自监督DNA基础模型与抗坍缩多模态融合，属于大规模基因组模型核心方向
tldr: 基因组基础模型虽在序列任务上表现优异，但仅靠序列无法全面捕获调控信息。现有多模态模型多针对特定任务，难以学习可复用嵌入，且异质模态融合易因统计结构差异导致退化。本文提出自监督DNA多模态基础模型，整合序列与染色质可及性，通过全局归一化缓解模态塌缩，实现窗口级嵌入预训练。在调控功能预测、峰值检测等任务上显著提升，外部验证亦获改进，为多模态DNA建模提供新方法。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1696, \"height\": 969}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1633, \"height\": 1476}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1671, \"height\": 1183}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1677, \"height\": 1509}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1684, \"height\": 1337}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1669, \"height\": 1231}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1728, \"height\": 272}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1740, \"height\": 308}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1743, \"height\": 362}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1742, \"height\": 360}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1733, \"height\": 235}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1746, \"height\": 235}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1740, \"height\": 235}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1716, \"height\": 510}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1715, \"height\": 600}]"
motivation: 序列仅能表达部分调控信息，需融合染色质等多模态；但异质模态融合易塌缩至退化解，缺乏有效的自监督多模态DNA模型。
method: 构建DNA-centric多模态编码器，融合序列嵌入与局部/全局染色质可及性，采用全局归一化防止对齐塌缩，并以掩码重建进行自监督预训练。
result: 峰值检测AUPRC较DNA-only提升4.6倍，在ClinVar、GTEx eQTL、PBMC caQTL外部验证中均获改进。
conclusion: 该框架可扩展至更多调控模态，为多模态DNA基础模型提供稳健的融合与预训练方法基础。
---

## 摘要
在DNA序列上预训练的基因组基础模型已在多种任务中取得强劲表现，但仅基于序列的表征无法完全捕捉由其他DNA中心模态所反映的调控信息。现有的多模态基因组模型通常针对特定预测任务进行优化，而非用于学习可跨下游分析复用的嵌入表示。然而，直接融合异质性基因组模态颇具挑战性，因为稀疏的峰状调控信号与密集的序列表征具有显著不同的统计结构，使得朴素的多模态对齐容易退化为接近零的退化解。我们提出了一种自监督的DNA中心多模态基础模型来解决这一问题，该模型在共享多模态编码器中整合DNA序列嵌入与局部及全局染色质可及性，生成可复用的窗口级嵌入，既支持预训练期间的掩码重建，也支持下游预测任务。我们诊断了这种异质性模态对齐失败的原因，并证明全局归一化能大幅缓解坍缩，从而实现跨模态的有效联合学习。所得嵌入提升了多项调控功能的下游评估，包括调控活性预测、调控信号排序和染色质可及性峰检测，在峰检测中相较于仅用DNA的基线实现了4.6倍的AUPRC提升，并在ClinVar、GTEx eQTL和PBMC caQTL数据集上的外部验证中进一步改善。该框架可扩展至其他调控模态，为多模态DNA基础模型提供了方法论基础。

## Abstract
Genomic foundation models pretrained on DNA sequence have achieved strong performance across a range of tasks, but sequence-only representations cannot fully capture regulatory information reflected by additional DNA-centric modalities. Existing multimodal genomic models are often optimized for specific prediction tasks rather than for learning reusable embeddings shared across downstream analyses. However, directly fusing heterogeneous genomic modalities is challenging because sparse, peak-shaped regulatory signals and dense sequence representations have markedly different statistical structures, making naive multimodal alignment prone to degenerate near-zero solutions. We present a self-supervised DNA-centric multimodal foundation model that addresses this gap, integrating DNA sequence embeddings with local and global chromatin accessibility in a shared multimodal encoder to produce reusable window-level embeddings that support both masked reconstruction during pre-training and downstream prediction tasks. We diagnose this heterogeneous-modality alignment failure and show that global normalization substantially alleviates collapse, enabling effective joint learning across modalities. The resulting embeddings improve multiple downstream evaluations of regulatory function, including regulatory activity prediction, regulatory signal ranking and chromatin accessibility peak detection, achieving a 4.6-fold AUPRC improvement over the DNA-only baseline in peak detection, and further improving external validation on ClinVar, GTEx eQTL and PBMC caQTL datasets. The framework is extensible to additional regulatory modalities, providing a methodological basis for multimodal DNA foundation models.

---

## 论文详细总结（自动生成）

# 论文详细总结

**论文标题**：A self-supervised DNA foundation model with collapse-resistant multimodal fusion（一种具有抗坍缩多模态融合的自监督 DNA 基础模型）

**作者**：Yuyan Chen（Houston Methodist Research Institute / Weill Cornell Medicine / ModelsLive Inc.）

**发表状态**：bioRxiv 预印本（2026 年 8 月 20 日），未经同行评审

---

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景与动机**：DNA 序列本身包含丰富的调控信息（转录因子基序、保守元件、远端基因组上下文），但仅靠序列无法全面捕获真实的调控状态。染色质可及性、组蛋白修饰、DNA 甲基化等 DNA 中心模态提供了互补的基因组功能视图。然而现有基因组模型存在明显缺口：
  - **序列语言模型**（DNABERT-2、Nucleotide Transformer、HyenaDNA、Evo 2 等）仅从序列学习表征，不包含调控状态信息；
  - **长程序列模型**（Enformer、AlphaGenome 等）虽然预测能力强，但通常面向特定预测目标而非学习可复用嵌入；
  - **染色质/表观模型**（ChromBPNet、gReLU、EpiBERT 等）侧重特定模态建模，缺乏跨模态共享表征；
  - 现有多模态基因组模型大多针对特定任务优化，缺乏自监督、可复用的多模态嵌入框架。
- **核心挑战（技术难点）**：异质模态融合存在根本性困难——DNA 衍生的嵌入是**密集、连续**的向量，而染色质可及性等调控信号是**稀疏、峰状**的（强信号集中在极少数位置）。这种分布失配导致朴素融合时出现**模态失衡**：模型倾向于学习模态特定的捷径而非有意义的跨模态交互；在自监督训练中，这种失衡表现为稀疏调控模态的**近零坍缩**（near-zero collapse），严重阻碍序列信息与调控信息的有效对齐。
- **论文定位**：填补"DNA 中心的多模态自监督嵌入框架"这一空白，提出一种能够整合异质基因组信号、学习跨模态互补信息并跨下游任务复用的窗口级嵌入模型。

---

## 2. 论文提出的方法论

### 2.1 整体框架：DNA-MFM

DNA-MFM（DNA-centric Multimodal Foundation Model）是一个端到端的自监督多模态基础模型，核心流程为：

```
基因组窗口构建 → 三模态输入（DNA嵌入 + 局部染色质可及性 + 全局染色质可及性）
→ 模态特定归一化与标记化 → 共享Transformer编码器 → 掩码重建自监督训练
→ 输出可复用的窗口级嵌入（256维）
```

### 2.2 输入表示与模态设计

- 每个基因组窗口由来自**同一基因组区域**的三个同步流表示：
  - **DNA 序列嵌入**：使用预训练的 chopped Enformer 模型提取，维度 1536，覆盖 896 个位置；
  - **局部染色质可及性（LCL）**：128bp 分辨率的 ATAC-seq 一维信号轨迹；
  - **全局染色质可及性（GBL）**：同一基因组上下文上的更宽一维可及性轨迹。
- 窗口构建：基于 hg38 参考基因组，约 114kb 窗口对齐到 Enformer 输出分辨率；训练集为 chr1-19（约 20,000 窗口），评估集为 chr20-22（约 940 窗口），**染色体级划分**防止序列泄漏。

### 2.3 关键技术创新：全局归一化（Global Normalization）抗坍缩

- **问题诊断**：LCL 稀疏且呈峰状分布，大部分位置接近零。在**逐样本归一化**下，模型只需预测接近零的值即可降低大部分掩码位置的损失，无需学习有意义的峰结构，从而陷入**稀疏模态坍缩**——这是论文诊断出的关键失败模式。
- **解决方案**：用**全局归一化**替代逐样本归一化。全局归一化使用训练窗口估计的全局统计量，**保留跨窗口的可及性信号相对量级**，消除了模型通过均匀预测近零值来最小化损失的动机，从而保持峰对比度、稳定联合多模态学习。
- **诊断实验表明其他方案无效**：调整 LCL 掩码率、强调峰相关信号、添加辅助峰分类头、重采样高可及性窗口等变体仅产生边际改善，甚至损害 DNA/GBL 重建稳定性；只有全局归一化带来了实质提升（LCL 改善比率从约 1.04-1.10 提升到 1.931）。

### 2.4 模型架构细节

- **归一化与投影**：
  - DNA：直接投影 1536→256 维，保留 896 位置序列；
  - LCL：全局归一化后，按 patch size=8 切分为非重叠补丁，投影为 256 维 token；
  - GBL：逐样本鲁棒归一化后，按 patch size=16 切分，得到 912 个 patch token。
- **共享 Transformer 编码器**：
  - 三模态 token 流与可学习的 CLS token 拼接；
  - 加入可学习的位置嵌入和**模态类型嵌入**（区分 CLS/DNA/LCL/GBL）；
  - 6 层、隐藏维度 256、8 注意力头、FFN 维度 1024、GELU 激活、dropout 0.1、pre-norm 布局；
  - 双向自注意力允许同一窗口内的三模态 token 在共享潜在空间中交互。
- **窗口级嵌入**：最终层对**未掩码 token** 取均值池化，得到 256 维窗口级嵌入。

### 2.5 自监督训练目标

- **掩码重建**：各模态独立采样掩码位置，掩码率分别为 DNA 0.75、LCL 0.30（考虑稀疏性）、GBL 0.75；掩码位置替换为可学习的占位向量；
- **损失函数**：仅在掩码位置计算**模态加权的 Huber 损失**，平衡高维 DNA 嵌入 token 与低维可及性 patch token 的重建；
- **训练策略**：AdamW 优化器、学习率 2e-4、余弦衰减+线性预热；预热期间应用**掩码课程**（masking curriculum），从初始低掩码率逐步增加到目标值；
- **重建质量评估**：均/中位余弦相似度 + 基线改善比率（相对零预测基线）。

---

## 3. 实验设计

### 3.1 内部调控功能基准（held-out chr20-22，线性探针评估）

| 任务 | 标签来源 | 评估指标 |
|------|----------|----------|
| 调控活性分类 | 六种组蛋白修饰标记信号（H3K27ac、H3K4me1、H3K4me3、H3K9me3、H3K27me3、H3K36me3）的分位数 | F1 |
| 调控活性排序 | 连续的组蛋白标记信号值 | Spearman 相关 |
| 染色质峰检测 | 从 LCL 信号提取的峰标签 | AUPRC |
| 峰位置预测 | 窗口内相对峰位置（左/中/右） | 分类准确率 |

### 3.2 外部变异效应验证

| 数据集 | 功能上下文 | 任务 | 指标 |
|--------|-----------|------|------|
| ClinVar（2024 版） | 非编码变异致病性（5'UTR/3'UTR/内含子/基因间） | 二元分类 | AUROC、AUPRC、F1、ACC |
| GTEx v8 Whole Blood eQTL | 表达相关变异效应 | 效应量回归 | Pearson、Spearman、R² |
| PBMC scATAC-seq caQTL | 染色质可及性相关变异效应 | 效应量回归 | Pearson、Spearman、R² |

### 3.3 对比方法

- **序列嵌入基准**：DNABERT-2（768 维）、Nucleotide Transformer（1024 维）、Enformer tracks（5313 维）、DNA pooling（1536 维均值池化）；
- **消融对照**：DNA pooling（无编码器）、DNA-only（仅 DNA 输入同架构自监督训练）、Random DNA-MFM（完整架构但随机初始化、无预训练）、DNA-MFM（完整模型）；
- **外部验证参照**：Enformer Δ（参考/替代等位基因序列的 Enformer 输出差异）、DNA-MFM + Enformer Δ 特征拼接。

---

## 4. 资源与算力

- **明确信息**（Supplementary Table 1）：
  - GPU：A100 40G；
  - 优化器：AdamW（β₁=0.9, β₂=0.999）；
  - 学习率 2e-4，权重衰减 0.05，批次大小 32；
  - 训练 10 个 epoch，共 33,060 次迭代，预热 9,918 次迭代；
  - 3 个随机种子（333、666、999）。
- **未明确说明**：**GPU 数量、具体训练时长**未在论文中给出。

---

## 5. 实验数量与充分性

### 5.1 实验规模

论文实验覆盖较全面，主要包括：

- **掩码重建评估**（3 个模态 × 3 个随机种子，表 1）；
- **模态与预训练消融**（4 种配置 × 4 个下游任务，表 2）；
- **设计组件消融**（6 种改动 × 4 个下游任务，表 3）；
- **序列模型对比**（5 种方法 × 4 个下游任务，表 4）；
- **外部验证**（3 个数据集，表 5-7）；
- **LCL 诊断消融**（8 种配置，Extended Data Table 1）；
- **超参数敏感性**（掩码率、隐藏维度、patch size、损失权重，Extended Data Fig. 4）。

### 5.2 充分性与公平性评估

- **优点**：
  - 染色体级划分（chr1-19 训练，chr20-22 评估）有效防止序列泄漏；
  - 消融设计系统地分离了**模态融合**、**自监督训练**和**架构**三方面贡献；
  - 外部验证覆盖临床（ClinVar）、表达（eQTL）和染色质（caQTL）三种不同功能上下文；
  - 多随机种子评估提高可靠性；
  - 与序列嵌入基准在相同的下游评估协议下对比，公平性较好。
- **不足**：
  - 内部基准的标签（六种组蛋白修饰信号）与训练模态（DNA+ATAC）不完全对应，未评估如甲基化等其他模态任务；
  - 外部验证中 Enformer Δ 与 DNA-MFM 的样本量不同（例如 caQTL 中 Enformer Δ 996 条 vs DNA-MFM 768 条），某些对比并非严格同集合比较；
  - 未与其他多模态基因组模型（如 EpiBERT、AlphaGenome）直接对比；
  - caQTL 仅涉及 PBMC 单一细胞类型，eQTL 仅涉及全血。

---

## 6. 主要结论与发现

1. **全局归一化有效缓解稀疏模态坍缩**：逐样本归一化导致 LCL 陷入近零坍缩（改善比率仅 1.04-1.10），改为全局归一化后 LCL 重建改善比率提升至 1.931、余弦相似度 0.717，同时 DNA 和 GBL 重建也保持稳定。LCL 仍是重建最困难的模态。
2. **多模态融合 + 自监督训练共同驱动性能提升**：
   - DNA-MFM 在下游任务全面优于 DNA-only 和 Random DNA-MFM，表明仅有多模态输入或仅靠架构无法带来完整增益；
   - 峰检测 AUPRC 从 DNA-only 的 0.1644 提升至 0.7095（约 4.6 倍提升）。
3. **ATAC 可及性信息对调控活性分类和峰检测增益最大**：DNA-MFM 在活性分类（F1 0.9835）和峰检测（AUPRC 0.7095）上显著优于序列模型；活性排序上 Enformer tracks 最高（Spearman 0.8606），DNA-MFM（0.8281）保持竞争力。
4. **外部泛化有效**：
   - ClinVar 非编码变异分类：DNA-MFM（AUROC 0.6829、AUPRC 0.3541）优于 Enformer tracks（0.6141/0.3265），拼接特征最佳（0.7012/0.4009）；
   - GTEx eQTL 效应量预测：DNA-MFM（Pearson 0.505、R² 0.215）优于 Enformer Δ（0.218、-1.319）；拼接未带来一致增益；
   - PBMC caQTL 效应量预测：DNA-MFM 匹配子集（Pearson 0.3539、R² 0.1126）为 Pearson 和 R² 最优；拼接仅提升 Spearman。
5. **特征拼接收益有限且指标依赖**：在 eQTL/caQTL 中，DNA-MFM 与 Enformer Δ 的简单拼接仅在部分指标上提高，提示区域级调控上下文与等位基因特异扰动信号需要更结构化的融合方式。

---

## 7. 优点

- **问题诊断深入**：明确识别出稀疏模态近零坍缩这一融合失败的根源，并用系统的诊断实验排除替代解释，科学叙事清晰。
- **归一化方案简洁有效**：通过全局统计保持跨窗口信号量级差异，以最小的方法改动解决了多模态融合中的关键不稳定性，具有较强的可推广性。
- **可复用的嵌入设计**：产出固定的 256 维窗口级嵌入，支持各类下游线性探针评估，体现了"基础模型"的定位理念。
- **染色体级数据划分**：减少了训练/评估之间的序列泄漏风险，评估协议更可信。
- **全面的消融设计**：分别拆解了编码器、多模态融合、自监督训练和具体设计组件（归一化、池化、掩码课程、VICReg）的贡献。
- **框架可扩展**：明确支持扩展到组蛋白修饰、DNA 甲基化、表达相关信号等其他调控模态。
- **外部验证多维覆盖**：临床变异、表达 QTL、染色质 caQTL 三个层面验证嵌入的泛化能力。

---

## 8. 不足与局限

- **LCL 重建仍是瓶颈**：即使采用全局归一化，LCL 余弦相似度仅 0.717，峰的幅度仍被低估、局部重建误差仍存在，稀疏模态的学习尚未完全解决。
- **外部验证的基准不完全对齐**：
  - Enformer Δ 与 DNA-MFM 在 eQTL/caQTL 评估中的样本量不同（如 caQTL：Enformer Δ 9,996 条 vs DNA-MFM 1,768 条），部分对比并非严格同集合；
  - 未见针对同一样本集合的严格配对比较，可能影响对比的公平性。
- **模态覆盖有限**：仅使用 DNA 序列 + ATAC 衍生的染色质可及性，未纳入组

- **模态覆盖有限**：仅使用 DNA 序列 + ATAC 衍生的染色质可及性，未纳入组蛋白修饰、DNA 甲基化等模态。因此模型对调控机制的覆盖仍偏窄，多模态融合的实际体现主要局限于“稀疏峰信号 + 丰富序列信息”的二元组合，距离真正意义上的“多模态基因组模型”仍有一定距离。
- **内部评估标签与训练模态不完全对齐**：下游基准使用的标签是六种组蛋白修饰信号，而训练阶段并未将其作为模态输入；这在验证嵌入可迁移性方面有优势，但也意味着模型从未直接学习过组蛋白修饰的预测目标，其活性分类性能可能受间接表征能力制约。
- **外部验证的样本量和组织覆盖面有限**：ClinVar 仅覆盖非编码变异，且正负样本不均衡；eQTL 仅使用 GTEx 全血组织；caQTL 仅使用 PBMC 一种细胞类型。模型对肝、脑、心脏等复杂组织或疾病相关细胞类型的泛化能力尚未得到验证。
- **窗口级嵌入的粒度限制**：模型输出固定 256 维的特征表示，对应约 114kb 的基因组窗口，主要用于区域级调控状态建模。对于单碱基变异、精确峰边界等细粒度任务，窗口级嵌入可能存在信息损失；论文虽然设计了峰位置预测任务，但仅将位置粗分为左/中/右三档，粒度较粗。
- **训练规模与模型容量相对克制**：训练窗口仅约 2 万个，编码器为 6 层、256 维，与动辄数十亿参数的基因组大模型（如 Evo 2、Nucleotide Transformer）相比容量较小。这种设计提升了可复现性，但也可能限制了模型对复杂远距离调控机制的表示上限。论文未报告训练所需的 GPU 数量和具体时长，不便于推算其算力门槛。
- **缺乏与同类多模态模型或更优序列模型的直接对标**：论文对比了 DNABERT-2、Nucleotide Transformer、Enformer tracks 等序列/监督模型，但未与 ChromBPNet、EpiBERT、AlphaGenome 等多模态基因组模型进行跨框架对比；也未用 Evo 2、HyenaDNA 等长上下文序列模型做外部验证基线，导致无法准确判断 DNA-MFM 在同类方法中的相对位置。
- **特征拼接策略过于简单**：在外部验证中，将 DNA-MFM 嵌入与 Enformer Δ 特征进行拼接，仅在部分数据集/指标上带来增益，说明两类特征在语义尺度上差异较大。更复杂的融合方法（如注意力特征选择、跨模态对齐后拼接）可能更为有效，但论文未进一步探索。

总体而言，DNA-MFM 的核心贡献在于问题识别和解决路径具有较强启发性——它通过全局归一化这一轻量改动，缓解了自监督多模态基因组学习中的稀疏模态坍缩问题，并生成了可复用的窗口级嵌入；其消融实验和外部验证设计也较为严谨。然而，受限于模态覆盖范围、评估数据规模、样本集合对齐程度以及缺乏同类框架对比，其作为通用基因组基础模型的全面性和绝对性能优势仍需进一步证明。未来工作若能扩展更多调控模态、增大训练数据并做更严格的基线对齐，有望使该框架的潜力得到更充分的验证。

（完）
