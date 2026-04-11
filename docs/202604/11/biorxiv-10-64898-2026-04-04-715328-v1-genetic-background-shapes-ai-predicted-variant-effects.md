---
title: Genetic background shapes AI-predicted variant effects
title_zh: 遗传背景塑造 AI 预测的变异效应
authors: "Schilder, B. M., Liu, Z., Desmarais, J. J., Laub, D., Rahimi, F., Sethi, P., Pereira, L. A., Sun, M. M., Kinney, J. B., McCandlish, D. M., Zhou, J., Koo, P. K."
date: 2026-04-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.04.715328v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 不同遗传背景下AI预测的变异效应
tldr: 本研究针对传统变异预测忽略遗传多样性的局限，提出个性化变异效应预测（pVEP）框架。通过在数千个全球多样化基因组背景下应用深度学习模型，研究发现遗传背景会显著改变临床变异的预测效应，导致同一变异在不同个体中呈现致病或良性的差异。该研究强调了个性化基因组背景在变异注释中的关键作用，对提升全球多样化人群的临床诊断准确性具有重要意义。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-04-715328-v1/fig-001.webp\", \"caption\": \"Figure 4. pVEP reveals background-dependent predicted effects for clinical splicing variants. a, Filled density plot of all SpliceAI reference-based and personalized VEP scores per clinical variant (x-axis: 0 = no predicted splice disruption, 1 = complete disruption), stratified by ClinVar pathogenicity (n = 8.5 k: 2.6 k benign, 2.5 k VUS, 3.3 k pathogenic). The red vertical line indicates spliceogenicity threshold. b, Bar plot of pVEP scores grouped by ClinVar pathogenicity label, showing pathogenic variants and VUS have high predicted spliceogenicity than benign ones (two-sided Mann-Whitney U test: U = 2.16×106 – 2.72×106, p = 2.03×10−114 to 2.51×10−243). ns: p≥ .05; **: p < 0.01; ****: p < 0.0001). c, Bar plot of counts of SpliceAI-predicted variant effect classes (donor/acceptor gain or loss), colored by clinical significance. d, Bar plot of Shannon entropy of SpliceAI-predicted effect classes across haplotypes, grouped by pathogenicity labels. Pathogenic variants and VUS have significantly higher entropy than benign variants (two-sided independent-samples t-tests: t = 5.52–14.35, p = 6.2×10−46 to 3.6×10−8) e, Boxplot of surrogate model marginal effects per clinical variant, colored by ClinVar significance, showing pathogenic variants and VUS have higher marginal effects than benign variants (two-sided Mann-Whitney U tests: p < 0.0001). f, Bar plot of clinical variant marginals grouped by whether the clinical variant overlaps a splicing-relevant region: 3′ splice-site (ss), 5′ss, canonical, or intronic proximal. Variants within canonical and intronic proximal 3′/5′ss displayed greater effects than others (two-sided Mann-Whitney U tests: p < 0.001). g, VEP score distributions across haplotypes for chr17:2981247 A>G (RAP1GAP2, VUS) and chr17:43115788 G>C (BRCA1, pathogenic). Upper panels show log-scale haplotype frequency with spliceogenicity (red) and reference (grey) thresholds marked. Lower panels show superpopulation composition per VEP score bin. h, Attribution maps for four genomic context around BRCA1 chr17:43115788 G>C: reference and HG03691 haplotype, each with and without the clinical variant. Attribution maps given by Integrated Gradients highlight sequence-level determinants of 3′ splice-site choice. The clinical variant is highlighted in purple and the compensatory background variant in green. This variant induced a strong splicing change in all haplotypes (max ∆ = 0.996) except for the HG03691-specific haplotype (max ∆ = 0.0195). 6/17\", \"page\": 6, \"index\": 1, \"width\": 1038, \"height\": 1081}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-04-715328-v1/fig-002.webp\", \"caption\": \"Figure 1. Overview of the pVEP framework and variant datasets. a, Schematic of the pVEP framework. For each clinical variant, model predictions are computed across reference and personalized background sequences with (MUT) and without (WT) the clinical variant introduced, yielding a distribution of predicted variant effects with the reference-based VEP score (V EPref) marked for comparison. b, Bar chart of individuals per ancestral superpopulation across the 1000 Genomes Project and Human Genome Diversity Project (n = 3,819 individuals). c, Histogram of unique haplotypes per protein across all transcripts analyzed (n = 2,847 transcripts). d, Histograms of background variants per haplotype for protein sequences in ProteinGym (top, n = 132,721 unique haplotypes), 10 kb DNA windows centered on splicing variants in SpliceVarDB (middle, n = 64,846,620 unique haplotypes), and 524 kb DNA windows centered on 5′/3′ UTR variants from ClinVar (bottom, n = 105,182,898 unique haplotypes). Counts <10 are binned for visualization purposes. e, Schematics of the three clinical variant classes explored and bar plot of variant counts per class (missense: n = 62,727, splicing: n = 8,490, and UTR: n = 13,771), colored by ClinVar pathogenicity label.\", \"page\": 2, \"index\": 2, \"width\": 1017, \"height\": 763}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-04-715328-v1/fig-003.webp\", \"caption\": \"Figure 2. pVEP reveals heterogeneous predicted responses to clinical missense variants. a, Filled density plot of ESM2-650M reference-based and personalized VEP scores across all missense variants, stratified by ClinVar pathogenicity (n = 62,727: ∼8,600 benign, ∼19,500 likely benign, ∼19,300 likely pathogenic, and ∼8,900 pathogenic variants). Negative values (rightwards) indicate more pathogenic effects. Vertical dashed line (red) indicates benign/pathogenic threshold. b, Stacked bar plot showing the percentile bin (fill color) of reference-based VEP score (V EPref) relative to the full distribution average (V EPmean) at each V EPmean decile. A greater proportion of red bars indicates V EPref tends to overestimate pathogenicity, whereas a greater proportion of blue bars indicates underestimation. The gray horizontal dashed line demarcates 50% of the variants in that VEP Decile. c, Stacked barplot showing the proportion of clinical variants whose ESM2-650M VEP scores follow a normal distribution (D’Agostino-Pearson omnibus test, FDR > 0.05), non-normal distribution (FDR < 0.05,) or could not be tested (n < 20 protein haplotypes), grouped by ClinVar pathogenicity. d, Bar plot of the estimated number of modes per clinical variant VEP score distribution, inferred from a variational Bayes Gaussian mixture model. e, Haplotype-level VEP score distributions for three missense variants with high inter-haplotype variability: TH 167V>E (n = 71 haplotypes, top), COX10 225P>L (n = 46, middle), and ALDH5A1 179I>N (n = 55, bottom). Vertical dashed lines indicate V EPmean (gold), V EPref (grey), and the empirically inferred benign/pathogenic boundary (red). f, Haplotype-level ESM2-650M VEP score distribution for VHL 121C>F (n = 15 haplotypes). Vertical dashed lines indicate V EPmean (gold) and V EPref (grey). Bar plots below show the proportion of individuals from each ancestry per VEP score bin. AFR=African, AMR=Admixed American, EAS=East Asian, EUR=European, SAS=South Asian.\", \"page\": 3, \"index\": 3, \"width\": 1010, \"height\": 666}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-04-715328-v1/fig-004.webp\", \"caption\": \"Figure 5. pVEP reveals background-dependent predicted effects for clinical UTR variants. a, Filled density plot of Flashzoi average pVEP scores (V EPmean) per clinical variant, stratified by ClinVar pathogenicity. Vertical dashed lines indicate the reference-based VEP score (V EPref; grey) and the empirically inferred benign/pathogenic boundary (red). b, Bar plot of V EPmean grouped by UTR type (5′/3′) and ClinVar pathogenicity label. Pathogenic-labeled variants had significantly greater predicted pathogenicity than benign variants (two-sided Mann–Whitney U tests: 3′ UTR benign vs. pathogenic, U = 4.42×105, p = 1.3×10−7; 5′ UTR, U = 4.65×105, p = 0.016). ns: p≥ .05; ****: p≤ 0.0001. c, Bar plot of variability (median absolute deviation) of Flashzoi VEP score distributions across haplotypes, grouped by UTR type and ClinVar pathogenicity label. Benign variants within 5′ UTR regions showed greater variability in predicted effects than those witihn 3′ regions (two-sided Mann-Whitney U test: p < 0.0001). d, Haplotype-level VEP score distributions for the four clinical UTR variants with the greatest variability across haplotypes. Vertical dashed lines indicate V EPmean (gold), V EPref (grey), and the empirically inferred benign/pathogenic boundary (red), derived from gene-specific variational Bayes Gaussian mixture models. Below each histogram, bar plots show the proportion of haplotypes from each ancestry per VEP bin.\", \"page\": 8, \"index\": 4, \"width\": 765, \"height\": 677}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-04-715328-v1/fig-005.webp\", \"caption\": \"Figure 3. Background variants modify the effects of BRCA1 clinical variants in close structural proximity. a, Surrogate modeling takes as input a binary matrix of background variant presence across haplotypes (left) and predicts continuous clinical variant VEP scores (right), yielding a variant sensitization map of inferred joint effects (center). b, Predicted 3D structure of BRCA1 from AlphaFold2 (AF2). c, Variant sensitization map (inferred from ESM2 VEP scores) overlaid on the AF2-predicted BRCA1 distance map, showing all 652 significant non-additive interactions (center heatmap; p < 0.05). Red boxes indicate variant pairs where a background variant (y-axis) increases predicted pathogenicity of a clinical variant (x-axis). Pathogenic clinical variants (top scatter/density) are concentrated in the RING and BRCT domains (grey vertical bars), recapitulated by surrogate model marginal effects for clinical (bottom) and background variants (right). d, 3D structural visualization of interaction pairs: background variant 1706G>A with clinical variants 1684T>A and 1687V>I (left), and 1729L>Q with 1722S>F (FDR = 1.43×10−13; right). Spheres indicate clinical variants colored by V EPmean (red: pathogenic, blue: benign); ribbon color and dashed lines indicate the background variant’s effect on pathogenicity (red: ↑, blue: ↓, grey: no data). Labels indicate reference amino acid and residue position. e, Zoomed-in AF2 distance maps for the four variant pairs with the strongest interaction coefficients in BRCA1. f, Boxplot of clinical variant marginals grouped by ClinVar pathogenicity; pathogenic variants have higher marginals than benign ones (two-sided Mann–Whitney U tests: U = 1355–2302, p = 1.33×10−21 to 8.33×10−13, nbenign/likely benign = 137–167, npathogenic/likely pathogenic = 57–95; ns: p≥ .05; ****: p≤ 0.0001). g, Observed-to-expected enrichment of AF2 residue contacts among variant pairs at each interaction threshold, with variant pair counts on the secondary axis. h, Residue-by-residue heatmap showing the proportion of haplotypes (n = 126) gaining (blue) or losing (red) AF2-predicted contacts (< 8 Å) relative to the reference. i, Bar plot of reference contacts gained (blue) or lost (red) in population-weighted contact maps stratified by superpopulation; labels show percentage gained/lost relative to the reference. 5/17\", \"page\": 5, \"index\": 5, \"width\": 1038, \"height\": 1079}]"
motivation: 传统变异预测依赖单一参考基因组，忽视了遗传背景多样性对变异效应的调节作用。
method: 开发了pVEP框架，利用多种深度学习模型在数千个多样化人类基因组中量化遗传背景对变异预测的影响。
result: 发现大量临床变异在不同单倍型上表现出异质性效应，其预测结果受蛋白质接触变化和剪接位点识别等机制影响。
conclusion: 个性化基因组背景是变异解释中被长期低估的变量，对实现遗传多样化人群的精准医疗至关重要。
---

