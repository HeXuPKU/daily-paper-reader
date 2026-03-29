---
title: Quantitative prediction of nonsense-mediated mRNA decay across human genes by genomic language model and large-scale mutational scanning
title_zh: 通过基因组语言模型和大规模突变扫描对人类基因的无义介导的 mRNA 降解进行定量预测
authors: "Veiner, M., Toledano, I., Palou-Marquez, G., Lehner, B., Supek, F."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.714003v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于mRNA降解预测的基因组语言模型
tldr: 本研究旨在解决无义介导的mRNA降解（NMD）预测仍依赖于简单二元规则的问题。通过整合大规模基因组等位基因特异性表达数据、mRNA语言模型和高通量突变扫描，开发了NMDetective-AI模型。该模型在预测体细胞和生殖系提前终止密码子（PTC）引发的NMD方面表现优异。研究揭示了NMD遵循定量而非简单的位置逻辑，受转录本结构和局部序列调节，为变异解读和NMD靶向治疗提供了重要依据。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-001.webp\", \"caption\": \"Figure 4: NMDetective-AI captures and predicts quantitative NMD evasion in penultimate and last exons.\", \"page\": 11, \"index\": 1, \"width\": 943, \"height\": 725}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-002.webp\", \"caption\": \"Figure 2: NMDetective-AI model development and validation.\", \"page\": 7, \"index\": 2, \"width\": 943, \"height\": 504}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-003.webp\", \"caption\": \"Figure 5: Systematic analysis of exon length and spatial determinants of NMD efficiency.\", \"page\": 14, \"index\": 3, \"width\": 943, \"height\": 1177}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-004.webp\", \"caption\": \"Figure 1: Overview of the NMD efficiency datasets and NMDetective-AI.\", \"page\": 4, \"index\": 4, \"width\": 943, \"height\": 317}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-005.webp\", \"caption\": \"Figure 7: Reinitiation and local sequence-context effects.\", \"page\": 19, \"index\": 5, \"width\": 941, \"height\": 839}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-006.webp\", \"caption\": \"Figure 6: Landscape and predictability of start-proximal NMD evasion.\", \"page\": 17, \"index\": 6, \"width\": 937, \"height\": 769}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-007.webp\", \"caption\": \"Figure 8: Selection of PTCs in germline and soma\", \"page\": 24, \"index\": 7, \"width\": 943, \"height\": 1219}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-714003-v1/fig-008.webp\", \"caption\": \"Figure 3: Mutagenesis experiment overview and inter-replicate correlation.\", \"page\": 9, \"index\": 8, \"width\": 945, \"height\": 792}]"
motivation: 传统的NMD预测主要依赖于简单的二元位置规则，无法准确反映不同基因和转录本背景下PTC引发NMD的复杂定量差异。
method: 整合大规模人类队列的等位基因特异性表达数据，利用mRNA语言模型训练NMDetective-AI，并结合深度突变扫描技术对数千个PTC进行实验验证。
result: NMDetective-AI显著提升了NMD预测精度，并揭示了NMD受外显子长度、起始密码子距离及局部序列背景等因素的定量调节。
conclusion: 研究证明了哺乳动物NMD逻辑是定量的且具有基因依赖性，为理解疾病相关截短变异的影响及开发NMD定向疗法奠定了基础。
---

