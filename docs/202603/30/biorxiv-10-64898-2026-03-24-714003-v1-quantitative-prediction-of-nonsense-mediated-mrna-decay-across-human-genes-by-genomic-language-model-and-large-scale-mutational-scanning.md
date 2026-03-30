---
title: Quantitative prediction of nonsense-mediated mRNA decay across human genes by genomic language model and large-scale mutational scanning
title_zh: 通过基因组语言模型和大规模突变扫描对人类基因中无义介导的 mRNA 降解进行定量预测
authors: "Veiner, M., Toledano, I., Palou-Marquez, G., Lehner, B., Supek, F."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.714003v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于mRNA降解预测的基因组语言模型
tldr: 本研究旨在解决无义介导的mRNA降解（NMD）预测仍依赖简单二元规则的问题。通过整合大规模人类基因组等位基因特异性表达数据、mRNA语言模型和高通量突变扫描，开发了NMDetective-AI模型。该模型在预测体细胞和生殖系提前终止密码子（PTC）引发的NMD方面表现优异。研究揭示了NMD遵循定量而非简单的二元逻辑，受基因架构和局部序列调节，为变异解释和NMD靶向治疗提供了重要依据。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-001.webp\", \"caption\": \"Figure 4: NMDetective-AI captures and predicts quantitative NMD evasion in penultimate and last exons.\", \"page\": 11, \"index\": 1, \"width\": 943, \"height\": 725}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-002.webp\", \"caption\": \"Figure 2: NMDetective-AI model development and validation.\", \"page\": 7, \"index\": 2, \"width\": 943, \"height\": 504}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-003.webp\", \"caption\": \"Figure 5: Systematic analysis of exon length and spatial determinants of NMD efficiency.\", \"page\": 14, \"index\": 3, \"width\": 943, \"height\": 1177}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-004.webp\", \"caption\": \"Figure 1: Overview of the NMD efficiency datasets and NMDetective-AI.\", \"page\": 4, \"index\": 4, \"width\": 943, \"height\": 317}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-005.webp\", \"caption\": \"Figure 7: Reinitiation and local sequence-context effects.\", \"page\": 19, \"index\": 5, \"width\": 941, \"height\": 839}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-006.webp\", \"caption\": \"Figure 6: Landscape and predictability of start-proximal NMD evasion.\", \"page\": 17, \"index\": 6, \"width\": 937, \"height\": 769}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-007.webp\", \"caption\": \"Figure 8: Selection of PTCs in germline and soma\", \"page\": 24, \"index\": 7, \"width\": 943, \"height\": 1219}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-008.webp\", \"caption\": \"Figure 3: Mutagenesis experiment overview and inter-replicate correlation.\", \"page\": 9, \"index\": 8, \"width\": 945, \"height\": 792}]"
motivation: 传统的NMD预测主要依赖简单的二元位置规则，无法准确反映不同基因和转录本背景下PTC引发NMD的复杂定量差异。
method: 整合大规模人类队列的等位基因特异性表达数据，结合mRNA语言模型训练NMDetective-AI，并利用深度突变扫描技术对数千个PTC进行实验验证。
result: NMDetective-AI显著提升了NMD预测精度，并揭示了NMD受外显子长度、起始密码子距离及局部序列背景等因素的定量调节。
conclusion: 研究证明了哺乳动物NMD逻辑是定量的且具有基因依赖性，为理解疾病相关截短变异的影响及开发NMD疗法奠定了基础。
---

