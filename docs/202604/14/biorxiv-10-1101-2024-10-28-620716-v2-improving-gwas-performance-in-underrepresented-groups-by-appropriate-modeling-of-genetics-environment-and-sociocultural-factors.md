---
title: "Improving GWAS performance in underrepresented groups by appropriate modeling of genetics, environment, and sociocultural factors"
title_zh: 通过对遗传、环境和社会文化因素的适当建模，提高代表性不足群体中全基因组关联研究（GWAS）的表现
authors: "Cataldo-Ramirez, C., Lin, M., McMahon, A., Gignoux, C., Weaver, T. D., Henn, B. M."
date: 2026-04-08
pdf: "https://www.biorxiv.org/content/10.1101/2024.10.28.620716v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 通过建模提高多样化人群中GWAS和PGS的性能
tldr: 本研究针对生物样本库中非欧洲裔群体代表性不足的问题，以英国生物样本库（UKB）中的南亚裔人群为对象，通过支持向量机（SVM）重新分类模糊族裔代码，增加了样本量。研究结合环境协变量优化了全基因组关联分析（GWAS）模型，并开发了多基因评分（PGS）。结果表明，通过精细化建模和样本扩充，即使在较小样本量下也能显著提升GWAS性能并减少PGS的性别偏倚，为改善少数族裔遗传研究提供了新思路。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-001.webp\", \"caption\": \"Figure 2. UKB self-selected ethnicity groups (UDI 21000) projected onto 1KG PCs 2 and 3. A) 1KG data 171 used in the PCA, colored by reference population. B - D) UKB data projected onto 1KG PC space, with B) 172\", \"page\": 6, \"index\": 1, \"width\": 1051, \"height\": 969}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-002.webp\", \"caption\": \"Table 2. Environmental variables included as covariates in GWASnull (italicized) and/or GWASenv (all 322 variables listed here). 323\", \"page\": 11, \"index\": 2, \"width\": 1054, \"height\": 759}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-003.webp\", \"caption\": \"Figure 3. Supervised ADMIXTURE output trained on 1KG data, for k = 7. A) 1KG populations used in the 195 unsupervised analyses. B) Supervised ADMIXTURE output grouped by the original UKB self-selected 196 ethnicity labels (UDI 21000). C) Supervised ADMIXTURE output grouped by SVM training group (n = 30; 197 left) and respective predicted group classifications (right) for UKB “White and Asian” and “Any other 198 Asian” identifying participants. Only groups with 30 or more SVM classifications are included in this 199\", \"page\": 7, \"index\": 3, \"width\": 1051, \"height\": 649}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-004.webp\", \"caption\": \"Table 5. Predictive performance of PGS scores. All models meet significance at p < 1 x 10-5. Extended 426 results can be found in Tables S2.12 and S2.13. 427\", \"page\": 14, \"index\": 4, \"width\": 929, \"height\": 288}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-005.webp\", \"caption\": \"Figure 6. Comparison of correlations between PGS score and participant height (n = 997). R2 values 420 (symbols) and 95% CI (solid lines) reflect PGS performance across the full test sample (left panel) and 421 sex stratified samples (right panel). Dashed lines connect R2 estimates between sex stratified samples to 422 help visualize biases in PGS performance. PGS models are designated by color and symbol, and are 423 consistent across panels. 424 425\", \"page\": 14, \"index\": 5, \"width\": 1051, \"height\": 409}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-006.webp\", \"caption\": \"Table 1. UK Biobank sample. 58\", \"page\": 3, \"index\": 6, \"width\": 1038, \"height\": 1162}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-007.webp\", \"caption\": \"Figure 5. Manhattan plots of significantly associated SNPs resulting from GWASnull (left panel) and 391 GWASenv (right panel). A significance threshold of p < 5-8 is designated by the dashed lines. The rsID for 392 the variants with the lowest p-value per peak is listed in the GWASenv panel. Regions with inflated 393 significance in GWASnull that are reduced in GWASenv are designated by asterisks in the GWASnull panel. 394 Alternatively, regions with increased significance in GWASenv in comparison to GWASnull are designated 395 by asterisks in the GWASenv panel. 396 397 Polygenic score (PGS) construction and assessments 398 Following the GWAS, we developed one height PGS model for each of the two GWAS 399 using LDpred2-auto [30, 31]. We assessed the overall performance of each model (GWASnull 400 PGS and GWASenv PGS) by calculating R2 between PGS and height, both with and without the 401 demographic or environmental covariates used in the associated GWAS, for UKB South Asian 402 participants held out from the sample prior to GWAS analyses (n = 997). We additionally 403\", \"page\": 13, \"index\": 7, \"width\": 939, \"height\": 930}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-008.webp\", \"caption\": \"Figure 4. Relationships between group labels and genetic affinities throughout the SVM pipeline, for UKB 261 participants who selected “Any other Asian” (AOA) or “White and Asian” (WA) as their ethnicity. 262 Participants with self-selected AOA or WA ethnic backgrounds (UKB data-field 21000) (left column) were 263 first assigned a group membership to one of the 13 reference populations used to train the SVM (AFR not 264 pictured), based on the highest classification probability assigned (middle column). Classification 265 probabilities for each participant were grouped by subcontinental region and summed. Those with a 266 summed subcontinental classification probability ≥ 0.7 were assigned to that group (right column). AOA 267\", \"page\": 9, \"index\": 8, \"width\": 997, \"height\": 904}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-009.webp\", \"caption\": \"Figure 1. UKB BIP (middle column) and AOA and WA (right column) array data projected onto 1KG PC4 135 and PC7 space, when using standard QC thresholds for MAF (top row) and stringent MAF thresholds 136 (bottom row). For each plot, 1KG data are represented by open circles, BIP are represented by plus 137 signs, AOA are represented by filled diamonds, and WA are represented by filled circles. All data are 138 plotted in the left column, with UKB data grayed. BIP and 1KG data are plotted in the middle column, with 139 1KG data grayed. AOA, WA, and 1KG data are plotted in the right column, with 1KG data grayed. Top: 140 When using the full SNP intersection between UKB and 1KG data, PC4 and above are both driven by 141 European genetic variation (See SI Section 1.2.3 for more information). Bottom: when more stringent 142 MAF thresholds are used to filter out all but common SNPs (i.e., variants with MAF > 0.1 retained), PC4 is 143 driven by East Asian genetic variation and PC7 is driven by South Asian genetic variation. Standard QC 144 thresholds for filtering UKB array data will emphasize structure within European axes of variation and may 145 only be appropriate for addressing within-sample structure if just the first three PCs are being considered. 146 However, this may bias the interpretation of relative genetic variance within the sample data as well as 147 patterns of global population structure (therefore also biasing attempts to characterize genetic ancestry). 148 149 UKB Bangladeshi, Indian, and Pakistani Principal Components Analysis (PCA) 150 UKB Bangladeshi, Indian, and Pakistani (BIP) participants generally cluster closer to one 151 another and to 1KG South Asian reference groups than to other reference populations included 152 in the global PCA. The UKB Indian group demonstrates the highest variance in scores across 153 PCs, suggesting the highest levels of genetic diversity of the UKB BIP groups (Fig. 2; SI Section 154 1.3.1, Fig. S1.6-S1.8), although they also comprise the largest sub-sample, possibly 155 confounding this interpretation. Across PCs, the Pakistani scores fall within the Indian ranges, 156 making them largely indistinguishable from Indian-identifying participants. In 5 of the 20 157\", \"page\": 5, \"index\": 9, \"width\": 1051, \"height\": 760}]"
motivation: 旨在解决当前全基因组关联分析（GWAS）中非欧洲裔群体数据匮乏且代表性不足，导致遗传预测模型在这些群体中表现不佳的问题。
method: 利用支持向量机（SVM）对具有模糊族裔身份的参与者进行亚大陆级别的重新分类以扩大样本量，并引入环境协变量构建严谨的GWAS模型。
result: "成功增加了1,381名南亚裔样本，且基于环境调整后的GWAS模型开发的PGS在预测性能上可媲美更大规模的训练集，并有效减少了性别偏倚。"
conclusion: 通过整合模糊族裔数据、匹配祖先填充面板及纳入环境协变量，可以显著提升少数族裔群体的GWAS效能和多基因评分的准确性。
---