## 摘要
蛋白质截短变异的分子后果在很大程度上取决于其转录本是否被无义介导的 mRNA 降解（NMD）清除，然而，目前对 NMD 的预测仍主要依赖于一小组二元位置规则。因此，单个提前终止密码子（PTC）如何在不同基因和转录本背景下触发 NMD 仍未得到完全解决。在本研究中，我们整合了来自大规模基因组数据的内源性等位基因特异性 PTC 表达、mRNA 语言模型预测以及高通量突变扫描，以重新审视调控哺乳动物 NMD 的规则。利用来自大型人类队列的等位基因特异性表达测量数据，我们在约 14,000 个体细胞 PTC 上训练了 NMDetective-AI；在约 1,800 个生殖系 PTC 上进行测试后，我们发现该模型优于以往模型，其准确性接近基础测量数据的可重复性。随后，我们利用深度突变扫描生成了 NMD 的实验图谱，包括倒数第二外显子边界 50nt 附近的约 450 个 PTC、跨越 9 种外显子长度的约 950 个工程化 PTC（旨在解析长外显子逃逸），以及分布在 139 个基因中的约 1.1 万个 PTC（旨在量化并细化起始端近端逃逸）。我们的结果支持哺乳动物 NMD 的位置逻辑，但表明这种逻辑是以定量方式实现的：经典规则转化为分级的、基因依赖性的响应曲线，其边界由转录本结构塑造并受局部序列背景调节。将该框架应用于群体、疾病和癌症数据集，进一步识别出 NMD 被预测会加剧或减轻截短变异影响的基因，为变异解读和优先考虑 NMD 靶向疗法提供了基础。

## Abstract
The molecular consequences of protein truncating variants depend strongly on whether their transcripts are eliminated by nonsense-mediated mRNA decay (NMD), yet NMD is still predicted largely from a small set of binary positional rules. How individual premature termination codons (PTCs) engage NMD across genes and transcript contexts therefore remains incompletely resolved. Here we integrated endogenous allele-specific PTC expression from large-scale genomic data, mRNA language-model prediction and high-throughput mutational scanning to revisit the rules that govern mammalian NMD. Using allele-specific expression measurements from large human cohorts, we trained NMDetective-AI on [~]14,000 somatic PTCs, and after testing it on [~]1,800 germline PTCs, found that it improves on previous models, with its accuracy approaching the reproducibility of the underlying measurements. We then generated experimental maps of NMD with deep mutational scanning, including [~]450 PTCs nearby the 50-nt penultimate exon boundary, [~]950 engineered PTCs across 9 exon lengths to resolve long-exon escape, and [~]11k PTCs across 139 genes to quantify and refine start-proximal evasion. Our results support the positional logic of mammalian NMD yet show that this logic is implemented quantitatively: the classical rules resolve into graded, gene-dependent response curves whose boundaries are shaped by transcript architecture and modulated by local sequence context. Applying this framework to population, disease and cancer datasets further identifies genes in which NMD is predicted to aggravate or ameliorate the effects of truncating variants, providing a basis for variant interpretation and for prioritizing NMD-directed therapies.

---

## 论文详细总结（自动生成）

这是一份关于论文《通过基因组语言模型和大规模突变扫描对人类基因的无义介导的 mRNA 降解进行定量预测》的结构化深度总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：无义介导的 mRNA 降解（NMD）是细胞清除含有提前终止密码子（PTC）的转录本的关键质量控制机制。长期以来，预测 NMD 主要依赖于简单的二元位置规则（如“50-nt 规则”）。然而，这些规则无法解释约 1/3 的 NMD 效率差异，且无法反映不同基因背景下的定量变化。
*   **研究动机**：现有的 NMD 模型缺乏对转录本结构、局部序列背景和基因特异性差异的定量捕捉。准确预测 NMD 效率对于解读致病性变异、评估癌症驱动突变以及开发针对 NMD 的疗法（如 NMD 抑制剂或 PTC 读通药物）至关重要。

### 2. 方法论：核心思想与技术细节
*   **核心思想**：将大规模人类基因组/转录组观测数据与深度学习语言模型相结合，并利用高通量实验（DMS）进行验证和机制细化。
*   **关键技术 - NMDetective-AI**：
    *   **基础模型**：基于 **Orthrus**（一个拥有 10M 参数、在 4500 万个哺乳动物转录本上预训练的 Mamba 架构基因组语言模型）。
    *   **输入编码**：采用 6 轨道独热编码（4 种核苷酸 + 1 个 CDS 读码框轨道 + 1 个剪接位点轨道）。
    *   **训练数据**：利用来自 TCGA 的约 14,000 个体细胞 PTC 变异，以等位基因特异性表达（ASE）作为 NMD 效率的定量标签。
    *   **归一化**：将 NMD 效率线性转换至 [-0.5, 0.5] 区间，其中 0.5 代表完全降解，-0.5 代表完全逃逸。
