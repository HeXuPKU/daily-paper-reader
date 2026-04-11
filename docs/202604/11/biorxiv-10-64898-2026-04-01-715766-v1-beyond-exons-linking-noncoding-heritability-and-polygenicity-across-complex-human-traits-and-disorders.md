---
title: "Beyond Exons: Linking Noncoding Heritability and Polygenicity across Complex Human Traits and Disorders"
title_zh: 超越外显子：关联复杂人类性状与疾病中的非编码遗传率与多基因性
authors: "Fuhrer, J., Shadrin, A. A., Hughes, T., Parker, N., Hindley, G., Frei, E., Nguyen, D., Smeland, O. B., Djurovic, S., Andreassen, O., Dale, A., Frei, O."
date: 2026-04-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.01.715766v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 跨基因组注释划分遗传力和多基因性
tldr: 本研究探讨了复杂性状的多基因性与遗传力在基因组功能区域分布之间的关系。通过对34种性状进行MiXeR框架分析，研究发现外显子对遗传力的贡献随多基因性增加而下降，而基因间区贡献则上升。高多基因性性状更多受分散的调控效应影响，而低多基因性性状则更依赖近端调控。这一发现揭示了不同性状遗传架构差异的生物学基础。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-01-715766-v1/fig-001.webp\", \"caption\": \"Figure 3: Contribution of individual functional annotations relative to the full model with 74 annotations. Phenotypes are ordered by their polygenicity remaining after pruning with 𝑟g=0.3, favoring phenotypes with higher heritability. Annotations are sorted by their Euclidean distance. On the left, next to relative numbers of nucleotides (genome, exon, intron, intergenic), the Spearman rank correlation value between ACS and polygenicity across phenotypes is indicated. The symbols following each functional annotation on the right indicate the significance after Bonferroni correction for the Spearman correlation (significance: ***: p<0.001, **: p<0.01, *: p <0.05, n.s.: p≥0.05).\", \"page\": 7, \"index\": 1, \"width\": 970, \"height\": 1011}]"
motivation: 旨在阐明复杂性状的多基因性差异如何与单核苷酸多态性（SNP）遗传力的基因组功能定位相关联。
method: 采用基于MiXeR的框架对34种性状的外显子、内含子和基因间区遗传力进行划分，并引入似然贡献评分量化功能注释的影响。
result: 发现外显子贡献随多基因性增加而减少，而基因间区贡献增加，且高多基因性性状在比较基因组学和变异效应评分上表现出更强的贡献。
conclusion: 遗传力的功能划分随多基因性系统性变化，表明从基因近端调控向广泛分散调控效应的转变是决定性状多基因性差异的关键因素。
---

## 摘要
复杂性状的遗传架构跨越了一个多基因性的连续谱，但目前尚不清楚多基因性的差异如何与全基因组范围内 SNP 遗传率的功能定位相关联。我们使用基于 MiXeR 的框架对 34 种性状的外显子、内含子和基因间区域的遗传率进行了划分，并引入了一种基于似然的注释贡献评分，用于量化特定注释对遗传率的影响。外显子仅解释了少数遗传率，且其贡献随多基因性的增加而降低，从多基因性较低的躯体疾病和生物标志物中的平均 22% 下降到高度多基因性的精神和认知表型中的 13%。基因间区域的比例呈现相反趋势，而内含子比例保持相对稳定。对更广泛的功能注释集的分析揭示了沿多基因性轴的系统性差异：高度多基因性性状在比较基因组学和变异效应评分方面表现出更强的贡献，而多基因性较低的性状在启动子、转录和染色质注释方面表现出更强的贡献。总之，这些结果表明遗传率的功能划分随多基因性发生系统性变化，指出从近基因调控架构向由大量分散调控效应塑造的架构转变，是不同性状间多基因性差异的关键决定因素。

## Abstract
The genetic architecture of complex traits spans a continuum of polygenicity, yet it remains unclear how differences in polygenicity relate to the functional localization of SNP heritability across the genome. We use a MiXeR-based framework to partition heritability across exonic, intronic, and intergenic regions for 34 traits and introduce a likelihood-based annotation contribution score that quantifies annotation-specific impact on heritability. Exons explain a minority of heritability, and their contribution decreases with increasing polygenicity, from an average of 22% in less polygenic somatic diseases and biomarkers to 13% in highly polygenic psychiatric and cognitive phenotypes. Intergenic fractions show the opposite trend, whereas intronic fractions remain relatively stable. Analysis of a broader set of functional annotations reveals systematic differences along the polygenicity axis: highly polygenic traits show stronger contributions from comparative genomics and variant-effect scores, whereas less polygenic traits show stronger contributions in promoter, transcription, and chromatin annotations. Together, these results indicate that the functional partitioning of heritability systematically varies with polygenicity, pointing to a shift from gene-proximal regulatory architectures to architectures shaped by numerous dispersed regulatory effects as a key determinant of differences in polygenicity across traits.

---

## 论文详细总结（自动生成）

