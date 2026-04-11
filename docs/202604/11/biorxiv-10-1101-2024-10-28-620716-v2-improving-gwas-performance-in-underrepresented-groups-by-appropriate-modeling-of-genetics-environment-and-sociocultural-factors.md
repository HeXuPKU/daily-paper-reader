---
title: "Improving GWAS performance in underrepresented groups by appropriate modeling of genetics, environment, and sociocultural factors"
title_zh: 通过对遗传、环境和社会文化因素的适当建模，提高代表性不足群体中全基因组关联分析（GWAS）的表现
authors: "Cataldo-Ramirez, C., Lin, M., McMahon, A., Gignoux, C., Weaver, T. D., Henn, B. M."
date: 2026-04-08
pdf: "https://www.biorxiv.org/content/10.1101/2024.10.28.620716v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 针对代表性不足人群的GWAS和PGS遗传与环境建模
tldr: 针对生物样本库中非欧洲裔群体代表性不足的问题，本研究通过分析英国生物样本库（UKB）中南亚裔及混合族裔的遗传亲缘关系，利用支持向量机（SVM）重新划分族裔标签，增加了南亚样本量。研究进一步通过引入环境协变量优化身高GWAS模型，证明了在小样本量下也能获得与大规模训练集相当的多基因评分（PGS）预测性能，并减少了性别偏差，为提升少数族裔遗传研究效力提供了新思路。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-001.webp\", \"caption\": \"Figure 2. UKB self-selected ethnicity groups (UDI 21000) projected onto 1KG PCs 2 and 3. A) 1KG data 171 used in the PCA, colored by reference population. B - D) UKB data projected onto 1KG PC space, with B) 172\", \"page\": 6, \"index\": 1, \"width\": 1051, \"height\": 969}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-002.webp\", \"caption\": \"Table 2. Environmental variables included as covariates in GWASnull (italicized) and/or GWASenv (all 322 variables listed here). 323\", \"page\": 11, \"index\": 2, \"width\": 1054, \"height\": 759}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-003.webp\", \"caption\": \"Figure 3. Supervised ADMIXTURE output trained on 1KG data, for k = 7. A) 1KG populations used in the 195 unsupervised analyses. B) Supervised ADMIXTURE output grouped by the original UKB self-selected 196 ethnicity labels (UDI 21000). C) Supervised ADMIXTURE output grouped by SVM training group (n = 30; 197 left) and respective predicted group classifications (right) for UKB “White and Asian” and “Any other 198 Asian” identifying participants. Only groups with 30 or more SVM classifications are included in this 199\", \"page\": 7, \"index\": 3, \"width\": 1051, \"height\": 649}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-004.webp\", \"caption\": \"Table 5. Predictive performance of PGS scores. All models meet significance at p < 1 x 10-5. Extended 426 results can be found in Tables S2.12 and S2.13. 427\", \"page\": 14, \"index\": 4, \"width\": 929, \"height\": 288}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-005.webp\", \"caption\": \"Figure 6. Comparison of correlations between PGS score and participant height (n = 997). R2 values 420 (symbols) and 95% CI (solid lines) reflect PGS performance across the full test sample (left panel) and 421 sex stratified samples (right panel). Dashed lines connect R2 estimates between sex stratified samples to 422 help visualize biases in PGS performance. PGS models are designated by color and symbol, and are 423 consistent across panels. 424 425\", \"page\": 14, \"index\": 5, \"width\": 1051, \"height\": 409}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-006.webp\", \"caption\": \"Table 1. UK Biobank sample. 58\", \"page\": 3, \"index\": 6, \"width\": 1038, \"height\": 1162}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-007.webp\", \"caption\": \"Figure 5. Manhattan plots of significantly associated SNPs resulting from GWASnull (left panel) and 391 GWASenv (right panel). A significance threshold of p < 5-8 is designated by the dashed lines. The rsID for 392 the variants with the lowest p-value per peak is listed in the GWASenv panel. Regions with inflated 393 significance in GWASnull that are reduced in GWASenv are designated by asterisks in the GWASnull panel. 394 Alternatively, regions with increased significance in GWASenv in comparison to GWASnull are designated 395 by asterisks in the GWASenv panel. 396 397 Polygenic score (PGS) construction and assessments 398 Following the GWAS, we developed one height PGS model for each of the two GWAS 399 using LDpred2-auto [30, 31]. We assessed the overall performance of each model (GWASnull 400 PGS and GWASenv PGS) by calculating R2 between PGS and height, both with and without the 401 demographic or environmental covariates used in the associated GWAS, for UKB South Asian 402 participants held out from the sample prior to GWAS analyses (n = 997). We additionally 403\", \"page\": 13, \"index\": 7, \"width\": 939, \"height\": 930}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-008.webp\", \"caption\": \"Figure 4. Relationships between group labels and genetic affinities throughout the SVM pipeline, for UKB 261 participants who selected “Any other Asian” (AOA) or “White and Asian” (WA) as their ethnicity. 262 Participants with self-selected AOA or WA ethnic backgrounds (UKB data-field 21000) (left column) were 263 first assigned a group membership to one of the 13 reference populations used to train the SVM (AFR not 264 pictured), based on the highest classification probability assigned (middle column). Classification 265 probabilities for each participant were grouped by subcontinental region and summed. Those with a 266 summed subcontinental classification probability ≥ 0.7 were assigned to that group (right column). AOA 267\", \"page\": 9, \"index\": 8, \"width\": 997, \"height\": 904}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-28-620716-v2/fig-009.webp\", \"caption\": \"Figure 1. UKB BIP (middle column) and AOA and WA (right column) array data projected onto 1KG PC4 135 and PC7 space, when using standard QC thresholds for MAF (top row) and stringent MAF thresholds 136 (bottom row). For each plot, 1KG data are represented by open circles, BIP are represented by plus 137 signs, AOA are represented by filled diamonds, and WA are represented by filled circles. All data are 138 plotted in the left column, with UKB data grayed. BIP and 1KG data are plotted in the middle column, with 139 1KG data grayed. AOA, WA, and 1KG data are plotted in the right column, with 1KG data grayed. Top: 140 When using the full SNP intersection between UKB and 1KG data, PC4 and above are both driven by 141 European genetic variation (See SI Section 1.2.3 for more information). Bottom: when more stringent 142 MAF thresholds are used to filter out all but common SNPs (i.e., variants with MAF > 0.1 retained), PC4 is 143 driven by East Asian genetic variation and PC7 is driven by South Asian genetic variation. Standard QC 144 thresholds for filtering UKB array data will emphasize structure within European axes of variation and may 145 only be appropriate for addressing within-sample structure if just the first three PCs are being considered. 146 However, this may bias the interpretation of relative genetic variance within the sample data as well as 147 patterns of global population structure (therefore also biasing attempts to characterize genetic ancestry). 148 149 UKB Bangladeshi, Indian, and Pakistani Principal Components Analysis (PCA) 150 UKB Bangladeshi, Indian, and Pakistani (BIP) participants generally cluster closer to one 151 another and to 1KG South Asian reference groups than to other reference populations included 152 in the global PCA. The UKB Indian group demonstrates the highest variance in scores across 153 PCs, suggesting the highest levels of genetic diversity of the UKB BIP groups (Fig. 2; SI Section 154 1.3.1, Fig. S1.6-S1.8), although they also comprise the largest sub-sample, possibly 155 confounding this interpretation. Across PCs, the Pakistani scores fall within the Indian ranges, 156 making them largely indistinguishable from Indian-identifying participants. In 5 of the 20 157\", \"page\": 5, \"index\": 9, \"width\": 1051, \"height\": 760}]"
motivation: 解决当前全基因组关联分析（GWAS）中非欧洲裔群体数据匮乏且利用率低，导致遗传预测模型存在偏差的问题。
method: 利用支持向量机对模糊族裔标签进行遗传聚类重分类以扩大样本量，并结合环境协变量构建优化的GWAS模型。
result: "重新分配增加了1,381名南亚裔样本，且环境调整后的PGS在预测性能上可比肩更大规模的传统模型，并有效降低了性别偏倚。"
conclusion: 通过合理利用模糊族裔数据、匹配祖先参考面板及整合环境因素，可以显著提升少数族裔GWAS的分析效能和预测准确性。
---