## 摘要
全基因组关联研究（GWAS）和多基因评分（PGS）的开发通常受限于生物样本库中可用的数据，而在这些样本库中，欧洲队列的比例过高。在本文中，我们通过表征在英国生物样本库（UKB）中自我认同为孟加拉国人、印度人、巴基斯坦人、“白人与亚洲人混血”（WA）以及“任何其他亚洲人”（AOA）的参与者的遗传亲缘关系，提高了 UKB 中非欧洲参与者数据的效用，旨在为未来的遗传分析建立更稳健的南亚样本量。我们评估了遗传结构与自选种族身份之间的关系，并利用数据集中一致的聚类模式训练了一个支持向量机（SVM）。利用该 SVM 在次大陆层面重新分配了 n = 1,853 名 AOA 和 WA 参与者，使 UKB 南亚组的样本量增加了 1,381 人。我们进一步利用这些样本来评估 GWAS 的表现和 PGS 的开发。通过执行严格的协变量选择程序，我们在身高 GWAS 中纳入了环境协变量，并比较了两种 GWAS 模型（GWASnull 和 GWASenv）的输出。我们表明，从这两种 GWAS 模型中得出的 PGS 表现与使用大一个数量级的训练集开发的 PGS 模型具有相当的预测能力，且经过环境调整的 PGS 模型减少了预测表现中的性别偏差。总之，我们展示了如何通过利用模糊的种族代码、祖源匹配的填充面板以及纳入环境协变量来提高 GWAS 的表现。

