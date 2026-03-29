---
title: Genetic architectures of brain-related traits are shaped by strong selective constraints
title_zh: 大脑相关性状的遗传架构受强选择约束的影响
authors: "Zhu, H., Simons, Y. B., Spence, J. P., Sella, G., Pritchard, J. K."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.22.713538v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 精神疾病和大脑相关性状的GWAS研究
tldr: 本研究探讨了为何精神疾病及中枢神经系统（CNS）相关性状在GWAS中的关联强度普遍较弱。研究者通过匹配“有效样本量”的方法，排除了统计效力差异的干扰，对比了不同性状的遗传架构。结果表明，CNS相关性状具有更大的突变靶标规模，且相关变异受到更强的自然选择约束。这一发现揭示了组织特异性的选择压力是塑造复杂性状遗传架构的关键因素，为理解疾病异质性提供了新视角。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713538-v1/fig-001.webp\", \"caption\": \"Figure 2: Traits with functional enrichment in the CNS share similar GWAS hit patterns. A) Functional enrichment analyses with S-LDSC [26, 27] on selected traits. Each row consists of 220 cell types from 10 categories, colored by −log10(p) for the coefficient τ if significant after Bonferroni correction. The gradient scale is bounded above at 15. Results on all other traits are in Figures S4 to S6. B) Contrasting the GWAS hits for psychiatric disorders with those of nine other complex diseases. The full list of diseases can be found in Supplementary Table 2. C) Contrasting the GWAS hits for behavioral-cognitive traits with those of 144 other quantitative traits. The full list of quantitative traits is in Supplementary Table 1. D) GWAS hits for traits enriched for the CNS have higher median MAF and lower median |z|-score. Each trait included in this study is colored by the combined p-value for CNS enrichment, computed following the aggregate Cauchy association test (ACAT) [41] (Methods). The points corresponding to the 36 body composition–related traits are outlined with black borders. ADHD: attention deficit hyperactivity disorder; BIP: bipolar disorder; MD: major depression. AFS: age first had sexual intercourse; DFP: duration to first press of snap-button in each round; FIS: fluid intelligence score; IMR: number of incorrect matches in round; NS: neuroticism score; TCR: time to complete round; TIM: mean time to correctly identify matches. BMI: body mass index.\", \"page\": 6, \"index\": 1, \"width\": 979, \"height\": 601}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713538-v1/fig-002.webp\", \"caption\": \"Figure 4: Stronger selection on brain-related variants and larger mutational target sizes for brain-related traits.\", \"page\": 11, \"index\": 2, \"width\": 976, \"height\": 681}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713538-v1/fig-003.webp\", \"caption\": \"Figure 6: Burden tests provide aligned evidence of stronger selection on CNS-relevant genes. A) Mean squared genic effects on brain-related versus non-brain-related quantitative traits, with genes grouped into 15 quantiles of shet estimates [58]. The estimated γ̂2 values are scaled so that the mean across all gene-trait pairs in the tenth bin equals one. All estimates are shown with a 95% confidence interval computed from the standard error. We bootstrapped genes at the trait level and showed the mean and 95% confidence intervals of the fitted LOESS curves. B) Comparing selection signals from gene-to-trait and variant-to-trait associations. ① Brain-relevant genes have a stronger distribution of constraint values than genes relevant to other traits. The two curves are hypothetical and are intended to illustrate the relationship between their modes. ② Brain-relevant variants have a stronger distribution of selection coefficients than variants relevant to other traits.\", \"page\": 14, \"index\": 3, \"width\": 976, \"height\": 362}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713538-v1/fig-004.webp\", \"caption\": \"Figure 5: Recovering the genetic architectures of brain-related traits through simulations. A) Simulation model for traits with varying mutational target sizes. We fixed f (s) to the shared distribution inferred from 151 quantitative traits as shown in Figure 4B. Colors in panels B and C correspond to the simulation settings shown in A. B) Larger L values lead to narrower distributions of GWAS hit |z|-scores. C) Nonlinear relationship between L and GWAS hit count. We ran additional simulations at finer increments of L and plotted them as gray dots. D) Simulation model for traits with varying distributions of selection coefficients. Colors in panels E and F correspond to the simulation settings shown in D. E) In the absence of GWAS ascertainment, variants simulated under stronger f (s) distributions tend to have lower MAF. F) After GWAS ascertainment (MAF > 1% and |Z| > 5.45), stronger f (s) simulations yield GWAS hits enriched for higher MAF. For each f (s) distribution, we ran 50 simulations, highlighted the median CDF curve of the MAF of simulated hits, and labeled the corresponding number of hits.\", \"page\": 13, \"index\": 4, \"width\": 976, \"height\": 626}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713538-v1/fig-005.webp\", \"caption\": \"Figure 1: Schizophrenia GWAS hits narrowly exceed the significance threshold. A) Manhattan plots for three example traits. The y-axes of all three plots are restricted to the range [0, 80]. Significant associations beyond this range are labeled with the most significant p-value. Independent hits are obtained from GCTA-COJO [38], and hits with MAF below 1%, in the HLA region, or of low imputation quality are excluded (Methods). B) Cumulative distributions of COJO hit absolute z-scores. C) Cumulative distributions of COJO hit MAF. CAD: coronary artery disease; SCZ: schizophrenia.\", \"page\": 4, \"index\": 5, \"width\": 976, \"height\": 591}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713538-v1/fig-006.webp\", \"caption\": \"Figure 3: Calibrating GWAS statistical power between quantitative traits and binary traits. A) Binarizing LDL with varying prevalence in the upper tail. LDL levels were measured in unrelated White British individuals from the UK Biobank. The original phenotypic distribution was standardized using rank-based inverse normal transformation. B) Derivation of the sample size needed on the liability scale to reach equivalent power of a case-control GWAS. MAF is denoted by p. We transferred effect sizes from log odds ratio scale (ζ) to continuous scale (β) using the liability threshold model. For details, see Supplementary Notes. C) Deflation of LDL GWAS hit z-scores after binarizing. Different colors reflect the threshold used to binarize traits, as shown in panel A. Solid lines represent predicted slopes, and dashed lines indicate fitted slopes. Gray lines in the background are y = 0, x = 0 and y = ±x. D) Deflation of LDL GWAS hit z-scores after downsampling to matched sample sizes. Color choices, line styles, and background lines are identical to those in panel C. E) Reducing coronary artery disease and LDL GWAS power to match with the current effective sample size of schizophrenia GWAS, N′ = 192,273 (Methods).\", \"page\": 9, \"index\": 6, \"width\": 976, \"height\": 643}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713538-v1/fig-007.webp\", \"caption\": \"Figure 7: Explaining past and predicting future disease GWAS discoveries. A) Expected disease GWAS outcomes as a function of sample size, computed using the inferred f (s) for brain-related and non-brain-related traits (Figure 4C), along with their corresponding estimates of h2 and L as shown in Figure 4D. We evaluated a range of sample sizes across 35 grid points and plotted the curves using the median values across 10 simulations at each point. Our inference was based on the current GWAS (see Supplementary Table 2). For reference, we overlaid the reported number of hits and sample sizes from selected earlier GWAS (IBD [73]; BrCa [74]; T2D [75, 76]; CAD [77]; MD [61, 63–66]; and SCZ [78]). B) Inferred h2/L estimates used in the simulations. C) Inferred L estimates used in the simulations.\", \"page\": 16, \"index\": 7, \"width\": 976, \"height\": 358}]"
motivation: 旨在解释精神疾病等中枢神经系统相关性状在基因组关联分析中关联强度较低的生物学本质及其背后的选择压力。
method: 采用二值化定量性状并匹配责任量表上的“有效样本量”的方法，实现了不同统计效力性状间遗传架构的稳健比较。
result: 研究证实CNS富集性状拥有更广泛的突变靶标，且其贡献变异和基因经历了比其他组织相关性状更强烈的自然选择。
conclusion: 复杂性状的遗传架构是由其介导的组织（如脑组织）所面临的选择约束强度所塑造的，反映了不同性状与适应度的相关性。
---

