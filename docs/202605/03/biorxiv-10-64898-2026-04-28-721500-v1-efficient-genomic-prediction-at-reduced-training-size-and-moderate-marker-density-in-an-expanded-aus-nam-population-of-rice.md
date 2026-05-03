---
title: Efficient genomic prediction at reduced training size and moderate marker density in an expanded aus-NAM population of rice
title_zh: 在扩展的水稻 aus-NAM 群体中利用缩减的训练规模和中等标记密度实现高效基因组预测
authors: "Kitony, J. K., Reyes, V. P., Sunohara, H., Tasaki, M., Yamasaki, M., Mori, J.-i., Shimazu, A., Nishiuchi, S., Michael, T. P., Doi, K."
date: 2026-05-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721500v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 评估了基因组预测(GP)和全基因组关联分析(GWAS)的性能
tldr: 本研究利用包含1818个重组近交系的扩展aus-NAM水稻群体，评估了基因组预测（GP）和全基因组关联分析（GWAS）的性能。发现GP在适中标记密度（约2万SNP）和训练规模（约500系）时即达准确度平台期，而GWAS则受益于更高密度标记。该研究为水稻育种中实施GP提供了重要基准。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究训练群体规模和标记密度对NAM群体中基因组选择效果的影响，以优化水稻育种效率。
method: 利用14个家系的1818个水稻系，结合GBS标记和全基因组测序变异，对11个农艺性状进行GP和GWAS分析。
result: GP准确度在标记密度达2万且训练规模约500时趋于稳定，而GWAS分辨率随标记密度增加而持续提升。
conclusion: 遗传力是决定GP性能的关键因素，研究为在单一环境下利用GP进行籼粳杂交育种提供了重要参考。
---

## 摘要
基因组选择 (GS) 可以加速作物的遗传增益，但其有效性取决于训练群体的设计和标记密度。嵌套关联制图 (NAM) 群体提供了一个结构化框架，能够在受控的遗传背景下捕捉广泛的等位基因多样性。在本研究中，我们评估了一个扩展的水稻 aus-NAM 群体的基因组预测 (GP) 和全基因组关联分析 (GWAS) 性能。该群体包含 14 个家系的 1,818 个重组近交系，涉及 11 个农艺性状，使用了测序基因分型 (GBS) 标记和推断的全基因组序列变异。研究发现，预测准确性在中等标记密度（约 2 万个 SNP）和约 500 个株系的训练群体（约占可用资源的 40% 至 60%）时达到平台期；性状遗传力成为预测性能的最强决定因素，而非模型选择或标记密度。相比之下，GWAS 的分辨率随着标记密度的增加而持续提高，从而能够检测到额外的位点，包括一个与抽穗期相关的 12 号染色体位点，同时一致地找回了已充分表征的基因，如 EARLY HEADING DATE 1 (Ehd1) 和 SEMIDWARF 1 (SD1)。这些对比模式表明，一旦全基因组变异得到充分代表，GP 即可达到近乎最优的性能，而 GWAS 则受益于更高标记密度带来的位点分辨率提升。本研究为在单一环境下利用 GP 实施涉及粳稻/籼稻杂交的育种计划建立了基准。

## Abstract
Genomic selection (GS) can accelerate genetic gain in crops, but its effectiveness depends on training population design and marker density. Nested association mapping (NAM) populations provide a structured framework that captures broad allelic diversity within a controlled genetic background. Here, we evaluated genomic prediction (GP) and genome-wide association study (GWAS) performance in an expanded aus-NAM population of rice comprising 1,818 recombinant inbred lines across 14 families and 11 agronomic traits, using genotyping-by-sequencing (GBS) markers and projected whole-genome sequence variants. Prediction accuracy plateaued at moderate marker densities (~20k SNPs) and with training populations of ~500 lines (~40 to 60% of the available pool), with trait heritability emerging as the strongest determinant of predictive performance rather than model choice or marker density. In contrast, GWAS resolution continued to improve with increasing marker density, enabling detection of additional loci, including a chromosome 12 locus associated with heading date, while consistently recovering well-characterized genes such as EARLY HEADING DATE 1 (Ehd1) and SEMIDWARF 1 (SD1) . These contrasting patterns indicate that GP reaches near-optimal performance once genome-wide variation is adequately represented, whereas GWAS benefits from higher marker density through improved locus resolution. The present study establishes a benchmark for implementing breeding programs involving japonica/indica crosses using GP in a single environment.

---

## 论文详细总结（自动生成）

