---
title: Quantitative prediction of nonsense-mediated mRNA decay across human genes by genomic language model and large-scale mutational scanning
title_zh: 通过基因组语言模型和大规模突变扫描对人类基因的无义介导的 mRNA 降解进行定量预测
authors: "Veiner, M., Toledano, I., Palou-Marquez, G., Lehner, B., Supek, F."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.714003v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于 mRNA 降解预测的基因组语言模型
tldr: 本研究针对无义介导的mRNA降解（NMD）预测长期依赖简单二元规则的局限，整合了大规模基因组等位基因特异性表达数据、mRNA语言模型及高通量突变扫描技术。开发出的NMDetective-AI模型在预测体细胞和生殖系提前终止密码子（PTC）引发的NMD方面达到了极高精度。研究揭示了NMD遵循受转录本结构和序列背景调节的定量响应逻辑，为临床变异解读和NMD靶向治疗提供了关键的定量框架。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-001.webp\", \"caption\": \"Figure 4: NMDetective-AI captures and predicts quantitative NMD evasion in penultimate and last exons.\", \"page\": 11, \"index\": 1, \"width\": 943, \"height\": 725}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-002.webp\", \"caption\": \"Figure 2: NMDetective-AI model development and validation.\", \"page\": 7, \"index\": 2, \"width\": 943, \"height\": 504}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-003.webp\", \"caption\": \"Figure 5: Systematic analysis of exon length and spatial determinants of NMD efficiency.\", \"page\": 14, \"index\": 3, \"width\": 943, \"height\": 1177}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-004.webp\", \"caption\": \"Figure 1: Overview of the NMD efficiency datasets and NMDetective-AI.\", \"page\": 4, \"index\": 4, \"width\": 943, \"height\": 317}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-005.webp\", \"caption\": \"Figure 7: Reinitiation and local sequence-context effects.\", \"page\": 19, \"index\": 5, \"width\": 941, \"height\": 839}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-006.webp\", \"caption\": \"Figure 6: Landscape and predictability of start-proximal NMD evasion.\", \"page\": 17, \"index\": 6, \"width\": 937, \"height\": 769}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-007.webp\", \"caption\": \"Figure 8: Selection of PTCs in germline and soma\", \"page\": 24, \"index\": 7, \"width\": 943, \"height\": 1219}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-008.webp\", \"caption\": \"Figure 3: Mutagenesis experiment overview and inter-replicate correlation.\", \"page\": 9, \"index\": 8, \"width\": 945, \"height\": 792}]"
motivation: 传统的NMD预测主要依赖于简单的二元位置规则，难以准确捕捉不同基因和转录本背景下PTC引发降解的复杂定量差异。
method: 结合大规模人类队列的等位基因特异性表达数据与mRNA语言模型训练NMDetective-AI，并利用深度突变扫描对上万个PTC进行实验制图。
result: NMDetective-AI显著提高了预测准确性，并证实NMD逻辑是定量的、基因依赖的，受外显子长度、起始位置及局部序列背景的共同调节。
conclusion: 该研究重新定义了哺乳动物NMD的调控规则，为评估蛋白质截短变异在疾病和癌症中的影响提供了更精准的计算与实验基础。
---

## 摘要
蛋白质截短变异的分子后果在很大程度上取决于其转录本是否被无义介导的 mRNA 降解（NMD）清除，然而，目前对 NMD 的预测仍主要依赖于一小组二元位置规则。因此，单个提前终止密码子（PTC）如何在不同基因和转录本背景下触发 NMD 仍未得到完全解决。在本研究中，我们整合了来自大规模基因组数据的内源性等位基因特异性 PTC 表达、mRNA 语言模型预测以及高通量突变扫描，以重新审视调控哺乳动物 NMD 的规则。利用来自大型人类队列的等位基因特异性表达测量数据，我们在约 14,000 个体细胞 PTC 上训练了 NMDetective-AI；在约 1,800 个生殖系 PTC 上进行测试后，我们发现该模型优于以往模型，其准确性接近基础测量数据的可重复性。随后，我们利用深度突变扫描生成了 NMD 的实验图谱，包括倒数第二外显子边界 50nt 附近的约 450 个 PTC、跨越 9 种外显子长度的约 950 个工程化 PTC（旨在解析长外显子逃逸），以及分布在 139 个基因中的约 1.1 万个 PTC（旨在量化并细化起始端近端逃逸）。我们的结果支持哺乳动物 NMD 的位置逻辑，但表明这种逻辑是以定量方式实现的：经典规则转化为分级的、基因依赖性的响应曲线，其边界由转录本结构塑造并受局部序列背景调节。将该框架应用于群体、疾病和癌症数据集，进一步识别出 NMD 被预测会加剧或减轻截短变异影响的基因，为变异解读和优先考虑 NMD 靶向疗法提供了基础。

## Abstract
The molecular consequences of protein truncating variants depend strongly on whether their transcripts are eliminated by nonsense-mediated mRNA decay (NMD), yet NMD is still predicted largely from a small set of binary positional rules. How individual premature termination codons (PTCs) engage NMD across genes and transcript contexts therefore remains incompletely resolved. Here we integrated endogenous allele-specific PTC expression from large-scale genomic data, mRNA language-model prediction and high-throughput mutational scanning to revisit the rules that govern mammalian NMD. Using allele-specific expression measurements from large human cohorts, we trained NMDetective-AI on [~]14,000 somatic PTCs, and after testing it on [~]1,800 germline PTCs, found that it improves on previous models, with its accuracy approaching the reproducibility of the underlying measurements. We then generated experimental maps of NMD with deep mutational scanning, including [~]450 PTCs nearby the 50-nt penultimate exon boundary, [~]950 engineered PTCs across 9 exon lengths to resolve long-exon escape, and [~]11k PTCs across 139 genes to quantify and refine start-proximal evasion. Our results support the positional logic of mammalian NMD yet show that this logic is implemented quantitatively: the classical rules resolve into graded, gene-dependent response curves whose boundaries are shaped by transcript architecture and modulated by local sequence context. Applying this framework to population, disease and cancer datasets further identifies genes in which NMD is predicted to aggravate or ameliorate the effects of truncating variants, providing a basis for variant interpretation and for prioritizing NMD-directed therapies.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **NMDetective-AI** 的新模型，旨在通过整合基因组语言模型和大规模实验数据，实现对人类基因中无义介导的 mRNA 降解（NMD）效率的定量预测。

