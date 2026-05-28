---
title: Leveraging cis- and trans-variants to improve protein expression level prediction for proteome-wide association studies
title_zh: 利用顺式和反式变异改进蛋白质表达水平预测以用于蛋白质组关联研究
authors: "Dong, R., Lamb, D., Wang, G., DeWan, A., Leal, S. M."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.28.728201v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 开发TransCisPredict用于蛋白质组关联研究，使用类似GWAS的方法（BayesR、弹性网络、LASSO、SuSiE）
tldr: "遗传效应常通过蛋白质介导，但多数研究缺乏蛋白质组数据。为此开发TransCisPredict，通过LD块选择整合顺式和反式变异预测蛋白质表达，并采用多种方法进行权重估计。在UK Biobank中，利用顺式和反式变异可预测2339个蛋白质（CV-R2>0.05），而仅用顺式变异仅466个。对2型糖尿病的PWAS发现40个关联蛋白，其中仅顺式变异仅3个，表明整合反式变异大幅提升PWAS效力。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有蛋白质组数据不足，且多数方法仅用顺式变异，限制了预测能力。
method: 开发TransCisPredict，使用LD块选择整合顺反式变异，结合BayesR、Elastic Net等四种方法预测蛋白质表达并执行PWAS。
result: "整合顺反式变异预测2339个蛋白质（CV-R2>0.05），对比仅顺式466个；在T2D中验证40个关联蛋白，仅顺式仅3个。"
conclusion: 整合顺反式变异显著提高蛋白质预测数量，增强PWAS功效，为大规模蛋白质组关联研究提供新工具。
---

## 摘要
由于遗传效应通常通过蛋白质介导，蛋白质组数据的分析可以为疾病病因学提供见解。然而，大多数研究缺乏蛋白质组数据。为解决这个问题，我们开发了TransCisPredict，以生物库规模进行蛋白质组关联研究（PWAS）。TransCisPredict通过连锁不平衡区块选择减少计算负担，便于整合顺式和反式变异来预测蛋白质表达，并进行蛋白质-表型关联分析。考虑到蛋白质调控架构的差异，使用四种预测方法进行权重估计，即BayesR、Elastic Net、LASSO和SuSiE。采用五折交叉验证为每种蛋白质选择最佳方法。利用具有蛋白质组和基因型阵列数据的英国白人英国生物库研究对象（N=42,644）进行权重估计。在可用的2,920个蛋白质表达水平中，使用顺式和反式变异时，有2,339个可预测（CV-R2>0.05）。由于大多数方法仅限于顺式变异，为了比较，仅使用顺式变异进行预测，得到466个蛋白质（CV-R2>0.05）。对2,339个预测的蛋白质表达水平和2型糖尿病（T2D）进行了PWAS，使用没有蛋白质组数据的英国白人英国生物库研究对象（N=364,132），然后使用控制水平多效性的方法进行两样本孟德尔随机化验证。40个蛋白质与T2D相关并通过验证。对于仅用顺式预测的466个蛋白质表达水平，3个蛋白质与T2D相关并通过验证。使用TransCisPredict整合顺式和反式变异，与仅使用顺式变异相比，有助于预测更多蛋白质，从而增加PWAS的功效。

## Abstract
Since genetic effects are often mediated through proteins, the analysis of proteomic data can provide insights into disease etiology. However, most studies lack proteomic data. To address this problem, we developed TransCisPredict to perform proteome-wide association studies (PWAS) at a biobank scale. TransCisPredict reduces computational burden through linkage-disequilibrium block selection which facilitates incorporating cis- and trans-variants to predict protein expression and performs protein-phenotype association analyses. To account for differences in protein regulatory architecture, four prediction methods are used for weight estimation, i.e., BayesR, Elastic Net, LASSO, and SuSiE. Five-fold cross-validation (CV) is used to select the optimal method for each protein. Weight estimation was performed using White British UK Biobank study subjects (N=42,644) with proteomic and genotype array data. Of the 2,920 available protein expression levels, 2,339 could be predicted with a CV-R2>0.05 when cis- and trans-variants were used. Since most methods are limited to cis-variation, for comparison only cis-variants were used for prediction yielding 466 proteins with a CV-R2>0.05. A PWAS was performed for 2,339 predicted protein expression levels and type 2 diabetes (T2D) using White British UK Biobank study subjects without proteomic data (N=364,132) followed by two-sample Mendelian randomization using a method that controls for horizontal pleiotropy for validation. Forty proteins were associated with T2D and validated. For the 466 cis-only predicted protein expression levels, three proteins were associated with T2D and validated. Incorporating both cis- and trans-variation using TransCisPredict facilitates the prediction of many more proteins compared to using cis-only variants, thereby increasing the power of PWAS.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：遗传效应通常通过蛋白质介导，蛋白质组数据分析能为疾病病因学提供关键见解。然而，大多数大型生物库研究缺乏蛋白质组数据，限制了蛋白质组关联研究（PWAS）的开展。现有蛋白质表达预测方法大多仅利用顺式变异（cis-variants），忽略了反式变异（trans-variants）的贡献，导致预测的蛋白质数量有限，PWAS统计功效较低。
- **研究动机**：开发一种能够整合顺式和反式变异的大规模蛋白质表达预测方法，以充分利用基因型数据，提高蛋白质表达水平的预测能力，从而在无蛋白质组数据的样本中也能进行有效的蛋白质组关联分析。
- **整体含义**：该研究为大规模生物库提供了新的分析工具，可大幅增加可预测的蛋白质数量，增强对复杂疾病（如2型糖尿病）遗传病因的发现能力。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过连锁不平衡（LD）区块选择策略，整合顺式与反式变异，并采用多种预测模型进行权重估计，最终选择最佳模型来预测蛋白质表达水平，再利用预测表达水平进行蛋白质-表型关联分析。
- **关键技术细节**：
  - **LD区块选择**：基于连锁不平衡结构，将变异划分为区块，减少计算负担，便于同时纳入顺式和反式变异（顺式定义为基因附近区域，反式定义为其余基因组区域）。
  - **四种预测方法**：使用BayesR、Elastic Net、LASSO和SuSiE四种方法分别估计遗传预测权重。每种方法适用于不同的蛋白质调控结构（如稀疏效应、多效应等）。
  - **模型选择**：通过五折交叉验证（CV-R²）为每个蛋白质选择预测性能最佳的方法。
  - **PWAS流程**：利用训练好的权重，在无蛋白质组数据的大样本中预测蛋白质表达水平，然后进行蛋白质-表型关联检验（类似全转录组关联研究TWAS的思路）。
  - **验证策略**：采用控制水平多效性的两样本孟德尔随机化（MR）方法对PWAS结果进行验证。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - **训练集**：英国生物库（UK Biobank）中具有蛋白质组数据和基因型阵列数据的英国白人研究对象，共42,644人，用于训练蛋白质表达预测模型。
  - **测试/应用集**：英国生物库中无蛋白质组数据的英国白人研究对象，共364,132人，用于进行2型糖尿病（T2D）的PWAS。
  - **蛋白质组数据**：共2,920个蛋白质表达水平可用。
