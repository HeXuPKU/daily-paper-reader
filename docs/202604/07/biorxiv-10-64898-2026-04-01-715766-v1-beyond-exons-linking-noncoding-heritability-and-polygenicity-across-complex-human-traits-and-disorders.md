---
title: "Beyond Exons: Linking Noncoding Heritability and Polygenicity across Complex Human Traits and Disorders"
title_zh: 超越外显子：关联复杂人类性状与疾病中的非编码遗传率与多基因性
authors: "Fuhrer, J., Shadrin, A. A., Hughes, T., Parker, N., Hindley, G., Frei, E., Nguyen, D., Smeland, O. B., Djurovic, S., Andreassen, O., Dale, A., Frei, O."
date: 2026-04-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.01.715766v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 基于MiXeR的框架，用于划分复杂性状在基因组区域的遗传力
tldr: 本研究探讨了复杂性状的多基因性与SNP遗传力在基因组功能区域分布之间的关系。通过对34种性状的分析，发现外显子对遗传力的贡献随多基因性增加而降低，而基因间区域则呈现相反趋势。研究揭示了高多基因性性状（如精神疾病）更依赖分散的调控效应，而非基因近端的调控，为理解不同人类性状遗传架构的异质性提供了重要证据。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-01-715766-v1/fig-001.webp\", \"caption\": \"Figure 3: Contribution of individual functional annotations relative to the full model with 74 annotations. Phenotypes are ordered by their polygenicity remaining after pruning with 𝑟g=0.3, favoring phenotypes with higher heritability. Annotations are sorted by their Euclidean distance. On the left, next to relative numbers of nucleotides (genome, exon, intron, intergenic), the Spearman rank correlation value between ACS and polygenicity across phenotypes is indicated. The symbols following each functional annotation on the right indicate the significance after Bonferroni correction for the Spearman correlation (significance: ***: p<0.001, **: p<0.01, *: p <0.05, n.s.: p≥0.05).\", \"page\": 7, \"index\": 1, \"width\": 970, \"height\": 1011}]"
motivation: 探究复杂性状的多基因性差异如何与SNP遗传力在基因组不同功能区域的定位相关联。
method: 利用基于MiXeR的框架对34种性状的遗传力进行分区，并引入似然贡献评分量化不同功能注释的影响。
result: 外显子对遗传力的贡献随多基因性增加而显著下降，且高多基因性性状在比较基因组学和变异效应评分中表现出更强的关联。
conclusion: 遗传力的功能分区随多基因性系统性变化，反映了从基因近端调控向广泛分散的调控效应的架构转变。
---

## 摘要
复杂性状的遗传架构跨越了一个多基因性的连续谱，但目前尚不清楚多基因性的差异如何与全基因组范围内 SNP 遗传率的功能定位相关联。我们使用基于 MiXeR 的框架对 34 种性状的外显子、内含子和基因间区域的遗传率进行了划分，并引入了一种基于似然的注释贡献评分，用于量化特定注释对遗传率的影响。外显子仅解释了少数遗传率，且其贡献随多基因性的增加而降低，从多基因性较低的躯体疾病和生物标志物中的平均 22% 下降到高度多基因性的精神和认知表型中的 13%。基因间区域的比例呈现相反趋势，而内含子比例则保持相对稳定。对更广泛的功能注释集的分析揭示了沿多基因性轴的系统性差异：高度多基因性的性状在比较基因组学和变异效应评分方面表现出更强的贡献，而多基因性较低的性状在启动子、转录和染色质注释方面表现出更强的贡献。总之，这些结果表明遗传率的功能划分随多基因性发生系统性变化，指出从近基因调控架构向由大量分散调控效应塑造的架构转变，是不同性状间多基因性差异的关键决定因素。

## Abstract
The genetic architecture of complex traits spans a continuum of polygenicity, yet it remains unclear how differences in polygenicity relate to the functional localization of SNP heritability across the genome. We use a MiXeR-based framework to partition heritability across exonic, intronic, and intergenic regions for 34 traits and introduce a likelihood-based annotation contribution score that quantifies annotation-specific impact on heritability. Exons explain a minority of heritability, and their contribution decreases with increasing polygenicity, from an average of 22% in less polygenic somatic diseases and biomarkers to 13% in highly polygenic psychiatric and cognitive phenotypes. Intergenic fractions show the opposite trend, whereas intronic fractions remain relatively stable. Analysis of a broader set of functional annotations reveals systematic differences along the polygenicity axis: highly polygenic traits show stronger contributions from comparative genomics and variant-effect scores, whereas less polygenic traits show stronger contributions in promoter, transcription, and chromatin annotations. Together, these results indicate that the functional partitioning of heritability systematically varies with polygenicity, pointing to a shift from gene-proximal regulatory architectures to architectures shaped by numerous dispersed regulatory effects as a key determinant of differences in polygenicity across traits.

---

## 论文详细总结（自动生成）

这是一份关于论文《Beyond Exons: Linking Noncoding Heritability and Polygenicity across Complex Human Traits and Disorders》的结构化深入总结：

