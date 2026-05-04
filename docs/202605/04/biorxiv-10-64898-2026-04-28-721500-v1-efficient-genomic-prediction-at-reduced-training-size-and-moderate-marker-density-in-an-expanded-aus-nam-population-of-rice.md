---
title: Efficient genomic prediction at reduced training size and moderate marker density in an expanded aus-NAM population of rice
title_zh: 在扩展的水稻 aus-NAM 群体中利用缩减的训练规模和中等标记密度实现高效基因组预测
authors: "Kitony, J. K., Reyes, V. P., Sunohara, H., Tasaki, M., Yamasaki, M., Mori, J.-i., Shimazu, A., Nishiuchi, S., Michael, T. P., Doi, K."
date: 2026-05-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721500v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 嵌套关联映射群体中的GWAS性能评估
tldr: 本研究利用包含1818个重组近交系的扩展aus-NAM水稻群体，评估了基因组预测（GP）和全基因组关联分析（GWAS）的性能。研究发现，GP在适中标记密度（约2万个SNP）和训练群体规模（约500个系）下即可达到性能平台，而GWAS则受益于更高密度的标记以提高分辨率。该研究为利用GP优化水稻育种程序提供了重要参考。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究训练群体规模和标记密度对嵌套关联制图（NAM）群体中基因组选择效率的影响。
method: 基于14个家系的1818个水稻重组近交系，利用GBS标记和全基因组序列变异评估11个农艺性状的GP和GWAS表现。
result: GP准确率在标记密度达2万且训练样本约500个时趋于平稳，而GWAS分辨率随标记密度增加而持续提升。
conclusion: 遗传力是决定GP性能的关键因素，研究为在特定环境下实施高效的水稻基因组选择育种建立了基准。
---

## 摘要
基因组选择 (GS) 可以加速作物的遗传增益，但其有效性取决于训练群体的设计和标记密度。嵌套关联制图 (NAM) 群体提供了一个结构化框架，能够在受控的遗传背景下捕捉广泛的等位基因多样性。在本研究中，我们评估了一个扩展的水稻 aus-NAM 群体的基因组预测 (GP) 和全基因组关联分析 (GWAS) 性能。该群体包含 14 个家系的 1,818 个重组近交系，涉及 11 个农艺性状，使用了测序基因分型 (GBS) 标记和推断的全基因组序列变异。研究发现，预测准确性在中等标记密度（约 2 万个 SNP）和约 500 个株系的训练群体（约占可用资源的 40% 至 60%）时达到平台期；性状遗传力成为预测性能的最强决定因素，而非模型选择或标记密度。相比之下，GWAS 的分辨率随着标记密度的增加而持续提高，从而能够检测到额外的位点，包括一个与抽穗期相关的 12 号染色体位点，同时一致地找回了已充分表征的基因，如 EARLY HEADING DATE 1 (Ehd1) 和 SEMIDWARF 1 (SD1)。这些对比模式表明，一旦全基因组变异得到充分代表，GP 即可达到近乎最优的性能，而 GWAS 则受益于更高标记密度带来的位点分辨率提升。本研究为在单一环境下利用 GP 实施涉及粳稻/籼稻杂交的育种计划建立了基准。

## Abstract
Genomic selection (GS) can accelerate genetic gain in crops, but its effectiveness depends on training population design and marker density. Nested association mapping (NAM) populations provide a structured framework that captures broad allelic diversity within a controlled genetic background. Here, we evaluated genomic prediction (GP) and genome-wide association study (GWAS) performance in an expanded aus-NAM population of rice comprising 1,818 recombinant inbred lines across 14 families and 11 agronomic traits, using genotyping-by-sequencing (GBS) markers and projected whole-genome sequence variants. Prediction accuracy plateaued at moderate marker densities (~20k SNPs) and with training populations of ~500 lines (~40 to 60% of the available pool), with trait heritability emerging as the strongest determinant of predictive performance rather than model choice or marker density. In contrast, GWAS resolution continued to improve with increasing marker density, enabling detection of additional loci, including a chromosome 12 locus associated with heading date, while consistently recovering well-characterized genes such as EARLY HEADING DATE 1 (Ehd1) and SEMIDWARF 1 (SD1) . These contrasting patterns indicate that GP reaches near-optimal performance once genome-wide variation is adequately represented, whereas GWAS benefits from higher marker density through improved locus resolution. The present study establishes a benchmark for implementing breeding programs involving japonica/indica crosses using GP in a single environment.

---

## 论文详细总结（自动生成）