## 摘要
全基因组关联研究（GWAS）已鉴定出数百个与精神疾病显著相关的位点，但与具有相似命中数量的其他人类复杂性状相比，这些关联的强度仍然较弱。这种模式是反映了统计偏差还是真实的生物学差异——如果是后者，其背后的机制是什么——目前尚不清楚。除了精神疾病外，我们发现其他在中枢神经系统（CNS）中具有功能富集的性状（无论是二元性状还是定量性状）也具有相似的遗传架构，其特征是 GWAS 命中位点的统计显著性有限且等位基因频率通常较高。为了稳健地比较 GWAS 统计效力不同的性状，我们展示了将定量性状二元化如何降低效力。这种效力损失可以通过易感性量表（liability scale）上匹配的“有效样本量”来复现。在匹配“有效样本量”后，我们表明 CNS 富集性状具有较大的突变靶标规模，其贡献变异和基因比其他性状经历更强的选择。我们的研究揭示了疾病之间的异质性，并为更有效地捕捉适应度相关过程的性状提供了见解。更广泛地说，我们的结果表明，复杂性状的遗传架构是由介导这些性状的组织所塑造的。

## Abstract
Genome-wide association studies (GWAS) have identified hundreds of significant loci for psychiatric disorders, yet the strength of these associations remains modest compared to other human complex traits with similar numbers of hits. Whether this pattern reflects statistical artifacts or real biological differences -- and, if the latter, what underlies it -- remains unclear. In addition to psychiatric disorders, we find that other traits with functional enrichment in the central nervous system (CNS), whether binary or quantitative, also share similar genetic architectures, characterized by GWAS hits of limited statistical significance and generally higher allele frequencies. To robustly compare traits that differ in GWAS statistical power, we demonstrate how binarizing a quantitative trait reduces power. This loss of power can be replicated by a matched "effective sample size" on the liability scale. After matching "effective sample sizes", we show that CNS-enriched traits have large mutational target sizes, with contributing variants and genes experiencing stronger selection than those for other traits. Our findings reveal heterogeneity among diseases and provide insights into traits that more effectively capture fitness-relevant processes. More broadly, our results suggest that the genetic architectures of complex traits are shaped by the tissues through which these traits are mediated.

