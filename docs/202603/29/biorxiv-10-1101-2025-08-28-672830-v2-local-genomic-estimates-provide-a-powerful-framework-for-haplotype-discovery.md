---
title: Local genomic estimates provide a powerful framework for haplotype discovery
title_zh: 局部基因组估计为单倍型发现提供了一个强大的框架
authors: "Shaffer, W., Papin, V., Yadav, S., Voss-Fels, K. P., Hickey, L., Hayes, B., Dinglasan, E. G."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.1101/2025.08.28.672830v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 用于单倍型发现和标记效应估计的GWAS框架
tldr: 本研究针对传统GWAS在处理单标记连锁不平衡时的局限性，系统评估了局部基因组估计育种值（localGEBV）在QTL发现中的应用。该方法通过将标记划分为单倍型块并计算其效应方差，克服了传统方法对累积信号捕捉不足的问题。在大麦行型性状的验证中，localGEBV在QTL识别精度和表型预测准确性上均优于传统GWAS，且对先验假设和分块参数具有良好的鲁棒性，为植物育种提供了高效的单倍型发现框架。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-08-28-672830-v2/fig-001.webp\", \"caption\": \"Figure 4. Detection of haploblocks containing QTL. Physical position in barley 210 chromosome of SNP markers associated with row-type spike architecture detected from 211 localGEBV and GWAS. Tracks 1 to 5 (outer to innermost): Track 1 Barley chromosome 212 showing physical position (Mbp) based on cv Morex assembly v2 from the 40K XT SNP 213 chip. SNP markers are coloured in grey. Colocation of known genes and QTL from the 214 literatures is shown: row-type known genes (VRS3 in 1H, VRS1 in 2H, VRS4 in 3H, VRS5 in 215 4H, VRS2 in 5H; dark red), phenology genes (FT3, PPD1, CIGARP, Cry1b, CYP-1, 216 GA20ox2-2, Q2_CMF4, HSH1, FT5, Q6_TFL, Q6_FCA, Q6_PFT, PHYC, Q7_AGL1, 217 CO2_H4M1, Q10_CO11, Q3_MADS25-2, Q3_FT1, Q3_CO8, CO1; green ), yield-218 component candidate genes (brown); and QTL for spike sterility (qStrlSpk), grain spiculation 219 of inner lateral nerve (qGSILN), spike row number (qRow), are also shown in dark red. 220 Track 2 LocalGEBV estimated using Bayes R, track colour in blue. Track 3 LocalGEBV 221 estimated using rrBLUP, track colour in green. Track 4 GWAS using BLINK, track colour in 222\", \"page\": 11, \"index\": 1, \"width\": 1019, \"height\": 869}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-08-28-672830-v2/fig-002.webp\", \"caption\": \"Figure 5. Accuracy of predictors in identifying informative associations with row-spike phenotype. (A) Principal component analysis 280 showing the effects contribution of M = 9,050 XT SNP marker estimates from FarmCPU, BLINK, rrBLUP, and BayesR. Colours represent the 7 281 barley chromosomes; size of each dots represents the SNP effect contribution to the principal components relating to row-spike phenotype. (B) 282 Regression analysis of marker genotypesor haploblock haplotype configurations as predictors. Shown is the accuracy calculated as correlations 283 of the predicted value in the testing set; predicted values calculated using ordinary least squares linear probability model (LPM, light purple) and 284 logistic regression in the generalised linear model (GLM, dark purple). The most significant marker (2H:AVRIG03047) identified by both 285\", \"page\": 15, \"index\": 2, \"width\": 1523, \"height\": 627}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-08-28-672830-v2/fig-003.webp\", \"caption\": \"Figure 2. Relationship between haploblock variance and haploblock size. Haploblock 160 variance derived from localGEBV estimates using rrBLUP (green) and BayesR (blue), 161 plotted on the y-axis. Block size is defined by the number of SNP markers within 162 haploblocks, plotted on the x-axis. In the figure, different LD parameters are shown as facets: 163 column facets represent LD thresholds of 𝑟2 ∈ {0.1, 0.3, 0.5}; and row facet as marker 164 tolerance, 𝑡𝑜𝑙 ∈ {0, 1, 2, 3}. The localGEBV variance was scaled using a min-max scaling of 165 the log10 transformed variance. Blocks were connected using a generalized additive model 166 for non-linear relationships to represent trends between haploblock size and localGEBV 167 variance.168\", \"page\": 7, \"index\": 3, \"width\": 1019, \"height\": 727}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-08-28-672830-v2/fig-004.webp\", \"caption\": \"Table 1. Summary statistics of high variance haploblocks for row-spike phenotype from localGEBV estimated using rrBLUP and BayesR, and 862 significant markers identified using FarmCPU and BLINK. Only haploblocks with localGEBV Bonferroni or False Discovery Rate (FDR) 863 corrected p-values are displayed. 864\", \"page\": 39, \"index\": 4, \"width\": 1603, \"height\": 767}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-08-28-672830-v2/fig-005.webp\", \"caption\": \"Figure 3. LocalGEBV variance of haploblocks in chromosome 2H. The VRS1 gene 170 (marked as Δ) is co-located at 652.03 Mbp based on the XT SNP chip physical position using 171 cv Morex assembly v2. (A) The localGEBV variance profiles across chromosome 2H 172\", \"page\": 8, \"index\": 5, \"width\": 1019, \"height\": 1296}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-08-28-672830-v2/fig-006.webp\", \"caption\": \"Figure 7. Haplotype analysis. (A) Identification of haplotypes from the localGEBV 297 estimates using rrBLUP and BayesR. In the figure, x-axis shows the marker physical position 298 (Mbp) of chromosome 2H based on cv Morex assembly v2 from the 40K XT SNP chip; while 299 the y-axis corresponds to localGEBV or haplotype effects. The dotted vertical line illustrates 300 the position of VRS1 gene at 652.03 Mbp. Haplotypes associated with row-type phenotypes 301 are determined by the direction of localGEBV estimates, whereby negative localGEBV 302 effects favours 2-row phenotypes while positive localGEBV effects favours 6-row 303 phenotypes. Each dot corresponds to a specific haplotype, wherein the size of the dots 304 represents the haplotype abundance or the frequency of barley accessions carrying the 305\", \"page\": 19, \"index\": 6, \"width\": 1019, \"height\": 1029}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-08-28-672830-v2/fig-007.webp\", \"caption\": \"Figure 6. Relationship between haploblock variance and haplotype effects. Haploblock variance was determined from the localGEBV 291 estimates using rrBLUP (green) and BayesR (blue); plotted as min-max scaled of the log10 transformed variance for visual clarity. In the figure, 292 different LD parameters are shown as facets: column facet represented by LD threshold at 𝑟2 ∈ {0.1, 0.3, 0.5}; and row facet as marker tolerance 293\", \"page\": 17, \"index\": 7, \"width\": 1532, \"height\": 763}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-08-28-672830-v2/fig-008.webp\", \"caption\": \"Figure 1. Population structure and genetic relationships of barley germplasm. (A) 120 Principal component analysis of N = 790 barley accessions using 9,050 XT SNP chip 121 markers, revealing three distinct genetic clusters. Shown are PCs 1 and 2 from Roger’s 122 genetic distance matrix, accounting for 44.8% cumulative explained variation. The optimum 123 number of clusters were clusters = 3: Cluster 1 (313), Cluster 2 (297), and Cluster 3 (180). 124 Colours represent the row spike phenotype i.e. 2-row is orange, 6-row is blue. (B) 125 Proportions of barley accessions across the three clusters: Cluster 1 (2-row = 283, 6-row = 8, 126 NA = 22), Cluster 2 (2-row = 56, 6-row = 214, NA = 27), Cluster 3 (2-row = 15, 6-row = 150, 127 NA = 15), where NA represents accessions with ambiguous information and ‘irregular’ type. 128 (C) Genome-wide LD decay as a function of physical distance (Mbp). LD decay is shown at 129 an average distance (Mbp) between adjacent SNP based on the XT SNP chip physical 130 position using cv Morex assembly v2 and visualised up to 10 Mbp. (D) An example of the 131 two-row and six-row phenotypes.132\", \"page\": 5, \"index\": 8, \"width\": 1007, \"height\": 781}]"
motivation: 传统GWAS难以有效处理多个标记与QTL间的不完全连锁或信号分裂问题，限制了优异单倍型的识别效率。
method: 提出一种基于连锁不平衡划分单倍型块，并利用rrBLUP和BayesR计算局部基因组估计育种值方差的QTL定位策略。
result: 实验证明localGEBV在大麦性状定位中比单标记方法更精确，且在不同参数设置下均表现出极高的稳定性。
conclusion: localGEBV为利用局部基因组效应提升QTL发现和基因组选择效力提供了一个强大且灵活的单倍型分析框架。
---

