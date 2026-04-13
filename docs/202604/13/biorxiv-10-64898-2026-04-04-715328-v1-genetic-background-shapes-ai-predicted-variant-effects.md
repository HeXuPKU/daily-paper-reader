---
title: Genetic background shapes AI-predicted variant effects
title_zh: 遗传背景塑造 AI 预测的变异效应
authors: "Schilder, B. M., Liu, Z., Desmarais, J. J., Laub, D., Rahimi, F., Sethi, P., Pereira, L. A., Sun, M. M., Kinney, J. B., McCandlish, D. M., Zhou, J., Koo, P. K."
date: 2026-04-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.04.715328v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 由遗传背景塑造的 AI 预测变异效应
tldr: 本研究针对传统变异预测忽略遗传多样性的局限，提出了个性化变异效应预测（pVEP）框架。通过在数千个全球多样化基因组背景下运行蛋白质结构、剪接和非编码调节的深度学习模型，研究发现遗传背景会显著改变临床变异的预测结果。同一变异在不同个体中可能表现出截然不同的致病性，揭示了分子机制层面的异质性，强调了在临床解释中考虑个性化基因组背景对提升精准医疗公平性和准确性的重要性。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-04-715328-v1/fig-001.webp\", \"caption\": \"Figure 4. pVEP reveals background-dependent predicted effects for clinical splicing variants. a, Filled density plot of all SpliceAI reference-based and personalized VEP scores per clinical variant (x-axis: 0 = no predicted splice disruption, 1 = complete disruption), stratified by ClinVar pathogenicity (n = 8.5 k: 2.6 k benign, 2.5 k VUS, 3.3 k pathogenic). The red vertical line indicates spliceogenicity threshold. b, Bar plot of pVEP scores grouped by ClinVar pathogenicity label, showing pathogenic variants and VUS have high predicted spliceogenicity than benign ones (two-sided Mann-Whitney U test: U = 2.16×106 – 2.72×106, p = 2.03×10−114 to 2.51×10−243). ns: p≥ .05; **: p < 0.01; ****: p < 0.0001). c, Bar plot of counts of SpliceAI-predicted variant effect classes (donor/acceptor gain or loss), colored by clinical significance. d, Bar plot of Shannon entropy of SpliceAI-predicted effect classes across haplotypes, grouped by pathogenicity labels. Pathogenic variants and VUS have significantly higher entropy than benign variants (two-sided independent-samples t-tests: t = 5.52–14.35, p = 6.2×10−46 to 3.6×10−8) e, Boxplot of surrogate model marginal effects per clinical variant, colored by ClinVar significance, showing pathogenic variants and VUS have higher marginal effects than benign variants (two-sided Mann-Whitney U tests: p < 0.0001). f, Bar plot of clinical variant marginals grouped by whether the clinical variant overlaps a splicing-relevant region: 3′ splice-site (ss), 5′ss, canonical, or intronic proximal. Variants within canonical and intronic proximal 3′/5′ss displayed greater effects than others (two-sided Mann-Whitney U tests: p < 0.001). g, VEP score distributions across haplotypes for chr17:2981247 A>G (RAP1GAP2, VUS) and chr17:43115788 G>C (BRCA1, pathogenic). Upper panels show log-scale haplotype frequency with spliceogenicity (red) and reference (grey) thresholds marked. Lower panels show superpopulation composition per VEP score bin. h, Attribution maps for four genomic context around BRCA1 chr17:43115788 G>C: reference and HG03691 haplotype, each with and without the clinical variant. Attribution maps given by Integrated Gradients highlight sequence-level determinants of 3′ splice-site choice. The clinical variant is highlighted in purple and the compensatory background variant in green. This variant induced a strong splicing change in all haplotypes (max ∆ = 0.996) except for the HG03691-specific haplotype (max ∆ = 0.0195). 6/17\", \"page\": 6, \"index\": 1, \"width\": 1038, \"height\": 1081}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-04-715328-v1/fig-002.webp\", \"caption\": \"Figure 1. Overview of the pVEP framework and variant datasets. a, Schematic of the pVEP framework. For each clinical variant, model predictions are computed across reference and personalized background sequences with (MUT) and without (WT) the clinical variant introduced, yielding a distribution of predicted variant effects with the reference-based VEP score (V EPref) marked for comparison. b, Bar chart of individuals per ancestral superpopulation across the 1000 Genomes Project and Human Genome Diversity Project (n = 3,819 individuals). c, Histogram of unique haplotypes per protein across all transcripts analyzed (n = 2,847 transcripts). d, Histograms of background variants per haplotype for protein sequences in ProteinGym (top, n = 132,721 unique haplotypes), 10 kb DNA windows centered on splicing variants in SpliceVarDB (middle, n = 64,846,620 unique haplotypes), and 524 kb DNA windows centered on 5′/3′ UTR variants from ClinVar (bottom, n = 105,182,898 unique haplotypes). Counts <10 are binned for visualization purposes. e, Schematics of the three clinical variant classes explored and bar plot of variant counts per class (missense: n = 62,727, splicing: n = 8,490, and UTR: n = 13,771), colored by ClinVar pathogenicity label.\", \"page\": 2, \"index\": 2, \"width\": 1017, \"height\": 763}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-04-715328-v1/fig-003.webp\", \"caption\": \"Figure 2. pVEP reveals heterogeneous predicted responses to clinical missense variants. a, Filled density plot of ESM2-650M reference-based and personalized VEP scores across all missense variants, stratified by ClinVar pathogenicity (n = 62,727: ∼8,600 benign, ∼19,500 likely benign, ∼19,300 likely pathogenic, and ∼8,900 pathogenic variants). Negative values (rightwards) indicate more pathogenic effects. Vertical dashed line (red) indicates benign/pathogenic threshold. b, Stacked bar plot showing the percentile bin (fill color) of reference-based VEP score (V EPref) relative to the full distribution average (V EPmean) at each V EPmean decile. A greater proportion of red bars indicates V EPref tends to overestimate pathogenicity, whereas a greater proportion of blue bars indicates underestimation. The gray horizontal dashed line demarcates 50% of the variants in that VEP Decile. c, Stacked barplot showing the proportion of clinical variants whose ESM2-650M VEP scores follow a normal distribution (D’Agostino-Pearson omnibus test, FDR > 0.05), non-normal distribution (FDR < 0.05,) or could not be tested (n < 20 protein haplotypes), grouped by ClinVar pathogenicity. d, Bar plot of the estimated number of modes per clinical variant VEP score distribution, inferred from a variational Bayes Gaussian mixture model. e, Haplotype-level VEP score distributions for three missense variants with high inter-haplotype variability: TH 167V>E (n = 71 haplotypes, top), COX10 225P>L (n = 46, middle), and ALDH5A1 179I>N (n = 55, bottom). Vertical dashed lines indicate V EPmean (gold), V EPref (grey), and the empirically inferred benign/pathogenic boundary (red). f, Haplotype-level ESM2-650M VEP score distribution for VHL 121C>F (n = 15 haplotypes). Vertical dashed lines indicate V EPmean (gold) and V EPref (grey). Bar plots below show the proportion of individuals from each ancestry per VEP score bin. AFR=African, AMR=Admixed American, EAS=East Asian, EUR=European, SAS=South Asian.\", \"page\": 3, \"index\": 3, \"width\": 1010, \"height\": 666}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-04-715328-v1/fig-004.webp\", \"caption\": \"Figure 5. pVEP reveals background-dependent predicted effects for clinical UTR variants. a, Filled density plot of Flashzoi average pVEP scores (V EPmean) per clinical variant, stratified by ClinVar pathogenicity. Vertical dashed lines indicate the reference-based VEP score (V EPref; grey) and the empirically inferred benign/pathogenic boundary (red). b, Bar plot of V EPmean grouped by UTR type (5′/3′) and ClinVar pathogenicity label. Pathogenic-labeled variants had significantly greater predicted pathogenicity than benign variants (two-sided Mann–Whitney U tests: 3′ UTR benign vs. pathogenic, U = 4.42×105, p = 1.3×10−7; 5′ UTR, U = 4.65×105, p = 0.016). ns: p≥ .05; ****: p≤ 0.0001. c, Bar plot of variability (median absolute deviation) of Flashzoi VEP score distributions across haplotypes, grouped by UTR type and ClinVar pathogenicity label. Benign variants within 5′ UTR regions showed greater variability in predicted effects than those witihn 3′ regions (two-sided Mann-Whitney U test: p < 0.0001). d, Haplotype-level VEP score distributions for the four clinical UTR variants with the greatest variability across haplotypes. Vertical dashed lines indicate V EPmean (gold), V EPref (grey), and the empirically inferred benign/pathogenic boundary (red), derived from gene-specific variational Bayes Gaussian mixture models. Below each histogram, bar plots show the proportion of haplotypes from each ancestry per VEP bin.\", \"page\": 8, \"index\": 4, \"width\": 765, \"height\": 677}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-04-715328-v1/fig-005.webp\", \"caption\": \"Figure 3. Background variants modify the effects of BRCA1 clinical variants in close structural proximity. a, Surrogate modeling takes as input a binary matrix of background variant presence across haplotypes (left) and predicts continuous clinical variant VEP scores (right), yielding a variant sensitization map of inferred joint effects (center). b, Predicted 3D structure of BRCA1 from AlphaFold2 (AF2). c, Variant sensitization map (inferred from ESM2 VEP scores) overlaid on the AF2-predicted BRCA1 distance map, showing all 652 significant non-additive interactions (center heatmap; p < 0.05). Red boxes indicate variant pairs where a background variant (y-axis) increases predicted pathogenicity of a clinical variant (x-axis). Pathogenic clinical variants (top scatter/density) are concentrated in the RING and BRCT domains (grey vertical bars), recapitulated by surrogate model marginal effects for clinical (bottom) and background variants (right). d, 3D structural visualization of interaction pairs: background variant 1706G>A with clinical variants 1684T>A and 1687V>I (left), and 1729L>Q with 1722S>F (FDR = 1.43×10−13; right). Spheres indicate clinical variants colored by V EPmean (red: pathogenic, blue: benign); ribbon color and dashed lines indicate the background variant’s effect on pathogenicity (red: ↑, blue: ↓, grey: no data). Labels indicate reference amino acid and residue position. e, Zoomed-in AF2 distance maps for the four variant pairs with the strongest interaction coefficients in BRCA1. f, Boxplot of clinical variant marginals grouped by ClinVar pathogenicity; pathogenic variants have higher marginals than benign ones (two-sided Mann–Whitney U tests: U = 1355–2302, p = 1.33×10−21 to 8.33×10−13, nbenign/likely benign = 137–167, npathogenic/likely pathogenic = 57–95; ns: p≥ .05; ****: p≤ 0.0001). g, Observed-to-expected enrichment of AF2 residue contacts among variant pairs at each interaction threshold, with variant pair counts on the secondary axis. h, Residue-by-residue heatmap showing the proportion of haplotypes (n = 126) gaining (blue) or losing (red) AF2-predicted contacts (< 8 Å) relative to the reference. i, Bar plot of reference contacts gained (blue) or lost (red) in population-weighted contact maps stratified by superpopulation; labels show percentage gained/lost relative to the reference. 5/17\", \"page\": 5, \"index\": 5, \"width\": 1038, \"height\": 1079}]"
motivation: 传统变异预测方法通常基于单一参考基因组，忽略了遗传背景多样性对变异效应的潜在调节作用。
method: 引入个性化变异效应预测（pVEP）框架，利用深度学习模型在数千个全球多样化的人类基因组背景下评估临床变异。
result: 发现许多临床变异在不同单倍型中表现出异质性预测效应，同一变异在某些背景下被预测为致病，而在另一些背景下则为良性。
conclusion: 个性化基因组背景是变异注释和临床解释中被系统性低估的关键变量，对遗传多样化人群的精准医疗具有重要意义。
---