## 摘要
预测遗传变异的后果仍然是生物医学领域的一个主要目标。传统方法通常在单一参考基因组的背景下评估单核苷酸变异，而未考虑可能调节变异效应的遗传多样性。在此，我们介绍了个性化变异效应预测器（pVEP）框架，该框架量化了来自全球多样化人群的数千个人类基因组遗传背景如何影响临床变异效应的计算预测。通过跨越蛋白质结构、剪接和非编码调控的深度学习模型，pVEP 揭示了许多临床变异在不同单倍型中表现出异质性的预测效应，即同一个变异在某些遗传背景下被预测为致病性，而在其他背景下则被预测为良性。我们发现了潜在分子机制的支持证据，包括预测的蛋白质接触偏移和剪接位点识别的变化。总体而言，个性化基因组背景已成为变异注释和临床解释中一个被系统性低估的变量，这对遗传多样化的人群具有特殊意义。

## Abstract
Predicting the consequences of genetic variants remains a major goal in biomedicine. Conventional approaches typically assess single-nucleotide variants in the context of a single reference genome, without accounting for genetic diversity that can modulate variant effects. Here we introduce the personalized variant effect predictor (pVEP) framework, which quantifies how genetic background across thousands of human genomes from globally diverse populations shapes computational predictions of clinical variant effects. Across deep learning models spanning protein structure, splicing, and noncoding regulation, pVEP reveals that many clinical variants exhibit heterogeneous predicted effects across haplotypes, with the same variant predicted to be pathogenic in some genetic backgrounds and benign in others. We find support for underlying molecular mechanisms, including shifts in predicted protein contacts and changes in splice-site recognition. Overall, personalized genomic context emerges as a systematically underappreciated variable in variant annotation and clinical interpretation, with particular implications for genetically diverse populations.

