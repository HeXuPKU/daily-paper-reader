---
title: Efficient genomic prediction at reduced training size and moderate marker density in an expanded aus-NAM population of rice
title_zh: 在扩展的水稻 aus-NAM 群体中利用缩减的训练规模和中等标记密度实现高效基因组预测
authors: "Kitony, J. K., Reyes, V. P., Sunohara, H., Tasaki, M., Yamasaki, M., Mori, J.-i., Shimazu, A., Nishiuchi, S., Michael, T. P., Doi, K."
date: 2026-05-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721500v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 评估NAM群体中的基因组预测和GWAS性能
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

这是一份关于论文《Efficient genomic prediction at reduced training size and moderate marker density in an expanded aus-NAM population of rice》的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：在水稻育种中，如何平衡基因组选择（GS/GP）的预测准确性与实施成本（包括基因分型密度和表型鉴定规模）？
*   **研究背景**：全球粮食需求增长要求加速育种进程。基因组预测（GP）虽有潜力，但其效率受训练群体设计、标记密度、遗传结构及环境互作等多种因素制约。
*   **研究意义**：通过构建一个包含14个家系的扩展型aus-NAM（嵌套关联制图）群体，研究者旨在确定GP准确性达到饱和的实际阈值，并探讨这些阈值与全基因组关联分析（GWAS）分辨率需求之间的差异，为高效育种计划提供基准。

### 2. 论文提出的方法论
*   **核心思想**：利用NAM群体特有的遗传结构（共同亲本T65与14个多样化aus供体杂交），结合高密度SNP投影技术，系统评估不同参数对GP和GWAS的影响。
*   **关键技术细节**：
    *   **群体构建**：1,818个重组近交系（RILs），分为14个双亲家系。
    *   **基因分型**：采用测序基因分型（GBS）获得初始标记，并利用亲本全基因组重测序（WGS）数据将SNP投影至RILs，生成约56k的高密度SNP面板。
    *   **GP模型**：对比了四种算法：岭回归最佳线性无偏预测（rrBLUP）、再生核希尔伯特空间（RKHS）、贝叶斯B（BayesB）和贝叶斯LASSO（BL）。
    *   **GWAS分析**：采用局部评分法（Local score approach）结合连锁不平衡（LD）热图，对候选区域进行精细定位。

### 3. 实验设计
*   **数据集**：1,818个水稻RILs，涵盖11个农艺性状（如抽穗期DTH、株高CL、生物量BM等）。
*   **Benchmark与对比变量**：
    *   **标记密度**：设置了1k、2k、5k、10k、20k、40k等不同梯度的SNP密度。
    *   **训练规模**：设置了可用训练池的20%、40%、60%、80%和100%（约260至1300个株系）。
    *   **验证方式**：采用10次重复的5折交叉验证。
*   **对比方法**：在GP中对比了上述四种统计模型；在GWAS中对比了不同标记密度下的信号检测能力。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的硬件算力（如GPU型号或数量）。
*   **软件环境**：分析主要在 R (v.4.5.2) 环境下完成，使用了 `rrBLUP`、`BGLR`、`pcaMethods`、`ggplot2` 等包，部分分析使用了 Python 3.11.7。

### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了14个家系、11个复杂性状、6种标记密度、5种训练规模以及4种预测模型。
*   **充分性评价**：实验设计非常**充分且系统**。通过多维度的交叉对比，清晰地展示了预测准确性的变化趋势。使用重复交叉验证确保了结果的客观性，对NAM群体结构的PCA和进化树分析证明了实验材料的代表性和公平性。

### 6. 主要结论与发现
*   **GP的饱和效应**：预测准确性在标记密度达到**约2万个SNPs**以及训练群体规模达到**约500个株系（40-60%）**时进入平台期，进一步增加投入带来的增益微乎其微。
*   **遗传力的主导作用**：性状的遗传力（h²）是决定GP准确性的最关键因素，其影响远超模型选择和标记密度。
*   **GP与GWAS的差异**：GP在中等密度下即可达标，但GWAS的分辨率随标记密度增加而持续提升，能够发现更多微效位点（如Chr 12上的新位点）。
*   **模型表现**：在训练样本较少时，贝叶斯模型和RKHS略优于rrBLUP；在样本充足时，各模型表现趋同。

### 7. 优点（亮点）
*   **两层策略建议**：提出了针对育种的实用策略——利用中等密度标记进行大规模预测，利用高密度标记进行精准定位。
*   **精细定位能力**：成功找回了*Ehd1*、*SD1*、*FZP*等已知关键基因，验证了NAM群体在复杂性状解析中的强大功能。
*   **资源贡献**：提供了扩展的aus-NAM群体这一宝贵的遗传资源，并建立了粳/籼杂交育种的预测基准。

### 8. 不足与局限
*   **环境局限性**：表型数据仅基于**单一环境（日本名古屋）**采集，未考虑基因型与环境互作（G×E）对预测准确性的影响。
*   **遗传多样性范围**：虽然使用了14个aus供体，但共同亲本仅为一种粳稻（T65），结果在其他遗传背景下的普适性仍需验证。
*   **性状局限**：对于低遗传力性状（如结实率SSR、产量相关性状），GP的预测效果依然较差，单纯依靠增加标记或样本量无法解决表型质量带来的瓶颈。

（完）