*   **实验技术 - 深度突变扫描 (DMS)**：
    *   设计了针对“50-nt 规则”、“长外显子规则”和“起始端近端规则”的多个微基因（Minigene）文库。
    *   利用 Illumina 和 Nanopore 测序定量测量数千个 PTC 变异对 mRNA 丰度的影响。

### 3. 实验设计与 Benchmark
*   **数据集**：
    *   **训练/验证集**：TCGA 体细胞 PTC（约 1.5 万个唯一变异）。
    *   **独立测试集**：TCGA 生殖系 PTC（1,065 个）和 GTEx 生殖系 PTC（763 个）。
    *   **实验验证集**：涵盖 139 个基因、超过 1.1 万个 PTC 的 DMS 数据。
*   **Benchmark（对比方法）**：
    *   **NMDetective-A**：基于手工特征的随机森林模型。
    *   **NMDetective-B**：基于规则的决策树模型。
    *   **原始规则**：经典的 50-nt 规则、长外显子规则等。
*   **对比结果**：NMDetective-AI 在所有测试集上的表现均显著优于旧模型，其 Spearman 相关系数（ρ ≈ 0.67）已接近测量数据本身的可重复性上限（ρ ≈ 0.70）。

### 4. 资源与算力
*   **算力说明**：论文提到使用了 **W&B (Weights & Biases)** 进行贝叶斯超参数搜索（共 42 次迭代）。
*   **具体细节**：文中未明确给出具体的 GPU 型号、数量或总训练时长。但考虑到 Orthrus 模型规模（10M 参数）相对较小，且训练集规模在万级，推测单次训练在单张现代 GPU（如 A100 或 RTX 3090）上可在数小时内完成。

### 5. 实验数量与充分性
*   **实验规模**：
    *   **计算实验**：进行了消融实验（对比了全微调、线性探测和随机初始化），证明了预训练语言模型的必要性。
    *   **生物实验**：设计了 3 大类 DMS 文库，涵盖了倒数第二外显子边界、9 种不同长度的外显子以及 139 个基因的起始端区域。
*   **充分性评价**：实验设计非常充分且具有高度的互补性。通过将“自上而下”的群体基因组分析与“自下而上”的合成生物学实验相结合，不仅验证了模型的准确性，还揭示了 NMD 逃逸的生物物理机制（如翻译再起始）。

### 6. 主要结论与发现
*   **定量逻辑**：NMD 并非简单的二元开关，而是一个受基因依赖的、定量的“分级响应”。
*   **规则细化**：
    *   **50-nt 规则**：实际上是一个逻辑回归曲线（Logistic Curve），拐点在 54-nt 左右。
    *   **长外显子规则**：证实了长外显子（>400nt）存在 NMD 逃逸，且逃逸程度随 PTC 位置和外显子长度定量变化。
    *   **起始端近端规则**：发现翻译再起始（Reinitiation）是逃逸的主因，受下游 AUG 的 Kozak 序列强度和距离调节。
*   **临床意义**：识别出 NMD 会“加剧”或“减轻”疾病表型的特定基因，为精准医疗提供了预测图谱。

### 7. 优点
*   **端到端学习**：NMDetective-AI 无需人工定义复杂的生化特征，直接从序列和剪接注释中学习隐藏的“转录组语法”。
*   **高精度**：预测精度达到了目前该领域的最高水平，接近实验测量的信噪比极限。
*   **机制深度**：通过 DMS 实验不仅提供了数据，还深入探讨了翻译动力学和序列背景（如 UGACUA 基序）对 NMD 的影响。

### 8. 不足与局限
*   **黑盒性质**：尽管作者尝试通过拟合逻辑曲线来解释模型，但深度学习模型内部的具体决策逻辑仍具有一定的不可解释性。
*   **微基因局限**：DMS 实验主要基于微基因报告系统，可能无法完全模拟内源性染色质环境或复杂的长程 RNA 相互作用。
*   **组织特异性**：虽然模型在多组织数据上表现良好，但对于某些极具组织特异性的 NMD 调节机制，可能仍需更细粒度的数据支持。

（完）