- **基准与对比**：
  - 对比方法：仅使用顺式变异进行预测（即大多数现有方法，如PrediXcan、FUSION等所采用的做法）。
  - 基准：以交叉验证R²（CV-R²）>0.05作为可预测蛋白质的阈值。
- **对比结果**：
  - 使用顺式+反式变异时，可预测2,339个蛋白质（CV-R²>0.05）。
  - 仅使用顺式变异时，仅可预测466个蛋白质（CV-R²>0.05）。
- **评估指标**：CV-R²（交叉验证决定系数）、PWAS发现的关联蛋白质数量、MR验证通过的蛋白质数量。

## 4. 资源与算力

- 论文摘要及元数据中**未明确说明**使用的GPU型号、数量或训练时长。仅提及通过LD区块选择减少计算负担，但未给出具体算力资源信息。可能主要依赖CPU集群进行遗传权重估计和交叉验证，训练数据规模为42,644人、2,920个蛋白质，计算量较大但未详述。

## 5. 实验数量与充分性

- **主要实验组**：
  1. 训练蛋白质表达预测模型（使用2,920个蛋白质，四种方法 + 五折交叉验证）。
  2. 对比仅顺式与顺式+反式变异的预测性能（2,920个蛋白质分别评估，报告可预测数量）。
  3. 在364,132人中对2型糖尿病进行PWAS（涉及2,339个预测蛋白质）。
  4. 两样本孟德尔随机化验证（控制水平多效性）。
- **单疾病验证**：仅针对2型糖尿病进行验证。未在其他疾病上测试。
- **充分性评价**：实验设计较为完整，对比了关键的单一变量（顺式 vs 顺式+反式），并采用了交叉验证和独立MR验证，具有一定的客观性。但仅在一个疾病（T2D）、一个人群（英国白人）中验证，泛化性不足。未进行不同人群或不同蛋白质组平台的实验。

## 6. 论文的主要结论与发现

- 整合顺式和反式变异可显著提高蛋白质表达预测的数量：如CV-R²>0.05，顺式+反式得到2,339个（占80%），而仅顺式仅466个（占16%）。
- 在2型糖尿病的PWAS中，使用顺式+反式预测发现40个关联蛋白并通过MR验证，而仅使用顺式仅发现3个。说明整合反式变异极大提升了PWAS的统计功效。
- TransCisPredict是一种可在生物库规模有效执行的工具，为缺乏蛋白质组数据的疾病研究提供了新途径。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：首次在PWAS框架中系统整合顺式和反式变异，利用LD区块选择解决计算负担，相比现有方法（仅顺式）显著提升预测能力。
- **多模型集成**：采用四种预测方法（BayesR、Elastic Net、LASSO、SuSiE）并自动选择最优，适应不同蛋白质的遗传调控结构，提高了预测鲁棒性。
- **验证严格**：使用控制水平多效性的两样本MR进行下游验证，降低了假阳性风险。
- **大规模实证**：在UK Biobank数万训练样本和数十万测试样本上验证，结果具有实际参考价值。

## 8. 不足与局限

- **人群局限**：仅使用了英国白人数据，可能无法直接推广到其他种族/人群。
- **疾病覆盖少**：仅验证了2型糖尿病，未评估其他复杂疾病的PWAS效果。
- **蛋白质组数据局限性**：仅涵盖2,920个蛋白质，且来自Olink平台（可能有机测定偏差），未能覆盖全部蛋白质组。
- **未详细报告计算成本**：未说明GPU/CPU资源、时间消耗，难以评估实际可复现性。
- **预测性能阈值随意**：采用CV-R²>0.05作为可预测阈值，缺乏理论或生物学依据，可能遗漏真实信号或引入噪声。
- **反式变异选择策略**：仅通过LD区块选择，未考虑功能注释或生物学先验，可能包含大量无因果效应的变异降低预测精确度。

（完）
