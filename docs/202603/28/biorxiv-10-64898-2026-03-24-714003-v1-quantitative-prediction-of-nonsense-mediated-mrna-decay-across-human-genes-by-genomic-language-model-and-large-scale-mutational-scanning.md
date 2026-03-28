---
title: Quantitative prediction of nonsense-mediated mRNA decay across human genes by genomic language model and large-scale mutational scanning
title_zh: 通过基因组语言模型和大规模突变扫描对人类基因中无义介导的 mRNA 降解进行定量预测
authors: "Veiner, M., Toledano, I., Palou-Marquez, G., Lehner, B., Supek, F."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.714003v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于预测 mRNA 降解的基因组语言模型
tldr: 本研究针对传统无义介导的mRNA降解（NMD）预测仅依赖简单二元规则的局限，开发了NMDetective-AI模型。通过整合大规模人类队列的等位基因特异性表达数据、mRNA语言模型及高通量突变扫描技术，研究者量化了不同基因背景下提前终止密码子（PTC）引发NMD的规律。结果表明，NMD受转录本结构和局部序列的定量调节，而非简单的位置规则。该成果为变异解读和NMD靶向治疗提供了重要依据。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-001.webp\", \"caption\": \"Figure 4: NMDetective-AI captures and predicts quantitative NMD evasion in penultimate and last exons.\", \"page\": 11, \"index\": 1, \"width\": 943, \"height\": 725}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-002.webp\", \"caption\": \"Figure 2: NMDetective-AI model development and validation.\", \"page\": 7, \"index\": 2, \"width\": 943, \"height\": 504}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-003.webp\", \"caption\": \"Figure 5: Systematic analysis of exon length and spatial determinants of NMD efficiency.\", \"page\": 14, \"index\": 3, \"width\": 943, \"height\": 1177}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-004.webp\", \"caption\": \"Figure 1: Overview of the NMD efficiency datasets and NMDetective-AI.\", \"page\": 4, \"index\": 4, \"width\": 943, \"height\": 317}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-005.webp\", \"caption\": \"Figure 7: Reinitiation and local sequence-context effects.\", \"page\": 19, \"index\": 5, \"width\": 941, \"height\": 839}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-006.webp\", \"caption\": \"Figure 6: Landscape and predictability of start-proximal NMD evasion.\", \"page\": 17, \"index\": 6, \"width\": 937, \"height\": 769}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-007.webp\", \"caption\": \"Figure 8: Selection of PTCs in germline and soma\", \"page\": 24, \"index\": 7, \"width\": 943, \"height\": 1219}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-008.webp\", \"caption\": \"Figure 3: Mutagenesis experiment overview and inter-replicate correlation.\", \"page\": 9, \"index\": 8, \"width\": 945, \"height\": 792}]"
motivation: 传统的NMD预测主要依赖简单的二元位置规则，无法准确反映不同基因和转录本背景下PTC引发NMD的复杂定量差异。
method: 整合大规模基因组数据的等位基因特异性表达、mRNA语言模型预测以及针对上万个PTC的高通量突变扫描实验。
result: 开发的NMDetective-AI模型显著提升了预测准确性，并揭示了NMD受外显子长度、起始近端逃逸等因素影响的定量响应曲线。
conclusion: NMD的调控逻辑是定量的且具有基因依赖性，这一新框架有助于更精准地评估截短变异在疾病和癌症中的致病性。
---