---

## 论文详细总结（自动生成）

### 论文结构化总结：遗传背景塑造 AI 预测的变异效应

#### 1. 核心问题与整体含义
*   **研究动机**：传统的变异效应预测（VEP）通常采用“一变异一效应”的范式，即在单一参考基因组（如 GRCh38）上评估变异。然而，每个人的基因组与参考基因组之间存在数百万个差异，这些遗传背景（Genetic Background）可能通过复杂的相互作用（如上位性）调节变异的临床后果。
*   **核心问题**：遗传背景在多大程度上影响 AI 模型对临床变异（致病 vs 良性）的预测？这种背景依赖性是否存在可解释的分子机制？
*   **整体含义**：论文提出了 **pVEP（personalized Variant Effect Predictor）** 框架，证明了遗传背景是变异解释中一个被长期忽视的关键变量，强调了在多样化人群中进行个性化变异评估的必要性。

#### 2. 方法论
*   **核心思想**：通过将临床变异“注入”到数千个真实的全球多样化人类单倍型中，观察 AI 模型预测值的分布变化，而非仅依赖单一参考基因组的预测。
*   **关键技术流程**：
    1.  **单倍型构建**：从 1000 Genomes Project 和 HGDP 数据集中提取 3,819 个个体的相位化（Phased）基因组，构建蛋白质和 DNA 单倍型。
    2.  **变异注入**：将 ClinVar 等数据库中的临床变异（错义、剪接、UTR 变异）原位替换到这些个性化背景序列中。
    3.  **多模态预测**：
        *   **蛋白质层面**：使用 ESM 系列模型（如 ESM2-650M）预测蛋白质适应度。
        *   **剪接层面**：使用 SpliceAI 预测剪接位点的改变。
        *   **调控层面**：使用 Flashzoi（Borzoi 的高效版）预测 UTR 区域的 RNA 覆盖度变化。
    4.  **变异敏化图（Variant Sensitization Map）**：利用岭回归（Ridge Regression）建立代理模型，量化背景变异与临床变异之间的非加性相互作用。
    5.  **结构验证**：利用 AlphaFold2 预测不同单倍型的 3D 结构接触变化。