---

## 论文详细总结（自动生成）

### 论文总结：大脑相关性状的遗传架构受强选择约束的影响

#### 1. 论文的核心问题与整体含义（研究动机和背景）
全基因组关联研究（GWAS）在精神疾病（如精神分裂症）中虽然发现了大量显著位点，但这些位点的关联强度（Z-score）普遍较低，且等位基因频率（MAF）偏高，这与冠心病或身高类性状截然不同。研究的核心问题是：**这种现象究竟是由于统计效力不足导致的偏差，还是反映了某种深层的生物学机制？** 论文旨在探讨中枢神经系统（CNS）相关性状的遗传架构是否受到独特的自然选择压力和突变靶标规模的影响。

#### 2. 论文提出的方法论
*   **核心思想**：通过消除二元性状（疾病）与定量性状之间统计效力的不平衡，在同一基准下比较不同组织相关性状的遗传特征。
*   **关键技术细节**：
    *   **有效样本量匹配（Effective Sample Size, $N_{eff}$）**：利用易感性阈值模型（Liability Threshold Model），将二元性状的统计效力转化到连续变量量表上。
    *   **定量性状二值化实验**：以低密度脂蛋白（LDL）为例，人为将其转化为二元性状，验证了二值化会导致显著性（Z-score）大幅下降，从而证明了直接比较二元和定量性状的误区。
    *   **遗传架构建模**：利用 S-LDSC 等工具评估功能富集，并结合突变靶标规模（$L$）和选择系数分布 $f(s)$ 的模型，推断不同性状背后的演化压力。
    *   **基因负担测试（Burden Tests）**：在基因水平上验证选择压力，排除位点水平分析的潜在偏差。