## 摘要
预测遗传变异的后果仍然是生物医学领域的一个主要目标。传统方法通常在单一参考基因组的背景下评估单核苷酸变异，而未考虑可能调节变异效应的遗传多样性。在此，我们介绍了个性化变异效应预测器（pVEP）框架，该框架量化了来自全球多样化人群的数千个人类基因组的遗传背景如何塑造临床变异效应的计算预测。通过涵盖蛋白质结构、剪接和非编码调控的深度学习模型，pVEP 揭示了许多临床变异在不同单倍型中表现出异质性的预测效应，即同一个变异在某些遗传背景下被预测为致病性，而在其他背景下则被预测为良性。我们发现了潜在分子机制的支持证据，包括预测的蛋白质接触位点偏移和剪接位点识别的变化。总体而言，个性化基因组背景是变异注释和临床解释中一个被系统性低估的变量，这对遗传多样化的人群具有特殊意义。

## Abstract
Predicting the consequences of genetic variants remains a major goal in biomedicine. Conventional approaches typically assess single-nucleotide variants in the context of a single reference genome, without accounting for genetic diversity that can modulate variant effects. Here we introduce the personalized variant effect predictor (pVEP) framework, which quantifies how genetic background across thousands of human genomes from globally diverse populations shapes computational predictions of clinical variant effects. Across deep learning models spanning protein structure, splicing, and noncoding regulation, pVEP reveals that many clinical variants exhibit heterogeneous predicted effects across haplotypes, with the same variant predicted to be pathogenic in some genetic backgrounds and benign in others. We find support for underlying molecular mechanisms, including shifts in predicted protein contacts and changes in splice-site recognition. Overall, personalized genomic context emerges as a systematically underappreciated variable in variant annotation and clinical interpretation, with particular implications for genetically diverse populations.

