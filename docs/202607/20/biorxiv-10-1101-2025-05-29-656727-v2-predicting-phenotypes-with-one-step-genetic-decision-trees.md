---
title: Predicting phenotypes with one step genetic decision trees
title_zh: 一步遗传决策树预测表型
authors: "Blommaert, J., Bayer, P. E., Ashton, D. T., Samuels, G., Jesson, L., Wellenreuther, M."
date: 2026-07-19
pdf: "https://www.biorxiv.org/content/10.1101/2025.05.29.656727v2.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 遗传决策树用于表型预测，与PRS/GS预测算法相关
tldr: "传统基因组预测受限于表型记录和线性模型。本文采用高通量图像表型提取13个尺寸测量，结合GWAS、GBLUP和XGBoost对澳洲鲷鱼进行关联分析和性状预测。共鉴定28个生长相关SNP，GBLUP和XGBoost在训练集R²分别为0.50和0.77，但测试集降至0.11，考虑亲缘后仅0.06；模型捕获约20%遗传方差。研究展示了计算机视觉与机器学习在遗传育种中的潜力，同时揭示了种群结构和亲缘关系对预测精度的挑战。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-05-29-656727-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1923, \"height\": 908, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-05-29-656727-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1762, \"height\": 1593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-05-29-656727-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1951, \"height\": 832, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-05-29-656727-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1602, \"height\": 2703, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-05-29-656727-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1924, \"height\": 1980, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-05-29-656727-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1667, \"height\": 2755, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-05-29-656727-v2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1596, \"height\": 2595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-05-29-656727-v2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1931, \"height\": 2001, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-05-29-656727-v2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1941, \"height\": 872, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-1101-2025-05-29-656727-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 651, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-1101-2025-05-29-656727-v2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1595, \"height\": 869, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-1101-2025-05-29-656727-v2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1340, \"height\": 302, \"label\": \"Table\"}]"
motivation: 传统基因组预测受限于表型记录和线性模型，需要整合高通量表型和机器学习提升预测能力。
method: 对澳洲鲷鱼使用图像提取13个尺寸特征，进行GWAS、GBLUP和XGBoost模型预测与特征重要性分析。
result: "鉴定28个生长相关SNP；GBLUP和XGBoost在训练集R²达0.50和0.77，测试集降至0.11，考虑亲缘后为0.06；捕获约20%遗传方差。"
conclusion: 计算机视觉表型结合机器学习有效检测遗传信号，但种群结构限制了基因组预测精度，需改进方法。
---

## 摘要
当表型记录受限且使用线性模型时，复杂性状的基因组预测能力有限。通过高通量、基于图像的表型分析增加表型数据量，可以提高基因组预测效果并增强变异检测中的信号。本研究分析了来自选择性繁殖的澳大利亚鲷（Chrysophrys auratus）群体的表型和基因组数据，以鉴定与生长性状相关的遗传变异。我们使用高通量表型分析流程从图像中提取了13个大小测量值。分析了图像衍生性状与手动测量性状（体重、叉长）之间的表型相关性以及遗传力。所有测量值之间均呈显著正相关，遗传力范围在0.20-0.38之间。全基因组关联研究（GWAS）鉴定了28个与生长相关的SNP，同时使用GBLUP预测表型，并利用XGBoost机器学习模型联合预测表型及报告重要变异。GBLUP（平均R²=0.50）和XGBoost（平均R²=0.77）在训练数据上表现良好，但在测试集上性能下降（两者均为0.11），当考虑遗传相关性时进一步下降（两者均为0.06）。尽管如此，模型捕获了约20%的生长性状遗传方差，且XGBoost的特征重要性反映了GWAS中观察到的信号。我们的发现强调了将基于计算机视觉的表型分析与GWAS、GBLUP及机器学习相结合用于性状预测的实用性。尽管检测到了与GWAS共享的生物学信号，但基因组预测面临着群体结构和相关性等挑战，这些挑战存在于包括许多水生物种在内的群体产卵物种的育种计划中。