## 摘要
蛋白质截短变异的分子后果在很大程度上取决于其转录本是否被无义介导的 mRNA 降解 (NMD) 清除，然而，目前对 NMD 的预测仍主要依赖于一小组二元位置规则。因此，单个提前终止密码子 (PTC) 如何在不同基因和转录本背景下触发 NMD 仍未得到完全解决。在本研究中，我们整合了来自大规模基因组数据的内源性等位基因特异性 PTC 表达、mRNA 语言模型预测和高通量突变扫描，以重新审视调控哺乳动物 NMD 的规则。利用来自大型人类队列的等位基因特异性表达测量数据，我们在约 14,000 个体细胞 PTC 上训练了 NMDetective-AI；在约 1,800 个生殖系 PTC 上进行测试后，我们发现该模型优于以往模型，其准确性接近基础测量数据的可重复性。随后，我们通过深度突变扫描生成了 NMD 的实验图谱，包括倒数第二外显子边界 50-nt 附近的约 450 个 PTC、跨越 9 种外显子长度的约 950 个工程化 PTC（用于解析长外显子逃逸），以及跨越 139 个基因的约 1.1 万个 PTC（用于定量和细化起始端近端逃逸）。我们的结果支持哺乳动物 NMD 的位置逻辑，但表明这种逻辑是以定量方式实现的：经典规则转化为分级的、基因依赖性的响应曲线，其边界由转录本结构塑造并受局部序列背景调节。将该框架应用于群体、疾病和癌症数据集，进一步识别出 NMD 被预测会加剧或减轻截短变异影响的基因，为变异解读和优先考虑 NMD 靶向疗法提供了基础。

## Abstract
The molecular consequences of protein truncating variants depend strongly on whether their transcripts are eliminated by nonsense-mediated mRNA decay (NMD), yet NMD is still predicted largely from a small set of binary positional rules. How individual premature termination codons (PTCs) engage NMD across genes and transcript contexts therefore remains incompletely resolved. Here we integrated endogenous allele-specific PTC expression from large-scale genomic data, mRNA language-model prediction and high-throughput mutational scanning to revisit the rules that govern mammalian NMD. Using allele-specific expression measurements from large human cohorts, we trained NMDetective-AI on [~]14,000 somatic PTCs, and after testing it on [~]1,800 germline PTCs, found that it improves on previous models, with its accuracy approaching the reproducibility of the underlying measurements. We then generated experimental maps of NMD with deep mutational scanning, including [~]450 PTCs nearby the 50-nt penultimate exon boundary, [~]950 engineered PTCs across 9 exon lengths to resolve long-exon escape, and [~]11k PTCs across 139 genes to quantify and refine start-proximal evasion. Our results support the positional logic of mammalian NMD yet show that this logic is implemented quantitatively: the classical rules resolve into graded, gene-dependent response curves whose boundaries are shaped by transcript architecture and modulated by local sequence context. Applying this framework to population, disease and cancer datasets further identifies genes in which NMD is predicted to aggravate or ameliorate the effects of truncating variants, providing a basis for variant interpretation and for prioritizing NMD-directed therapies.

---

## 论文详细总结（自动生成）

### 论文总结：通过基因组语言模型和大规模突变扫描定量预测人类 NMD 效率

#### 1. 核心问题与整体含义（研究动机和背景）
无义介导的 mRNA 降解（NMD）是细胞内关键的质量控制机制，负责识别并降解含有提前终止密码子（PTC）的转录本。长期以来，预测 NMD 主要依赖简单的“二元位置规则”（如 50-nt 规则），即 PTC 距离最后一个外显子交界处超过 50-55 个核苷酸则触发降解，否则逃逸。
然而，这种二元逻辑无法解释约 1/3 的 NMD 效率差异。研究动机在于：NMD 实际上是一个**定量的、受基因背景和局部序列调节**的复杂过程。准确预测 NMD 效率对于解读致病变异（如癌症驱动突变或遗传病变异）以及开发针对性的 NMD 抑制疗法至关重要。

#### 2. 方法论：核心思想与关键技术
论文提出了 **NMDetective-AI**，一个基于深度学习的定量预测框架：
*   **核心思想**：利用预训练的 RNA 基础模型，通过端到端的微调，从成熟 mRNA 序列和剪接注释中直接学习 NMD 的复杂语法。
*   **关键技术细节**：
    *   **基础模型**：采用 **Orthrus**（一种基于 Mamba 架构、拥有 10M 参数的成熟 mRNA 基础模型），该模型在 4500 万个哺乳动物转录本上进行了预训练。
    *   **输入编码**：使用 6 轨道独热编码（4 种核苷酸 + 1 个 CDS 读码框轨道 + 1 个剪接位点轨道）。
    *   **标签生成**：利用等位基因特异性表达（ASE）数据作为 NMD 效率的真实值（Ground Truth），并进行了严格的偏倚校正和归一化处理（将完全触发定义为 +0.5，完全逃逸定义为 -0.5）。
    *   **实验验证（DMS）**：采用深度突变扫描技术，通过微基因（Minigene）报告系统在 HeLa 细胞中测量数千个工程化 PTC 的 mRNA 水平，用于细化 NMD 规则。