---

## 论文详细总结（自动生成）

### 论文总结：遗传背景塑造 AI 预测的变异效应

#### 1. 核心问题与整体含义
*   **核心问题**：传统的遗传变异效应预测（VEP）方法通常基于单一的“参考基因组”（Reference Genome）。然而，每个人的基因组中都存在数百万个背景变异，这些背景变异可能通过上位性（Epistasis）相互作用，调节临床变异的致病性。
*   **整体含义**：本研究旨在揭示遗传背景的多样性如何影响 AI 模型对临床变异风险的评估。研究强调，忽略个体遗传差异会导致对变异效应的误判，这对于精准医疗的公平性和准确性具有重要意义。

#### 2. 方法论
*   **核心思想**：提出了**个性化变异效应预测（pVEP）框架**。该框架不再只在参考序列上测试变异，而是将临床变异植入到数千个真实的、具有全球代表性的个体单倍型（Haplotypes）中。
*   **关键技术细节**：
    *   **多维度模型集成**：使用了三种深度学习模型来评估不同类型的变异：
        *   **ESM2-650M**（蛋白质语言模型）：预测蛋白质编码区的错义变异效应。
        *   **SpliceAI**：预测对 RNA 剪接的影响。
        *   **Flashzoi**：预测非编码区（如 5'/3' UTR）的调控效应。
    *   **分析流程**：针对每个临床变异，计算其在参考基因组上的得分（$VEP_{ref}$）以及在数千个个体背景下的得分分布。
    *   **代理模型（Surrogate Modeling）**：利用线性模型或交互模型来识别哪些特定的背景变异导致了临床变异效应的改变。