### 1. 核心问题与整体含义
*   **研究动机**：复杂人类性状在多基因性（受影响变异的数量）上存在巨大差异，但这种差异如何反映在基因组的功能定位（如外显子 vs. 非编码区）上尚不清楚。
*   **核心问题**：论文旨在探究遗传率（Heritability）在基因组不同功能分区（外显子、内含子、基因间区）的分布，是否随性状的多基因性程度而发生系统性偏移。
*   **整体含义**：研究揭示了复杂性状遗传架构的一个基本规律：从“基因近端调控”到“分散的远端调控”的转变，是决定性状多基因性差异的关键。

### 2. 方法论
*   **核心思想**：基于 **MiXeR** 框架（一种基于似然函数的混合模型），通过 GWAS 汇总统计量（Summary Statistics）来估计不同功能注释对遗传率的贡献。
*   **关键技术细节**：
    *   **模型构建**：将表型变异建模为加性遗传效应和残差变异。SNP 效应大小的方差被设定为依赖于功能注释的参数。
    *   **ACS（注释贡献评分）**：论文引入了 ACS 指标，通过比较“全模型”（包含所有注释）与“部分模型”（仅包含特定注释）相对于“核心模型”（无注释）的对数似然增益，量化特定注释对遗传架构的相对贡献。
    *   **功能分区**：将基因组划分为外显子（Exons）、内含子（Introns）和基因间区域（IGRs），并使用了包含 74 个功能注释的面板（基于 baseline-LD v2.3）。
*   **算法流程**：利用最大似然估计（MLE）推导模型参数，同时考虑连锁不平衡（LD）结构和样本重叠。

### 3. 实验设计
*   **数据集**：初始收集了 70 种性状的 GWAS 汇总数据，经过遗传相关性（$r_g < 0.3$）聚类和遗传率筛选，最终保留 **34 种代表性性状**。
*   **涵盖类别**：精神疾病（如精神分裂症）、认知能力、躯体疾病（如 2 型糖尿病）、生物标志物（如脂质、血细胞计数）及人体测量指标（如身高）。
*   **Benchmark 与对比方法**：
    *   对比了 **sLDSC**（分层连锁不平衡得分回归）和 **sLD4M**。
    *   使用了 **1000 Genomes Phase 3** 欧洲裔样本作为 LD 参考面板。

### 4. 资源与算力
*   **算力说明**：论文提到计算资源由挪威的 **Services for Sensitive Data (TSD)** 和 **Sigma2**（国家高性能计算基础设施）提供。
*   **具体细节**：文中**未明确说明**具体的 GPU/CPU 型号、核心数量或具体的训练/推理总时长。

### 5. 实验数量与充分性
*   **实验规模**：对 34 种性状进行了系统性的遗传率分区分析，并对 74 个功能注释进行了 ACS 评分计算。
*   **充分性验证**：
    *   **敏感性分析**：对比了无穷小模型（Infinitesimal）与非无穷小模型的估计结果，两者高度一致（Pearson $r=0.92$）。
    *   **方法一致性**：MiXeR 与 sLD4M 的多基因性估计相关性达 0.9。
    *   **外部验证**：通过加入 GWAS Catalog 注释轨道进行验证，结果符合预期。
*   **评价**：实验设计覆盖了广泛的表型谱，且通过多种统计模型的交叉验证，结果具有较高的客观性和说服力。

### 6. 主要结论与发现
*   **外显子贡献随多基因性下降**：在低多基因性性状（如生物标志物）中，外显子解释约 22% 的遗传率；而在高多基因性性状（如精神疾病）中，这一比例降至 13%。
*   **基因间区（IGR）的崛起**：随着多基因性增加，IGR 的遗传率占比显著上升，反映了远端调控效应的增加。
*   **内含子的稳定性**：无论多基因性如何变化，内含子始终解释约 50% 的遗传率，是遗传效应的主要载体。
*   **功能域的偏移**：高多基因性性状在“比较基因组学”（进化保守区）和“变异效应评分”上表现出更强的信号；而低多基因性性状则在启动子和转录活跃区域表现更强。

### 7. 优点
*   **指标创新**：ACS 评分有效地平衡了“注释大小”与“富集强度”，避免了 sLDSC 中小注释因极高富集率而产生的误导性排名。
*   **系统性视角**：首次在多性状维度上建立了“多基因性—功能定位”的关联模型，超越了单一性状的描述。
*   **生物学解释力强**：成功解释了为什么精神疾病等高级认知性状比基础生理性状更难通过外显子测序（WES）捕捉到全部遗传效应。

### 8. 不足与局限
*   **族群偏差**：研究主要基于**欧洲裔**参考面板和 GWAS 数据，其结论在非欧裔人群中的普适性有待验证。
*   **注释完整性**：功能注释面板虽然广泛，但仍可能遗漏某些特定组织或发育阶段的稀有调控元件；且对 X 染色体的覆盖不足。
*   **模型假设**：MiXeR 框架依赖于特定的先验分布假设（如加性效应、混合高斯分布），虽然经过敏感性测试，但在极端遗传架构下可能存在偏差。
*   **因果性限制**：研究基于 SNP 关联，无法直接证明非编码区变异的直接生物学因果机制。

（完）