## 摘要
全基因组关联分析（GWAS）和多基因评分（PGS）的开发通常受限于生物样本库中的可用数据，其中欧洲血统队列占据了绝大部分。在本研究中，我们通过表征英国生物样本库（UKB）中自我标识为孟加拉国人、印度人、巴基斯坦人、“白人与亚洲人混血”（WA）以及“任何其他亚洲人”（AOA）受试者的遗传亲缘关系，提高了 UKB 中非欧洲裔受试者数据的利用率，旨在为未来的遗传分析建立更稳健的南亚裔样本量。我们评估了遗传结构与自我选择的族裔身份之间的关系，并利用数据集中一致的聚类模式训练了一个支持向量机（SVM）。该 SVM 被用于在次大陆层面重新分配 1,853 名 AOA 和 WA 受试者，使 UKB 南亚裔群体的样本量增加了 1,381 人。我们进一步利用这些样本来评估 GWAS 的表现和 PGS 的开发。我们通过执行严格的协变量选择程序，在身高 GWAS 中纳入了环境协变量，并比较了两种 GWAS 模型（GWASnull 和 GWASenv）的输出。结果表明，源自这两种 GWAS 模型的 PGS 表现与使用大一个数量级的训练集开发的 PGS 模型具有相当的预测能力，且经过环境调整的 PGS 模型减少了预测表现中的性别偏差。总之，我们展示了如何通过利用模糊的族裔代码、祖源匹配的填充面板以及纳入环境协变量来提高 GWAS 的表现。