## 摘要
蛋白质截短变异的分子后果在很大程度上取决于其转录本是否被无义介导的 mRNA 降解 (NMD) 清除，然而，目前对 NMD 的预测仍主要依赖于一小组二元位置规则。因此，单个提前终止密码子 (PTC) 如何在不同基因和转录本背景下触发 NMD 仍未得到完全解决。在本研究中，我们整合了来自大规模基因组数据的内源性等位基因特异性 PTC 表达、mRNA 语言模型预测和高通量突变扫描，以重新审视调控哺乳动物 NMD 的规则。利用来自大型人类队列的等位基因特异性表达测量数据，我们在约 14,000 个体细胞 PTC 上训练了 NMDetective-AI；在约 1,800 个生殖系 PTC 上进行测试后，我们发现该模型优于以往模型，其准确性接近基础测量数据的可重复性。随后，我们通过深度突变扫描生成了 NMD 的实验图谱，包括倒数第二外显子边界 50-nt 附近的约 450 个 PTC、跨越 9 种外显子长度的约 950 个工程化 PTC（用于解析长外显子逃逸），以及跨越 139 个基因的约 1.1 万个 PTC（用于定量和细化起始端近端逃逸）。我们的结果支持哺乳动物 NMD 的位置逻辑，但表明这种逻辑是以定量方式实现的：经典规则转化为分级的、基因依赖性的响应曲线，其边界由转录本结构塑造并受局部序列背景调节。将该框架应用于群体、疾病和癌症数据集，进一步识别出 NMD 被预测会加剧或减轻截短变异影响的基因，为变异解读和优先考虑 NMD 靶向疗法提供了基础。

## Abstract
The molecular consequences of protein truncating variants depend strongly on whether their transcripts are eliminated by nonsense-mediated mRNA decay (NMD), yet NMD is still predicted largely from a small set of binary positional rules. How individual premature termination codons (PTCs) engage NMD across genes and transcript contexts therefore remains incompletely resolved. Here we integrated endogenous allele-specific PTC expression from large-scale genomic data, mRNA language-model prediction and high-throughput mutational scanning to revisit the rules that govern mammalian NMD. Using allele-specific expression measurements from large human cohorts, we trained NMDetective-AI on [~]14,000 somatic PTCs, and after testing it on [~]1,800 germline PTCs, found that it improves on previous models, with its accuracy approaching the reproducibility of the underlying measurements. We then generated experimental maps of NMD with deep mutational scanning, including [~]450 PTCs nearby the 50-nt penultimate exon boundary, [~]950 engineered PTCs across 9 exon lengths to resolve long-exon escape, and [~]11k PTCs across 139 genes to quantify and refine start-proximal evasion. Our results support the positional logic of mammalian NMD yet show that this logic is implemented quantitatively: the classical rules resolve into graded, gene-dependent response curves whose boundaries are shaped by transcript architecture and modulated by local sequence context. Applying this framework to population, disease and cancer datasets further identifies genes in which NMD is predicted to aggravate or ameliorate the effects of truncating variants, providing a basis for variant interpretation and for prioritizing NMD-directed therapies.

---

## 论文详细总结（自动生成）

### 论文总结：通过基因组语言模型和大规模突变扫描定量预测人类 NMD

#### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：无义介导的 mRNA 降解（NMD）是细胞清除含有提前终止密码子（PTC）的转录本的关键质量控制机制。长期以来，生物学界主要依赖简单的“二元规则”（如 50-nt 规则、末端外显子规则）来预测 NMD。然而，这些规则无法解释不同基因背景下 NMD 效率的定量差异，导致在临床变异解读和药物研发中存在预测偏差。
*   **研究背景**：蛋白质截短变异（PTVs）的后果取决于 NMD 是否发生。如果 NMD 效率高，则表现为蛋白质缺失（单倍剂量不足）；如果 NMD 逃逸，则可能产生具有显性负效应或获得性功能的截短蛋白。因此，实现对 NMD 的**定量预测**对于理解疾病机制至关重要。