#### 3. 实验设计
*   **数据集**：
    *   **背景序列**：来自全球 7 个超大种群的 3,819 个高质量基因组。
    *   **临床变异**：62,727 个错义变异（ProteinGym）、8,490 个剪接变异（SpliceVarDB）和 13,771 个 UTR 变异（ClinVar）。
*   **Benchmark 与对比**：
    *   以参考基因组预测值（$VEP_{ref}$）作为基准。
    *   对比 $VEP_{ref}$ 与人群分布均值（$VEP_{mean}$）的偏差。
    *   使用 95 种已知的变异注释（如进化保守性、等位基因频率）来验证预测值的生物学相关性。

#### 4. 资源与算力
*   **算力投入**：
    *   **蛋白质预测**：使用 4 × NVIDIA A100 (80GB) GPU。
    *   **剪接预测**：使用 1 × NVIDIA H100 (80GB) GPU。
    *   **UTR 预测**：由于窗口大（524kb）且变异多，使用了 **20 × NVIDIA H100 (80GB)** GPU 进行大规模并行推理。
    *   **结构预测**：使用 2 × NVIDIA A100 GPU 运行 AlphaFold2/ColabFold。
*   **说明**：论文未明确给出总训练/推理时长，但从硬件配置看，该研究属于高算力消耗型，尤其是非编码区的全基因组规模预测。