这篇论文对扩展的水稻 aus-NAM 群体进行了深入的遗传学分析，重点探讨了标记密度、训练群体规模和模型选择对基因组预测（GP）准确性的影响，并对比了其与全基因组关联分析（GWAS）在分辨率上的差异。

以下是该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **研究动机**：全球粮食需求日益增长，传统的育种方法（依赖表型选择）效率较低，难以满足遗传增益的需求。基因组选择（GS/GP）虽有潜力，但在实际应用中，如何平衡**标记密度**、**训练群体规模**和**成本**仍缺乏系统性指导。
*   **核心问题**：在结构化的嵌套关联制图（NAM）群体中，GP 准确性何时达到饱和？GWAS 的分辨率如何随标记密度变化？如何优化育种策略以实现高效预测？

### 2. 核心方法论
*   **群体构建**：利用 14 个多样化的 aus 稻供体与共同亲本 T65（粳稻）杂交，构建了包含 1,818 个重组近交系（RILs）的扩展 aus-NAM 群体。
*   **基因分型技术**：
    *   采用测序基因分型（GBS）获取基础标记。
    *   利用亲本全基因组重测序（WGS）数据，通过单倍型块投影（Projection）技术，将标记密度提升至约 5.6 万个 SNP。
*   **算法流程**：
    *   **基因组预测（GP）**：对比了四种模型：rrBLUP（岭回归最佳线性无偏预测）、BayesB、Bayesian LASSO (BL) 和 RKHS（再生核希尔伯特空间）。
    *   **GWAS 优化**：采用基于 Lindley 过程的**局部评分法（Local Score Approach）**，结合连锁不平衡（LD）结构来精细定位候选基因区域。

### 3. 实验设计
*   **数据集**：1,818 个 RILs，涵盖 11 个农艺性状（如抽穗期 DTH、株高 CL、生物量 BM、产量相关性状等）。
*   **基准测试（Benchmark）**：
    *   **标记密度梯度**：1k, 2k, 5k, 10k, 20k, 40k SNPs。
    *   **训练规模梯度**：总群体的 20%, 40%, 60%, 80%, 100%（约 260 至 1300 个株系）。
*   **验证方式**：采用 5 折交叉验证（5-fold cross-validation），重复 10 次。

### 4. 资源与算力
*   **算力说明**：文中未明确提及具体的 GPU 型号或训练时长。
*   **软件环境**：分析主要在 R (v.4.5.2) 环境下完成，使用了 `rrBLUP`、`BGLR`、`pcaMethods` 等包，部分辅助分析使用 Python 3.11.7。

### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了 11 个性状、4 种预测模型、6 种标记密度和 5 种训练规模，实验组合非常丰富。
*   **充分性评价**：实验设计较为充分且客观。通过对不同遗传力性状的对比，揭示了 GP 性能的普遍规律。使用了重复交叉验证，确保了结果的统计可靠性。

### 6. 主要结论与发现
*   **GP 的平台效应**：GP 准确性在标记密度达到 **2 万个 SNP** 左右时即进入平台期，进一步增加密度收益微小。
*   **训练规模的影响**：使用约 **500 个株系**（总群体的 40-60%）作为训练集即可获得接近最优的预测效果。
*   **决定因素**：**性状遗传力**是决定 GP 准确性的最关键因素，其影响远大于模型选择和标记密度。
*   **GP 与 GWAS 的分歧**：GP 在中等密度下饱和，而 GWAS 的分辨率随标记密度增加而持续提升，能够发现更多微效位点（如 12 号染色体上的新抽穗期位点）。
*   **模型表现**：在训练群体较小时，贝叶斯模型（BayesB, BL）略优于 rrBLUP；但在群体规模充足时，各模型表现趋同。

### 7. 优点与亮点
*   **实用性强**：为育种家提供了明确的参数建议（20k 标记 + 500 个训练株系），有助于降低基因分型和表型鉴定的成本。
*   **群体优势**：NAM 群体兼顾了遗传多样性和受控的遗传背景，能够同时支持高精度的 GWAS 和高效的 GP。
*   **精细定位**：成功找回了 *Ehd1*、*SD1*、*FZP* 等已知关键基因，验证了方法的有效性。

### 8. 不足与局限
*   **环境单一**：表型数据仅采集自 2018 年日本名古屋的一个环境，未考虑基因型与环境的互作（G×E）。
*   **表型精度**：部分性状（除抽穗期外）采用单株测量，可能存在一定的表型误差，限制了低遗传力性状的预测上限。
*   **遗传背景限制**：虽然使用了 14 个 aus 供体，但共同亲本仅为 T65（粳稻），结论在其他亚种杂交组合中的普适性仍需验证。

（完）