## Abstract
Genome-wide association studies (GWAS) and polygenic score (PGS) development are typically constrained by the data available in biobank repositories in which European cohorts are vastly overrepresented. Here, we increase the utility of non-European participant data within the UK Biobank (UKB) by characterizing the genetic affinities of UKB participants who self-identify as Bangladeshi, Indian, Pakistani, "White and Asian" (WA), and "Any Other Asian" (AOA), towards creating a more robust South Asian sample size for future genetic analyses. We assess the relationships between genetic structure and self-selected ethnic identities and use consistent patterns of clustering in the dataset to train a support vector machine (SVM). The SVM was utilized to reassign n = 1,853 AOA and WA participants at the subcontinental level, and increase the sample size of the UKB South Asian group by 1,381 additional participants. We further leverage these samples to assess GWAS performance and PGS development. We include environmental covariates in the height GWAS by implementing a rigorous covariate selection procedure, and compare the outputs of two GWAS models: GWASnull and GWASenv. We show that PGS performance derived from both GWAS models yield comparable prediction to PGS models developed with an order of magnitude larger training, and environmentally-adjusted PGS models reduce the sex-bias in predictive performance. In summary, we demonstrate how GWAS performance can be improved by leveraging ambiguous ethnicity codes, ancestry matched imputation panels, and including environmental covariates.

---

## 论文详细总结（自动生成）

这是一份关于论文《Improving GWAS performance in underrepresented groups by appropriate modeling of genetics, environment, and sociocultural factors》的结构化分析报告：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：当前的基因组研究（如GWAS和多基因评分PGS）存在严重的“欧洲中心主义”偏见。由于生物样本库中非欧洲裔群体样本量小且族裔分类模糊，研究者往往认为这些数据无法产生有意义的结果，导致少数族裔在精准医疗中被进一步边缘化。
*   **整体含义**：本研究旨在证明，通过**精细化的遗传亲缘关系表征**（挖掘模糊族裔数据）和**纳入环境/社会文化协变量**，即使在样本量较小的情况下，也能显著提升非欧洲裔群体GWAS的预测效能，并减少预测结果中的性别偏倚。

### 2. 方法论：核心思想与关键技术
*   **样本扩充（SVM分类）**：
    *   针对UK Biobank（UKB）中身份标签模糊的“任何其他亚洲人”（AOA）和“白人与亚洲人混血”（WA）群体，利用支持向量机（SVM）基于前15个主成分（PCs）进行训练。
    *   将这些模糊样本重新分配到亚大陆级别的遗传群体中，成功为南亚裔（South Asian）分析组增加了1,381名参与者（样本量提升约20%）。