#### 5. 实验数量与充分性
*   **实验规模**：分析了约 85,000 个临床变异在数百万个单倍型背景下的表现，数据量极大。
*   **充分性**：
    *   涵盖了从编码区到非编码区的多个分子层面。
    *   针对 BRCA1 和 TP53 等典型基因进行了深入的结构和机制消融分析。
    *   通过与大规模并行剪接实验（MPSA）数据对比，验证了模型捕捉上位性（Epistasis）的能力。
*   **客观性**：实验考虑了全球不同种群的代表性，并使用了多种独立的 AI 模型架构，结果具有较强的鲁棒性。

#### 6. 主要结论与发现
*   **背景依赖性普遍存在**：超过 95% 的临床变异在不同背景下的预测效应呈现多峰分布，而非简单的正态分布。
*   **参考基因组的局限性**：参考基因组往往处于预测分布的极端位置，系统性地低估了某些临床变异的致病性，尤其是在非欧洲裔背景下。
*   **分子机制**：
    *   在蛋白质中，背景变异通过改变 3D 接触（尤其是 RING 和 BRCT 结构域）来调节临床变异效应。
    *   在剪接中，背景变异可能通过破坏由临床变异产生的隐蔽剪接位点（Cryptic Splice Sites）起到补偿作用。
*   **性能提升**：使用人群平均预测值（$VEP_{mean}$）比单一参考基因组预测值更能准确反映变异的生物学特性（如与等位基因频率的相关性更强）。

#### 7. 优点
*   **范式转移**：挑战了变异解释中长期存在的“参考基因组依赖”假设，提出了更符合生物学真实的个性化评估框架。
*   **可解释性强**：结合了 XAI 技术和 3D 结构预测，为 AI 发现的背景依赖性提供了物理和分子层面的解释。
*   **工具化贡献**：开发的 pVEP 框架具有良好的扩展性，可适配未来的新模型和更大规模的生物样本库（如 UK Biobank）。

#### 8. 不足与局限
*   **模型偏差风险**：pVEP 的发现高度依赖于底层序列模型（如 ESM, SpliceAI）的准确性，如果模型本身存在系统性偏差，结果可能受影响。
*   **缺乏实验真值**：目前生物医学界极度缺乏在不同遗传背景下测试同一变异效应的大规模实验数据，导致 AI 预测的异质性难以得到完全的临床验证。
*   **计算成本高昂**：对于临床常规诊断而言，在数千个背景下运行深度学习模型的计算开销目前仍然过高。

（完）