## 摘要
在多样性群体或育种群体中进行的数量性状位点（QTL）发现研究通常使用全基因组关联分析（GWAS）来估计标记效应。对于动植物育种应用，研究人员日益认识到识别优异单倍型（处于连锁不平衡 LD 中的标记）而非依赖单个标记的潜在益处，因为传统方法在处理与 QTL 不完全连锁产生的累积信号，或当多个标记与 QTL 处于高连锁不平衡时产生的效应分裂方面效率较低。利用基因组预测框架，局部基因组估计育种值（localGEBV）方法在动物育种中被开发出来，并已被应用于作物单倍型图谱研究；然而，目前尚无研究彻底量化该方法的效用，或将其结果与传统 GWAS 方法进行系统比较。在本研究中，我们描述了一种基于连锁不平衡将染色体片段中的标记进行分组的策略（单倍型块或 haploblocks），将 localGEBV 计算为每个单倍型块内标记效应的线性对比，并利用 localGEBV 的方差来增强 QTL 发现，并与传统 GWAS 进行对比。localGEBV 的标记效应通过岭回归最佳线性无偏预测（rrBLUP）和 BayesR 进行估计，并将结果与两种常用的 GWAS 方法进行了比较。利用大麦棱型性状，我们证明了与单个标记相比，localGEBV 提高了 QTL 发现和表型预测的准确性。此外，localGEBV 的结果对于先验标记假设和分块参数的选择具有稳健性，从而在精细或宽尺度 QTL 定位中实现了灵活性。总的来说，我们的研究结果确立了 localGEBV 作为一种基于单倍型的策略，能够利用局部基因组效应来改善 QTL 发现，并具有改进基因组选择的潜力。