*   **纠正芯片祖源偏倚（Ascertainment Bias）**：
    *   发现UKB的SNP芯片设计偏向欧洲人群，导致低频变异在非欧洲人群中无法准确反映遗传多样性。
    *   **关键技术**：采用极其严格的最小等位基因频率（MAF > 0.1）过滤，以恢复全球遗传多样性的真实模式，确保主成分分析（PCA）能准确反映南亚内部的群体结构。
*   **环境协变量建模（GWASenv）**：
    *   核心思想：身高受发育期营养和环境影响巨大。
    *   技术细节：通过多重插补（MICE）处理缺失值，筛选出9个关键协变量（如：出生地是否在英国、是否摄入乳制品/肉类、Townsend剥夺指数、自我评估健康状况等）纳入线性混合模型（GCTA MLMA-LOCO）。

### 3. 实验设计与对比
*   **数据集**：
    *   主要分析对象：UKB南亚裔群体（包括孟加拉、印度、巴基斯坦及SVM重新分类后的样本）。
    *   参考面板：1000 Genomes (1KG) 全球样本、Genome Asia 100K (GAsP) 填充面板。
*   **对比模型（Benchmark）**：
    *   **GWASnull**：传统模型，仅包含性别、年龄和遗传主成分（PCs）。
    *   **GWASenv**：在null基础上加入环境/社会文化协变量。
    *   **外部基准**：对比了 Yengo 等人 (2022) 发表的南亚裔身高PGS（其训练样本量约为本研究的10倍）。

### 4. 资源与算力
*   **算力说明**：论文未详细列出具体的硬件型号（如GPU/CPU核心数）或具体的训练时长。
*   **软件工具**：使用了 Michigan Imputation Server 进行基因型填充，计算工具包括 PLINK v2.0、GCTA、LDpred2-auto（R包 bigsnpr）以及用于环境数据插补的 MICE 包。

### 5. 实验数量与充分性
*   **实验规模**：
    *   对约7,000名南亚裔样本进行了身高GWAS分析。
    *   进行了5次环境数据多重插补的并行GWAS并汇总结果（遵循Rubin规则）。
    *   进行了性别分层分析以评估PGS的性别偏倚。
*   **充分性评价**：实验设计较为充分。研究不仅关注了遗传层面的分类，还深入探讨了环境因子的遗传力（h2）及其可能带来的碰撞偏倚（Collider Bias），并与目前领域内最大规模的同类研究进行了直接性能对比，逻辑闭环完整。

### 6. 主要结论与发现
*   **样本挖掘有效性**：SVM分类证明了“族裔标签”与“遗传亲缘”并不完全等同，成功从模糊标签中提取了大量可用的南亚遗传样本。
*   **GWAS性能提升**：GWASenv模型相比传统模型检测到了更多的显著位点，减少了基因组膨胀（λ值更小），且SNP效应值的标准误（SE）普遍降低，估算更精确。
*   **PGS预测力**：本研究利用约7,000人训练出的PGS，其预测准确度（R²）与利用77,000人训练的外部模型相当。
*   **性别偏倚减少**：环境调整后的模型显著缩小了男性和女性在PGS预测表现上的差异。

### 7. 优点与亮点
*   **数据利用率极高**：通过算法手段挽救了原本因标签模糊而被剔除的少数族裔数据。
*   **跨学科建模**：将人类学、社会学背景下的环境因子（如饮食习惯、社会剥夺感）引入硬核遗传学模型，证明了环境建模在复杂性状研究中的必要性。
*   **偏倚纠正意识**：敏锐察觉并解决了芯片设计带来的祖源偏倚问题，这对非欧洲裔遗传研究具有重要的参考价值。

### 8. 不足与局限
*   **回顾性偏差**：UKB的环境数据多为成年后的自我报告，可能无法完全代表影响身高关键期（童年/青春期）的真实环境。
*   **碰撞偏倚风险**：虽然作者讨论了协变量的遗传力，但纳入“自我评估健康状况”等具有一定遗传力的变量作为协变量，理论上仍存在诱发碰撞偏倚、导致遗传效应估算偏差的风险。
*   **样本量局限**：尽管性能有所提升，但绝对样本量（n≈7,000）对于发现极微小效应的变异仍显不足，且研究仅限于“身高”这一高遗传力性状，在其他复杂疾病上的普适性有待验证。

（完）