## Abstract
Genome-wide association studies (GWAS) and polygenic score (PGS) development are typically constrained by the data available in biobank repositories in which European cohorts are vastly overrepresented. Here, we increase the utility of non-European participant data within the UK Biobank (UKB) by characterizing the genetic affinities of UKB participants who self-identify as Bangladeshi, Indian, Pakistani, "White and Asian" (WA), and "Any Other Asian" (AOA), towards creating a more robust South Asian sample size for future genetic analyses. We assess the relationships between genetic structure and self-selected ethnic identities and use consistent patterns of clustering in the dataset to train a support vector machine (SVM). The SVM was utilized to reassign n = 1,853 AOA and WA participants at the subcontinental level, and increase the sample size of the UKB South Asian group by 1,381 additional participants. We further leverage these samples to assess GWAS performance and PGS development. We include environmental covariates in the height GWAS by implementing a rigorous covariate selection procedure, and compare the outputs of two GWAS models: GWASnull and GWASenv. We show that PGS performance derived from both GWAS models yield comparable prediction to PGS models developed with an order of magnitude larger training, and environmentally-adjusted PGS models reduce the sex-bias in predictive performance. In summary, we demonstrate how GWAS performance can be improved by leveraging ambiguous ethnicity codes, ancestry matched imputation panels, and including environmental covariates.

---

## 论文详细总结（自动生成）

### 论文总结：通过遗传、环境和社会文化建模提升少数族裔 GWAS 表现

#### 1. 核心问题与整体含义（研究动机和背景）
全基因组关联分析（GWAS）和多基因评分（PGS）目前存在严重的“欧洲中心主义”偏差，绝大多数数据源自欧洲裔群体。这导致非欧洲裔群体的遗传研究效力不足，PGS 跨人群迁移性差。论文的核心动机是：**在非欧洲裔样本量有限的现状下，如何通过更精细的遗传亲缘关系表征和环境因素建模，最大化现有生物样本库（如 UK Biobank）中少数族裔数据的科研价值。**

#### 2. 方法论
论文提出了一套整合遗传与环境信息的分析框架：
*   **遗传亲缘关系重构：**
    *   **纠正芯片选择偏倚（Ascertainment Bias）：** 发现 UKB 基因芯片设计偏向欧洲裔，标准质控（MAF 0.01-0.05）会放大欧洲裔的遗传异质性。研究改用更严格的 MAF > 0.1 过滤，以恢复全球遗传多样性模式。
    *   **SVM 族裔重分类：** 利用支持向量机（SVM）对 1000 Genomes（1KG）参考面板和 UKB 已知族裔进行训练，对标签模糊的“任何其他亚洲人”（AOA）和“白人与亚洲人混血”（WA）受试者进行次大陆级别的重新分配，从而扩大南亚裔（SAS）分析样本。