## Abstract
Genomic prediction of complex traits is limited when phenotype records are restricted and when using linear models. Increasing the amount of phenotypic data with high-throughput, image-based phenotyping could result in better genomic prediction and stronger signals in variant detection. Here, we analysed phenotypic and genomic data from a selectively bred cohort of the Australasian snapper (Chrysophrys auratus) to identify genetic variants associated with growth traits. We used a high-throughput phenotyping pipeline to extract 13 measurements of size from images. Phenotypic correlations among image-derived and manually measured traits (weight, fork length), together with heritabilities, were analysed. All measurements were significantly positively correlated with each other, and heritability ranged from 0.20-0.38. Genome-wide association studies (GWAS) identified 28 growth-associated SNPs, while GBLUP was used to predict phenotypes, and XGBoost machine-learning models were used to jointly predict phenotypes and report important variants. Both GBLUP (mean R2 = 0.50) and XGBoost (mean R2 = 0.77) performed well on the training data, but performance dropped on testing sets (both = 0.11), which decreased further when accounting for genetic relatedness (both = 0.06). Despite this, approximately 20% of the genetic variance for growth traits was captured by the models, and feature importance from XGBoost reflected signals seen in GWAS. Our findings highlight the utility of integrating computer vision-based phenotyping with GWAS, GBLUP, and ML for trait prediction. Despite detecting shared biological signals as GWAS, genomic prediction faces challenges with population structure and relatedness that are inherent in breeding programmes of mass spawning species, including many aquatic species.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）

- **核心问题**：传统基因组预测（如GBLUP）受限于表型记录数量有限且依赖线性模型，难以捕捉复杂性状中的非加性效应（如上位性）。同时，水产养殖中表型采集成本高、劳动强度大，成为育种效率的瓶颈。
- **研究动机**：利用高通量、基于计算机视觉的表型提取技术增加表型数据维度，并结合机器学习（如XGBoost）来同时进行表型预测与重要变异发现，以期超越线性模型的性能上限。
- **整体含义**：以澳大利亚鲷（*Chrysophrys auratus*）为模型，证明将图像表型、GWAS、GBLUP与XGBoost集成能够捕获共享的生物学信号，但群体结构和亲缘关系（特别是群体产卵物种固有的繁殖偏倚）严重限制了预测泛化能力。

### 论文提出的方法论

- **核心思想**：先通过图像自动测量获得13个生长相关形态指标，再利用线性（GBLUP、GWAS）和非线性（XGBoost）模型进行基因组预测与关联分析，并比较两类方法在训练/测试集上的表现及特征重要性的一致性。
- **关键技术细节**：
  - **图像表型**：计算机视觉管道提取鱼体长度、面积、高度等13个测量值，加上手动测量的体重和叉长，共15个性状，并计算表型PC1（解释97.16%变异）。
  - **基因型数据**：使用多物种SNP芯片，经质量控制后保留11,006个SNP；构建基因组关系矩阵（GRM），通过k-means聚类（k=19）将个体分为19个亲缘簇。
  - **遗传力估计**：采用ASReml-R中的REML方法，窄义遗传力范围0.20–0.38。
  - **GWAS**：采用rMVP包中的GLM、MLM和FarmCPU三种模型，以Bonferroni校正确定显著性阈值，重点分析FarmCPU结果。
  - **GBLUP**：以GRM作为随机效应，在随机个体划分（80:20）和基于亲缘簇划分两种策略下进行50次重复，计算R²和RMSE。
  - **XGBoost**：使用tidymodels框架进行超参数调优（5折内部交叉验证），特征包括所有SNP、PCA分量（2–6个）和亲缘簇标签；采用早期停止（20轮无改善后停止）和拉丁超立方采样搜索20组参数组合。
- **公式或算法流程**：未给出具体公式，但关键公式包括Ne估计：  
  \(N_e = \frac{1}{3(\bar{r}_{inter}^2 - \frac{1}{n})}\)  
  以及GBLUP混合模型、XGBoost回归目标（RMSE）和特征重要性（增益，Gain）。

### 实验设计

- **数据集**：来自F4代选择性育种群体的1011条澳大利亚鲷，图像表型（13个计算机视觉测量+2个手动测量）和SNP芯片数据（11,006个SNP）。
- **基准**：以GBLUP为线性基线，XGBoost为非线性方法；另以GLM、MLM和FarmCPU为GWAS基线。
- **对比方法**：
  - 预测性能：GBLUP vs. XGBoost
  - 关联信号：GWAS（FarmCPU）vs. XGBoost特征重要性
  - 数据划分策略：随机个体划分 vs. 基于亲缘簇划分（减少数据泄漏）
- **评估指标**：R²、RMSE、遗传力捕获比例（约20%）；特征重要性中的增益（Gain）与跨折叠选择频率。