## Abstract
Quantitative trait loci (QTL) discovery studies on diversity panels or breeding populations typically use genome-wide association studies (GWAS) to estimate marker effects. For plant and animal breeding applications, researchers increasingly recognize the potential benefits of identifying superior haplotypes (markers in linkage disequilibrium; LD) rather than relying on single markers, as traditional approaches inefficiently account for cumulative signals from incomplete LD with QTL or split effects when multiple markers are in high LD with QTL. Using the genomic prediction framework, the local genomic estimated breeding values (localGEBV) method was developed in animal breeding and has been adopted in crop haplotype mapping studies; however, no study has thoroughly quantified the utility of this method or systematically compared outcomes to traditional GWAS approaches. Here, we characterized a strategy to group markers in chromosomal segments based on LD (haplotype blocks or haploblocks), computed localGEBV as a linear contrast of marker effects within each haploblock, and utilised the variance of localGEBV to enhance QTL discovery compared to traditional GWAS. Marker effects for localGEBV were estimated with ridge-regression best linear unbiased prediction (rrBLUP) and BayesR, with results compared to two common GWAS approaches. Using the barley row-type trait, we demonstrated that localGEBV improved QTL discovery and phenotypic prediction compared to single markers. Furthermore, localGEBV results were robust to the choice of prior marker assumptions and blocking parameters, enabling flexibility in fine or broad-scale QTL mapping. Overall, our findings establish localGEBV as a haplotype-based strategy capable of leveraging localized genomic effects to improve QTL discovery and, potentially, genomic selection.

---

## 论文详细总结（自动生成）

这篇论文对**局部基因组估计育种值（localGEBV）**在QTL（数量性状位点）发现中的应用进行了系统性评估，并将其与传统及现代GWAS方法进行了深入对比。以下是对该论文的结构化总结：

### 1. 核心问题与研究动机
*   **核心问题**：传统的全基因组关联分析（GWAS）主要依赖单标记回归。在连锁不平衡（LD）广泛存在的群体（如农作物和家畜）中，单标记方法存在两大缺陷：一是**效应分裂**（一个QTL的效应被多个标记瓜分），二是**信号捕捉不全**（单个标记无法完全代表QTL）。
*   **研究动机**：虽然单倍型（Haplotype）方法理论上能捕捉更完整的遗传信号，但目前缺乏将基于基因组预测框架的localGEBV方法与现代多位点GWAS方法（如FarmCPU、BLINK）进行系统量化对比的研究。