*   **环境协变量建模：**
    *   **协变量筛选与填充：** 从 283 个数据字段中筛选出 9 个与身高发育相关的环境因子（如饮食、社会经济地位、出生地、整体健康状况等）。
    *   **多重插补（MICE）：** 使用链式方程多重插补处理缺失数据，确保样本量最大化。
*   **GWAS 与 PGS 构建：**
    *   对比了基础模型（`GWAS_null`，仅含年龄、性别、主成分）和环境增强模型（`GWAS_env`）。
    *   使用 **LDpred2-auto** 算法开发 PGS，该算法无需验证集即可推断遗传力。

#### 3. 实验设计
*   **数据集：** 英国生物样本库（UK Biobank）中的南亚裔子集（包括孟加拉国、印度、巴基斯坦裔及重分类后的 AOA/WA 受试者）。
*   **Benchmark（基准）：** 
    *   **Yengo et al. (2022)** 发表的南亚裔身高 PGS（PGS002800），该模型基于约 7.8 万人的元分析，样本量比本研究大一个数量级。
*   **对比方法：** 比较了 `GWAS_null` 与 `GWAS_env` 在显著位点检测、效应值（Beta）精确度、以及 PGS 预测准确度（$R^2$）上的差异。

#### 4. 资源与算力
*   论文**未明确说明**具体的硬件配置（如 GPU 型号或数量）。
*   软件工具链包括：PLINK v2.0、GCTA（用于 MLMA-LOCO 分析）、FRAPOSA（祖先预测）、LDpred2（R 包 bigsnpr）、MICE（R 包）。

#### 5. 实验数量与充分性
*   **实验规模：** 研究对 8,178 名南亚裔受试者进行了遗传亲缘分析，最终在约 7,000 人的样本中进行 GWAS，并留出约 1,000 人作为 PGS 测试集。
*   **充分性：** 实验设计较为充分。作者不仅进行了常规的 PCA 和 ADMIXTURE 分析，还引入了 SVM 定量分类，并针对环境协变量进行了 5 次独立插补后的池化分析（Rubin's rules）。通过与超大规模元分析结果的对比，验证了小样本模型的高效性。

#### 6 主要结论与发现
*   **样本量提升：** 通过对模糊族裔标签（AOA/WA）的遗传重分类，使南亚裔分析样本量增加了 **20%**（1,381 人）。
*   **GWAS 优化：** 纳入环境协变量后，显著位点的检测能力提升，基因组膨胀系数（$\lambda$）降低，SNP 效应值的标准误减小，表明模型更精确。
*   **PGS 表现：** 本研究基于约 7,000 人构建的 PGS，其预测表现与基于 7.8 万人构建的基准模型**相当**。
*   **性别偏倚减少：** 环境调整后的 PGS 模型显著缩小了男女受试者之间预测准确度的差异。

#### 7. 优点
*   **数据挖掘深度：** 成功利用了以往因标签模糊而被排除的“混血”或“其他”类别数据。
*   **偏倚纠正：** 敏锐察觉并解决了基因芯片设计带来的欧洲中心主义选择偏倚问题。
*   **跨学科整合：** 将人类学背景下的社会文化因素（如饮食习惯、出生地）转化为生物统计模型中的有效协变量。

#### 8. 不足与局限
*   **样本量瓶颈：** 尽管有所增加，但相对于欧洲裔动辄数十万的样本，数千人的规模在发现极微效位点上仍显不足。
*   **环境数据局限：** UKB 的环境数据多为成年后的自我回顾报告，可能无法完全代表儿童发育期的关键暴露。
*   **碰撞偏倚风险：** 纳入“整体健康状况”等可能受身高影响的变量作为协变量，理论上存在诱发碰撞偏倚（Collider Bias）的风险，尽管作者进行了讨论和控制。
*   **地域限制：** 研究对象仅限于英国境内的南亚裔移民，其结论在南亚本土人群中的适用性仍需验证。

（完）