### 资源与算力

- 文中**未明确说明**所使用的GPU型号、数量或训练时长。仅提及使用了R包（ASReml、xgboost、tidymodels等）进行建模，未涉及深度学习网络或大规模并行计算资源。推断实验可在普通工作站上完成。

### 实验数量与充分性

- **实验数量**：
  - GWAS：对15个性状+PC1共16个响应变量，每个采用3种模型（GLM/MLM/FarmCPU）。
  - GBLUP：5个代表性性状（体重、长度、PC1、眼宽、75%高度） × 2种数据划分策略 × 50次重复 = 500次。
  - XGBoost：同上面5个性状 × 2种划分策略 × 50次重复 = 500次，每次含5折内部调优。
  - 特征重要性分析：对所有50次重复的SNP选择频率和增益进行汇总和统计检验（Mann-Whitney U、bootstrap CI）。
- **充分性**：实验量较大，重复次数（50次）保证了稳定性估计；覆盖了不同遗传力、数据划分策略和模型类别。**但缺少跨群体验证（如独立野生群体或不同世代），且仅有一个物种和一个F4世代，限制了结论的普适性。**
- **公平性**：GBLUP与XGBoost在相同数据划分和重复种子下比较，计算R²和RMSE；亲缘簇划分策略显著降低了数据泄漏，使比较更客观。但XGBoost的超参数搜索空间较窄（20组），可能未达到最优。

### 论文的主要结论与发现

1. **图像表型显著增加了表型维度**：计算机视觉提取的13个测量值与手动测量高度相关（R²>0.9），且通过GWAS检测到比仅用体重/长度更多的关联SNP（29个 vs. 更少）。
2. **遗传力中等**：15个性状narrow-sense h²在0.20–0.38之间。
3. **GWAS鉴定29个生长相关SNP**，其中9个在多性状中共有，位于16条染色体；富集到Hox9a:meis1a、Sox-10、p53等转录因子靶基因。
4. **GBLUP与XGBoost在训练集上性能高（R²=0.50–0.77），但测试集大幅下降（随机划分R²≈0.11，亲缘簇划分R²≈0.06）**，仅捕获约20%遗传方差。说明过拟合严重，主要由群体结构和低有效群体大小（Ne=18–57）导致。
5. **XGBoost的稳定特征与GWAS信号高度一致**，表明机器学习能复现线性分析结果的生物学热点，但未能因捕获非加性效应而提升预测精度。
6. **群体结构和亲缘关系是基因组预测的主要障碍**，在群体产卵物种中尤为突出；未来需要优化育种设计或采用更复杂的混杂控制方法。

### 优点

1. **将计算机视觉表型与多种基因组方法系统集成**：展示了自动化表型如何放大GWAS检测效力，并促进多性状联合分析。
2. **严格区分数据划分策略**：通过亲缘簇划分揭示数据泄漏对评估真实预测能力的关键影响，这是许多育种研究未充分考虑的。
3. **大规模重复实验与统计检验**：50次交叉验证结合bootstrap和Mann-Whitney U检验，增强了特征重要性分析的可靠性。
4. **跨方法一致性验证**：XGBoost特征重要性与GWAS信号在基因组位置上重叠，为机器学习辅助变异发现提供了证据。

### 不足与局限

1. **样本量有限且遗传多样性低**：仅1011个个体来源于F4世代，有效群体大小小（Ne≈18–57），导致模型泛化能力极差，无法评估在更广泛群体中的预测性能。
2. **缺乏外部独立验证**：所有实验均在同一群体内划分，未使用外部独立野生动群或其他品系进行测试，结论外部有效性存疑。
3. **XGBoost超参数搜索不充分**：仅探索20组拉丁超立方体组合，且PCA组件范围窄（2–6），可能未达到最优配置。
4. **未探索深度学习方法**：虽然提到了CNN在图像表型中的应用，但预测部分仅用了树模型，未对比更复杂的神经网络。
5. **非线性模型未体现优势**：XGBoost在测试集上未优于GBLUP，可能是由于群体结构掩盖了非加性效应，或样本量不足以检测上位性。需要更大样本来验证。
6. **计算资源与复现性细节缺失**：未报告软件版本、超参数最终选择值、训练时间等，降低了可复现性。
7. **伦理和数据共享限制**：基因型和基因组数据需获得毛利人许可，数据集未公开，存在可复现性障碍。

（完）