#### 3. 实验设计：数据集、场景与 Benchmark
*   **数据集**：
    *   **训练集**：来自 TCGA 的 ~14,000 个体细胞 PTC 变异。
    *   **测试集**：来自 TCGA 的 ~1,800 个生殖系 PTC 和来自 GTEx 的 ~11,000 个生殖系 PTC。
    *   **实验集**：针对 139 个基因设计的 >11,000 个 PTC 突变库。
*   **Benchmark（对比方法）**：
    *   **NMDetective-A**：基于手工特征的随机森林模型。
    *   **NMDetective-B**：基于规则的决策树模型。
    *   **消融实验**：对比了全微调、线性探测（冻结编码器）和随机初始化模型。
*   **实验场景**：涵盖了倒数第二外显子 50-nt 边界、长外显子逃逸（Long-exon rule）以及起始端近端逃逸（Start-proximal rule）三大场景。

#### 4. 资源与算力
*   论文提到使用了 **Weights & Biases (W&B)** 进行贝叶斯超参数搜索（共 42 次迭代）。
*   虽然未明确给出具体的 GPU 型号和总训练时长，但考虑到 Orthrus 模型规模（10M 参数）和训练样本量（~1.5万），该模型在单张现代 GPU（如 A100 或 V100）上即可在数小时内完成微调。

#### 5. 实验数量与充分性
*   **实验规模**：模型在超过 2.2 万个内源性 PTC 观测值上进行了验证，并配合了超过 1.1 万个合成 PTC 的高通量实验数据。
*   **充分性**：实验设计非常全面，不仅有跨组织、跨病种的基因组数据验证，还通过 DMS 实验深入探讨了翻译重新起始（Reinitiation）和局部序列背景（如 UGACUA 序列）对 NMD 的影响。
*   **客观性**：通过留出染色体（1 号和 20 号）进行验证，并使用独立的生殖系数据集进行测试，确保了评估的公正性。

#### 6. 主要结论与发现
*   **规则定量化**：经典的 NMD 规则并非“全或无”的开关，而是表现为**分级的、基因依赖性的逻辑回归曲线**（如 4 参数逻辑曲线）。
*   **长外显子效应**：证实了长外显子（>400 nt）会导致 NMD 效率随 PTC 位置向 3' 端移动而逐渐降低，且在极长外显子中表现出全局性的弱 NMD。
*   **起始端逃逸机制**：起始端近端逃逸受下游 AUG 介导的翻译重新起始驱动，其强度受 uORF 长度、间距和 Kozak 序列强度的调节。
*   **临床意义**：NMD 在不同基因中扮演双重角色。在某些基因（如抑癌基因）中，NMD 触发会导致功能完全丧失（加重疾病）；而在另一些基因中，NMD 逃逸产生的截短蛋白可能具有显性负效应（NMD 反而有保护作用）。

#### 7. 优点
*   **高精度预测**：NMDetective-AI 的准确性接近了生物学测量数据的重复性上限（Spearman ρ ≈ 0.67）。
*   **端到端学习**：无需人工定义复杂的生化特征，模型能自动捕捉序列中的隐性语法。
*   **干湿结合**：将大规模生物信息学分析与高通量实验验证完美结合，不仅提升了预测力，还深化了机制理解。

#### 8. 不足与局限
*   **微基因系统的局限性**：DMS 实验基于微基因报告系统，可能无法完全模拟内源性染色质环境或复杂的替代剪接模式。
*   **数据噪声**：ASE 数据受测序深度和组织特异性表达的影响，存在一定的技术噪声。
*   **黑盒特性**：尽管通过原位突变扫描（ISM）进行了解释，但深度学习模型内部的具体决策逻辑仍不如简单规则直观。
*   **覆盖范围**：虽然涵盖了 139 个基因，但对于人类全基因组（~2万个基因）的异质性覆盖仍有提升空间。

（完）