这篇论文深入探讨了人类复杂性状的遗传架构，特别是多基因性（Polygenicity）与遗传力在基因组功能分区（如外显子、内含子、基因间区）分布之间的系统性联系。以下是对该论文的结构化总结：

### 1. 核心问题与研究动机
*   **核心问题**：不同人类性状在多基因性（即影响性状的变异数量）上存在巨大差异，但这种差异是否反映在遗传力在基因组不同功能区域（编码区 vs. 非编码区）的分布上？
*   **背景**：虽然已知非编码区贡献了大部分遗传力，但过去的研究多侧重于单一性状或特定注释的富集分析，缺乏跨性状的、将多基因性与功能定位直接关联的系统性量化研究。

### 2. 方法论
*   **核心框架**：基于 **MiXeR** 似然框架。MiXeR 能够利用 GWAS 汇总统计数据（Summary Statistics）估算性状的多基因性（$\pi$）和可发现性。
*   **关键技术：注释贡献评分 (ACS)**：
    *   论文引入了 ACS 指标，用于量化特定功能注释对模型拟合优度的提升。
    *   **计算逻辑**：ACS 等于“单一注释模型相对于基础模型的对数似然增量”除以“全注释模型相对于基础模型的总增量”。
    *   **优势**：相比传统的富集倍数（Fold Enrichment），ACS 综合考虑了注释区域的大小和效应强度的集中度，避免了极小注释区域产生误导性的高富集率。
*   **功能分区**：将基因组划分为外显子（Exons）、内含子（Introns）和基因间区（IGRs），并使用了包含 74 个功能注释的面板（基于 baseline-LD v2.3，涵盖进化保守性、变异效应预测、染色质状态等）。

### 3. 实验设计
*   **数据集**：初始收集了 70 个性状的 GWAS 汇总数据，通过遗传相关性（$r_g < 0.3$）聚类和遗传力筛选，最终保留了 **34 个独立性状**。
*   **性状类别**：涵盖精神疾病（如精神分裂症）、认知性状、躯体疾病（如糖尿病）、生物标志物（如脂质、血细胞计数）和人体测量学指标（如身高）。
*   **对比方法（Benchmark）**：
    *   使用 **sLDSC**（分层连锁不平衡得分回归）和 **sLD4M** 作为验证基准。
    *   进行了敏感性分析，对比了无穷小模型（Infinitesimal）与非无穷小模型的估算结果。

### 4. 资源与算力
*   **算力说明**：论文提到使用了挪威的敏感数据服务（TSD）和国家高性能计算基础设施（UNINETT Sigma2）。
*   **具体细节**：文中未明确列出具体的 GPU/CPU 核心数量或具体的训练时长，但考虑到处理 70+ 性状的大规模 GWAS 似然估计，这属于计算密集型统计分析。

### 5. 实验数量与充分性
*   **实验规模**：对 34 个性状进行了全基因组范围的功能划分，并对 74 个功能注释逐一计算了 ACS。
*   **充分性**：
    *   **多维度验证**：通过 Spearman 相关性分析、聚类分析和回归模型验证了多基因性与遗传力分区的关系。
    *   **稳健性**：进行了多项敏感性分析（如不同模型假设的对比、细胞类型特异性分析），实验设计严谨，结果具有高度的一致性。

### 6. 主要结论与发现
*   **外显子贡献随多基因性下降**：在低多基因性性状（如生物标志物）中，外显子解释约 22% 的遗传力；而在高多基因性性状（如精神疾病）中，这一比例降至 13%。
*   **基因间区贡献随多基因性上升**：多基因性越强，遗传力越倾向于分布在远离基因的调控区域。
*   **内含子贡献保持稳定**：无论多基因性如何变化，内含子始终解释约 50% 的遗传力，反映了其作为基因近端调控和剪接元件的基准作用。
*   **功能域的系统性差异**：
    *   **高多基因性性状**：更多地加载在进化保守性评分（Comparative Genomics）和变异效应预测（Variant Effect）上。
    *   **低多基因性性状**：更多地集中在启动子（Promoter）、转录区域和特定的染色质状态上。
*   **生物学启示**：从“基因近端调控”向“广泛分散的远端调控”转变是性状多基因性增加的核心特征。

### 7. 优点
*   **理论创新**：首次系统性地建立了多基因性与基因组功能解剖结构之间的定量联系。
*   **指标优化**：ACS 评分提供了一个比富集倍数更客观的视角来衡量功能注释的相对重要性。
*   **分类清晰**：将复杂性状划分为“基础生理性状”（近端调控）和“高级认知/精神性状”（分散调控），具有很强的生物学解释力。

### 8. 不足与局限
*   **族群偏差**：研究主要基于欧洲裔参考面板（1000 Genomes Phase 3），结果在其他族群中的普适性有待验证。
*   **注释覆盖**：虽然使用了 74 个注释，但仍可能遗漏某些精细的细胞类型特异性或发育阶段特异性的调控元件。
*   **X 染色体缺失**：分析主要集中在常染色体，未涵盖 X 染色体的贡献。
*   **因果推断限制**：基于 GWAS 汇总数据的统计模型虽然能揭示关联，但无法直接证明分子层面的因果机制。

（完）