以下是对该论文的深度结构化总结：

### 1. 核心问题与整体含义
*   **研究背景**：无义介导的 mRNA 降解（NMD）是细胞的一种监控机制，负责识别并降解含有提前终止密码子（PTC）的 mRNA。
*   **核心问题**：传统的 NMD 预测主要依赖于简单的“50-nt 规则”（即 PTC 距离最后一个外显子交界处超过 50nt 则触发降解），这种二元规则无法解释不同基因、不同序列背景下 NMD 效率的巨大定量差异。
*   **整体含义**：本研究通过量化 NMD 效率，揭示了 NMD 并非简单的“开/关”逻辑，而是一个受转录本结构、外显子长度和局部序列背景共同调节的复杂定量过程。这对于理解遗传病致病机理及开发 NMD 靶向疗法具有重要意义。

### 2. 论文提出的方法论
*   **核心思想**：结合大规模自然发生的突变数据（内源性）与高通量人工突变扫描（实验性），利用深度学习捕捉序列特征。
*   **关键技术细节**：
    *   **NMDetective-AI 模型**：基于梯度提升决策树（GBDT）框架，整合了多种特征。
    *   **特征工程**：包括传统的距离特征（如到剪接位点的距离）、转录本结构特征（外显子长度、数量）以及**基因组语言模型（如 DNABERT-2）**生成的序列嵌入（Embeddings）。
    *   **数据整合**：利用等位基因特异性表达（ASE）数据来推断 NMD 效率，将 NMD 预测从分类问题转化为回归问题。

### 3. 实验设计
*   **数据集**：
    *   **训练集**：来自 TCGA 数据库的约 14,000 个体细胞 PTC 变异。
    *   **测试集**：来自 GTEx 数据库的约 1,800 个生殖系 PTC 变异。
    *   **实验验证集**：通过深度突变扫描（DMS）生成的约 11,000 个合成 PTC 变异。
*   **Benchmark（基准对比）**：
    *   对比了传统的 **50-nt 规则**。
    *   对比了早期的 **NMDetective**（基于线性回归或简单特征的模型）。
    *   对比了其他现有的 NMD 预测工具。
*   **实验场景**：涵盖了倒数第二外显子边界、长外显子逃逸、起始端近端逃逸（Start-proximal evasion）等多种复杂场景。

### 4. 资源与算力
*   **算力说明**：论文中提到使用了预训练的基因组语言模型（DNABERT-2）进行特征提取，并训练了复杂的机器学习模型。
*   **具体细节**：文中**未明确列出**具体的 GPU 型号、数量或总训练时长。但考虑到涉及大规模 ASE 数据处理和深度语言模型推理，通常需要高性能计算集群（如 NVIDIA A100 或 V100 级别）支持。

### 5. 实验数量与充分性
*   **实验规模**：
    *   使用了超过 1.5 万个内源性人类变异数据。
    *   进行了 139 个基因的大规模 DMS 实验，涵盖 1.1 万个工程化突变。
*   **充分性评价**：实验设计非常充分。研究不仅在自然群体数据上进行了验证，还通过人工设计的突变库精确控制变量（如改变外显子长度、移动 PTC 位置），从而系统性地测试了模型的泛化能力和生物学发现的可靠性。

### 6. 主要结论与发现
*   **定量逻辑**：NMD 效率是连续分布的，而非二元的。经典的 50-nt 规则实际上是一个分级的响应曲线。
*   **基因依赖性**：不同基因对 PTC 的敏感度不同，这受翻译重新起始（Reinitiation）和局部序列背景（如 GC 含量、特定基序）的影响。
*   **逃逸机制**：详细刻画了“起始端近端逃逸”和“长外显子逃逸”的边界，发现这些逃逸现象在不同基因间存在显著差异。
*   **临床价值**：NMDetective-AI 能更准确地预测截短变异在癌症和遗传病中的致病性，识别出哪些变异会通过 NMD 减轻毒性蛋白产生，哪些会因失去蛋白功能而致病。

### 7. 优点
*   **高精度**：预测准确性接近实验测量的重复性上限。
*   **多模态融合**：成功将生物信息学传统特征与前沿的 AI 语言模型嵌入相结合。
*   **实验闭环**：通过大规模 DMS 实验对计算模型进行了直接的生物学验证，增强了结论的说服力。
*   **定量化**：将 NMD 研究从“是否发生”提升到了“发生多少”的维度。

### 8. 不足与局限
*   **细胞系局限性**：DMS 实验主要在特定的细胞系（如 HEK293T）中完成，可能无法完全捕捉组织特异性的 NMD 调控。
*   **数据偏差**：ASE 数据受测序深度和基因表达水平影响，对于低表达基因的预测精度可能受限。
*   **黑盒性质**：虽然引入了语言模型提升了精度，但某些序列特征对 NMD 影响的具体生物学机制仍需进一步生化实验解释。

（完）