这篇论文对水稻 aus-NAM（嵌套关联映射）群体中的基因组预测（GP）和全基因组关联分析（GWAS）进行了深入评估。以下是详细的结构化总结：

### 1. 论文的核心问题与整体含义
*   **研究动机**：基因组选择（GS）能显著加速育种进程，但在实际应用中，高密度的基因分型和大规模训练群体的构建成本高昂。
*   **核心问题**：在复杂的嵌套关联映射（NAM）群体中，究竟需要多大的**训练群体规模（TPS）**和多高的**标记密度（MD）**才能达到最优的预测准确率？
*   **研究背景**：水稻 aus-NAM 群体结合了广泛的遗传多样性和受控的群体结构，是研究复杂性状遗传基础和优化预测模型的理想材料。

### 2. 论文提出的方法论
*   **核心思想**：通过对一个包含 14 个家系、1,818 个重组近交系（RILs）的扩展 aus-NAM 群体进行多维度采样，对比不同参数下的 GP 和 GWAS 表现。
*   **关键技术细节**：
    *   **群体构建**：以粳稻品种“越光”（Koshihikari）为共同亲本，与 14 个 aus 型水稻品种杂交产生。
    *   **基因分型**：利用测序基因分型（GBS）获得标记，并进一步推断（Projected）出全基因组序列变异（WGS-level variants）。
    *   **预测模型**：对比了三种主流模型：**GBLUP**（基于基因组的最佳线性无偏预测）、**BayesB**（贝叶斯模型）和 **RKHS**（再生核希尔伯特空间模型）。
    *   **评估流程**：采用交叉验证法，系统性地改变训练集大小（从 100 到 1,000+）和标记数量（从数百个到数万个）。

### 3. 实验设计
*   **数据集**：1,818 个水稻 RILs，涵盖 11 个农艺性状（如抽穗期、株高、产量相关性状等）。
*   **Benchmark（基准）**：以全群体规模和最高标记密度下的预测结果作为性能上限基准。
*   **对比维度**：
    *   **模型对比**：GBLUP vs. BayesB vs. RKHS。
    *   **标记密度对比**：从稀疏标记到中等密度（GBS）再到高密度（WGS）。
    *   **训练规模对比**：不同比例的子集采样。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的硬件配置（如 GPU 型号、数量）或具体的训练时长。这在植物育种和遗传学论文中较为常见，因为此类计算通常在高性能计算集群（HPC）上使用 CPU 并行完成。

### 5. 实验数量与充分性
*   **实验规模**：研究涉及 14 个家系、11 个性状、3 种模型以及数十种 TPS 和 MD 的组合，实验总量非常庞大。
*   **充分性与客观性**：
    *   实验设计考虑了性状遗传力的差异，涵盖了从高遗传力（如抽穗期）到低遗传力的性状。
    *   通过多次随机采样和交叉验证，确保了结果的统计可靠性。
    *   对比了 GWAS 和 GP 对标记密度的不同敏感性，体现了研究的全面性。

### 6. 论文的主要结论与发现
*   **GP 的平台效应**：基因组预测准确率在标记密度达到约 **2 万个 SNP** 且训练群体规模达到约 **500 个株系**（约占总体的 40%-60%）时即进入平台期。
*   **决定因素**：**性状遗传力**是决定预测准确率的最关键因素，其影响力远超模型选择和标记密度的微调。
*   **GWAS 与 GP 的差异**：GWAS 的分辨率随标记密度增加而持续提升（能发现更多微效位点），而 GP 对超高密度标记并不敏感。
*   **基因定位**：GWAS 成功找回了 *Ehd1* 和 *SD1* 等已知重要基因，并在 12 号染色体上发现了新的抽穗期相关位点。

### 7. 优点
*   **实用性强**：为育种家提供了明确的参数建议（500 株系 + 2 万标记），有助于在保证准确率的同时降低育种成本。
*   **群体代表性**：使用了大规模的 aus-NAM 群体，相比单一杂交群体，其结论更具普适性。
*   **多模型验证**：证明了在标记充足的情况下，简单模型（如 GBLUP）与复杂模型性能相当，简化了实际操作。

### 8. 不足与局限
*   **环境局限性**：实验是在**单一环境**下进行的，未考虑基因型与环境互作（G×E）对预测准确率的影响。
*   **遗传背景限制**：虽然使用了 NAM 群体，但结论主要适用于粳稻与 aus 型水稻的杂交组合，在其他亚种（如籼/粳杂交）中的适用性仍需验证。
*   **低遗传力性状挑战**：对于低遗传力性状，即使增加样本量和标记密度，预测效果依然有限，论文未提出针对性的改进方案。

（完）