#### 2. 方法论：核心思想与技术细节
*   **核心思想**：将大规模人类群体的内源性表达数据与深度学习语言模型相结合，并利用合成生物学手段进行高通量验证，构建一个能够捕捉复杂序列特征的定量预测模型。
*   **关键技术细节**：
    *   **NMDetective-AI 模型**：基于基因组/mRNA 语言模型（Genomic Language Models）提取的特征，整合了转录本结构信息（如外显子长度、剪接位点距离等）。
    *   **数据驱动训练**：利用来自 TCGA（癌症体细胞变异）和 GTEx（生殖系变异）的大规模**等位基因特异性表达（ASE）**数据。ASE 能够直接反映 PTC 含有转录本相对于正常转录本的降解程度。
    *   **定量建模**：模型不再仅仅输出“是/否”降解，而是输出一个连续的 NMD 效率分值（0 到 1 之间），反映 mRNA 的剩余水平。

#### 3. 实验设计与 Benchmark
*   **数据集**：
    *   **训练集**：约 14,000 个体细胞 PTC 变异。
    *   **测试集**：约 1,800 个生殖系 PTC 变异。
    *   **实验验证集**：通过**深度突变扫描（DMS）**生成的三个合成库：
        1.  倒数第二外显子边界附近的 450 个 PTC。
        2.  针对 9 种不同外显子长度设计的 950 个 PTC（研究长外显子逃逸）。
        3.  跨越 139 个基因的 11,000 个 PTC（研究起始端近端逃逸）。
*   **Benchmark（对比方法）**：
    *   传统的二元位置规则（50-nt rule）。
    *   早期的 NMD 预测模型（如原始的 NMDetective）。
    *   **基准线**：以 ASE 测量数据的重复性（Reproducibility）作为预测准确性的上限。

#### 4. 资源与算力
*   **算力说明**：论文中未详细列出具体的 GPU 型号、数量或训练时长。考虑到使用了基因组语言模型（通常涉及 Transformer 架构）和处理上万个变异的 ASE 数据，该研究通常需要高性能计算集群（如 NVIDIA A100 或 V100 级别）进行模型微调和推理。

#### 5. 实验数量与充分性
*   **实验充分性**：非常充分。
    *   **多维度验证**：不仅在自然发生的群体变异上验证，还通过人工设计的 DMS 实验精确控制变量（如外显子长度、到起始密码子的距离）。
    *   **覆盖面广**：涵盖了 NMD 的多个特殊区域（起始端、末端、长外显子），并分析了局部序列背景（如翻译重新起始）的影响。
    *   **客观性**：通过对比生殖系和体细胞变异，证明了模型在不同生物学背景下的通用性。

#### 6. 主要结论与发现
*   **定量逻辑**：哺乳动物的 NMD 遵循位置逻辑，但这种逻辑是**定量且分级**的。经典规则（如 50-nt 规则）在不同基因中表现为不同的响应曲线。
*   **起始端近端逃逸（Start-proximal evasion）**：发现 NMD 逃逸在转录本起始端非常普遍，且这种逃逸受局部序列背景和翻译重新起始（Reinitiation）的强烈调节。
*   **长外显子效应**：定量解析了外显子长度如何影响 NMD 效率，打破了以往对长外显子逃逸的模糊认识。
*   **临床意义**：NMDetective-AI 能够识别出哪些基因的截短变异会因 NMD 逃逸而产生潜在的有毒蛋白，为精准医疗提供了工具。

#### 7. 优点
*   **高精度**：预测准确性接近实验测量的重复性极限。
*   **机制洞察**：通过 AI 模型发现了传统规则忽略的特征，如局部序列对 NMD 的微调作用。
*   **数据融合**：成功将“自上而下”的群体基因组数据与“自下而上”的合成突变扫描实验相结合。

#### 8. 不足与局限
*   **组织特异性**：虽然使用了 GTEx 数据，但 NMD 在不同组织或细胞类型中的差异性仍有待进一步细化。
*   **模型复杂性**：作为深度学习模型，其内部决策逻辑（可解释性）虽有分析，但相比简单规则仍较难直观理解。
*   **偏差风险**：ASE 数据受测序深度和映射偏差（Mapping bias）影响，可能在低表达基因中存在噪声。

（完）