#### 3. 实验设计
*   **数据集**：
    *   **人群背景**：来自 1000 Genomes Project 和 Human Genome Diversity Project (HGDP) 的 3,819 名个体，涵盖全球五大超群（AFR, AMR, EAS, EUR, SAS）。
    *   **变异集**：ClinVar 数据库中的 62,727 个错义变异、8,490 个剪接变异和 13,771 个 UTR 变异。
*   **Benchmark**：以传统的基于参考基因组的预测结果（$VEP_{ref}$）作为基准，对比个性化背景下的得分均值（$VEP_{mean}$）和分布差异。
*   **对比分析**：通过 AlphaFold2 预测的蛋白质结构接触图，验证背景变异是否通过改变物理接触来影响临床变异的效应。

#### 4. 资源与算力
*   **算力说明**：论文中未明确给出具体的 GPU 型号、数量或总训练时长。但考虑到其处理了数千万个单倍型-变异组合（如 UTR 区域涉及超过 1 亿个单倍型窗口），且使用了 ESM2-650M 等大型模型进行推理，该研究显然消耗了极高规模的计算资源。

#### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了蛋白质结构、剪接和非编码调控三个生物学层面，实验对象包括数万个临床变异和数千个基因组背景，数据量极其庞大。
*   **充分性与客观性**：
    *   实验设计非常充分，不仅有大规模的统计分析，还针对特定基因（如 BRCA1）进行了深入的结构生物学验证。
    *   通过对不同族裔背景的对比，客观地展示了遗传背景导致的预测偏差，具有很高的科学严谨性。

#### 6. 主要结论与发现
*   **效应异质性**：许多临床变异在不同背景下表现出截然不同的预测效应。同一个变异在某些人身上被预测为致病，而在另一些人身上则为良性。
*   **参考基因组的局限**：$VEP_{ref}$ 往往不能代表人群的平均水平，有时会显著高估或低估变异的真实风险。
*   **分子机制**：背景变异通过改变蛋白质的局部接触环境或改变剪接位点的识别序列，从而“补偿”或“放大”临床变异的有害性。
*   **族裔差异**：某些变异的预测效应在特定族裔中呈现双峰分布，暗示了群体特异性的遗传修饰因子。

#### 7. 优点
*   **视角创新**：打破了“单一参考基因组”的思维定式，将遗传多样性引入 AI 变异预测领域。
*   **多模态覆盖**：同时考虑了蛋白质、RNA 剪接和非编码调控，提供了全方位的分子视角。
*   **临床价值**：为解释“外显率不全”（Incomplete Penetrance）提供了计算层面的解释工具，有助于减少临床诊断中的误报。

#### 8. 不足与局限
*   **缺乏实验金标准验证**：虽然 AI 预测显示了背景依赖性，但大规模的湿实验（如大规模并行报告分析 MPRA）验证仍相对有限。
*   **模型依赖性**：结论高度依赖于底层 AI 模型（如 ESM2, SpliceAI）的准确性，如果基础模型存在偏差，pVEP 的结果也会受影响。
*   **计算成本极高**：为每个患者进行全基因组背景下的 pVEP 计算在目前临床普及中仍面临算力挑战。
*   **罕见变异覆盖**：虽然使用了多样化人群，但极罕见的背景变异可能仍未被充分纳入分析。

（完）