### 2. 方法论
该研究提出了一套基于单倍型块（Haploblock）的QTL发现框架，包含四个关键步骤：
*   **单倍型块构建**：基于LD参数（$r^2$阈值和标记容差$tol$）将全基因组标记划分为不相交的染色体片段。
*   **标记效应估计**：利用基因组预测模型同时估计所有标记效应。对比了两种模型：
    *   **rrBLUP**：假设所有标记具有微小且相等的方差（无穷小模型）。
    *   **BayesR**：使用混合先验，允许标记具有不同大小的效应或无效应。
*   **localGEBV计算**：将特定单倍型块内所有标记效应的线性组合定义为该个体的局部估计育种值：$localGEBV_j = Z_j \hat{u}_j$。
*   **QTL识别指标**：利用**localGEBV的方差**作为检测信号。通过卡方分布检验该方差是否显著高于零（零假设为方差在全基因组块间均匀分布）。

### 3. 实验设计
*   **数据集**：大麦（Barley）全球多样性面板，包含759个品种，使用40K SNP芯片（筛选后剩余9,050个标记）。
*   **目标性状**：大麦棱型（Row-type，2-row vs 6-row），这是一个遗传结构相对清晰（包含主效基因和微效基因）的理想模型性状。
*   **基准方法（Benchmark）**：现代多位点GWAS方法 **FarmCPU** 和 **BLINK**。
*   **对比维度**：
    *   不同LD参数（$r^2 \in \{0.1, 0.3, 0.5\}$，$tol \in \{0, 1, 2, 3\}$）对定位的影响。
    *   rrBLUP与BayesR两种估计方法的差异。
    *   单标记与单倍型块在表型预测准确性上的差异。

### 4. 资源与算力
*   **软件环境**：使用 R 3.6.3 语言环境，涉及 `SelectionTools`、`GCTB v2.0`（用于BayesR）、`GAPIT v3`（用于GWAS）等工具。
*   **算力说明**：论文**未明确说明**具体的硬件配置（如GPU型号、CPU核心数）或具体的训练时长。由于涉及25,000次迭代的Gibbs采样（BayesR），计算量显著高于传统线性回归，但对于9,000个标记的规模，普通工作站即可胜任。

### 5. 实验数量与充分性
*   **实验规模**：
    *   测试了12种不同的LD分块参数组合。
    *   进行了5折交叉验证（80/20拆分）来评估预测准确性。
    *   针对随机标记和随机块进行了100次重复实验以排除偶然性。
*   **充分性评价**：实验设计非常充分。研究不仅验证了已知的主效基因（*VRS1*），还成功识别了GWAS漏检的已知微效基因（*VRS3*, *VRS5*），证明了该方法在处理复杂遗传结构时的优越性。

### 6. 主要结论与发现
*   **检测效力更高**：localGEBV成功检测到了分布在不同染色体上的多个已知QTL，而FarmCPU和BLINK仅能检测到效应最强的*VRS1*基因。
*   **预测能力更强**：使用单倍型块配置作为预测因子的准确性（LPM=0.88, GLM=0.81）显著高于单标记（LPM=0.75, GLM=0.71）。
*   **鲁棒性好**：localGEBV对标记效应的先验假设（rrBLUP vs BayesR）和分块参数具有良好的稳健性，虽然BayesR在主效位点上信号更尖锐，但rrBLUP在捕捉微效累积信号上更有优势。
*   **背景噪音低**：相比GWAS，localGEBV通过LD结构整合信号，显著降低了非QTL区域的背景噪音。

### 7. 优点
*   **桥接了GWAS与基因组选择**：将基因组预测的优势引入QTL定位，解决了信号分裂问题。
*   **灵活性**：允许研究者根据需求调整分块参数，实现从粗略定位到精细定位的转换。
*   **生物学解释性**：单倍型块比单标记更符合遗传演化规律（如重组热点和连锁遗传）。

### 8. 不足与局限
*   **效应类型限制**：目前的框架主要基于**加性效应**，尚未整合显性效应和上位性效应（尽管作者在讨论中提到了扩展的可能性）。
*   **依赖LD结构**：分块结果高度依赖于特定群体的历史重组和选择压力，不同群体间的单倍型块边界可能不一致，限制了跨群体的通用性。
*   **计算成本**：相比于极速的单标记扫描，基于贝叶斯迭代或岭回归的localGEBV计算成本更高，在超大规模数据集（如百万级标记）上的扩展性有待验证。

（完）