#### 3. 实验设计
*   **数据集**：
    *   **UK Biobank (UKB)**：包含约 50 万人的基因型和表型数据，涵盖 151 个定量性状。
    *   **外部 GWAS 汇总数据**：包括精神分裂症（SCZ）、双相情感障碍（BIP）、重度抑郁（MD）、冠心病（CAD）、2 型糖尿病（T2D）等大规模研究数据。
*   **Benchmark（基准）**：以非 CNS 富集的性状（如身体成分、心血管指标）作为对照组。
*   **对比方法**：对比了 CNS 富集性状（行为、认知、精神疾病）与非 CNS 富集性状在 Z-score 分布、MAF 分布、遗传力（$h^2$）以及突变靶标规模上的差异。

#### 4. 资源与算力
论文中**未明确说明**具体的硬件配置（如 GPU 型号或数量）。考虑到此类研究通常涉及大规模基因组数据的统计建模和模拟，通常依赖于高性能计算集群（HPC）进行 CPU 并行计算，而非重度依赖 GPU 训练。

#### 5. 实验数量与充分性
*   **实验规模**：分析了 151 个定量性状和多种重大疾病的 GWAS 数据，涵盖了数十万至上百万样本。
*   **充分性与客观性**：
    *   进行了大量的**模拟实验**（图 4 和图 5），验证了突变靶标规模 $L$ 和选择强度对 GWAS 结果分布的影响。
    *   通过**消融式对比**（如 LDL 的二值化处理），排除了统计方法本身带来的假象。
    *   使用了**交叉验证**，从变异位点水平和基因水平（Burden Test）两个维度得出了一致的结论，实验设计非常严谨且公平。

#### 6. 论文的主要结论与发现
*   **CNS 性状的独特架构**：大脑相关性状（精神疾病、认知能力等）的 GWAS 命中位点普遍呈现“低显著性、高频率”的特征。
*   **强选择约束**：与非 CNS 性状相比，影响大脑功能的变异受到更强烈的负向自然选择（Negative Selection）。这意味着高效应值的变异会被迅速从群体中剔除，导致留下的关联位点效应微弱。
*   **大突变靶标**：大脑相关性状拥有更大的突变靶标规模（$L$），即基因组中有更多区域的变异能影响这些性状，这解释了为何其多基因性（Polygenicity）极高。
*   **组织特异性**：复杂性状的遗传架构很大程度上是由其介导的组织（如 CNS）所面临的演化约束塑造的。

#### 7. 优点
*   **视角新颖**：从演化生物学和群体遗传学的角度解释了精神疾病 GWAS 的“瓶颈”问题。
*   **方法论严谨**：通过 $N_{eff}$ 解决了长期以来二元性状与定量性状难以直接比较的难题。
*   **解释力强**：不仅解释了现有数据，还对未来增加样本量后 GWAS 能发现多少新位点给出了预测模型。

#### 8. 不足与局限
*   **模型假设**：研究高度依赖易感性阈值模型和特定的选择模型（如 $f(s)$ 分布），若这些基础假设在某些极端情况下不成立，结论可能受限。
*   **常见变异局限性**：主要基于 GWAS 捕捉到的常见变异（Common Variants），对于罕见变异（Rare Variants）在这些性状中的贡献虽有提及，但未进行同等深度的实证分析。
*   **环境因素**：虽然探讨了遗传架构，但对于环境因素与遗传选择之间的交互作用（GxE）讨论较少。

（完）
