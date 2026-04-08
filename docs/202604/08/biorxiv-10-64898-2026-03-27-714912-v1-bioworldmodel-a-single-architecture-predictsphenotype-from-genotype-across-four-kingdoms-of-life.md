---
title: "BioWorldModel: a single architecture predictsphenotype from genotype across four kingdoms of life"
title_zh: BioWorldModel：一种跨越四个生物界的从基因型预测表型的单一架构
authors: "Shaik, K. H. B., Sahu, A."
date: 2026-03-31
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.27.714912v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 跨物种从基因型预测表型的世界模型架构
tldr: BioWorldModel 是一种跨物种的统一架构，通过模拟从基因型到表型的动态生物学过程（调控、表达、通路、细胞），实现了对细菌、真菌、动物和植物四大界生物表型的高精度预测。该模型不仅考虑基因变异，还整合了环境和时间因素，在多项任务中显著优于传统统计方法，证明了模拟生物生成过程比单纯的关联分析更具预测力。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-001.webp\", \"caption\": \"Figure 2: Comprehensive evaluation across all four kingdoms. (Row A) Point prediction accuracy: BioWorldModel outperforms Ridge (GBLUP) and Random Forest baselines in all organisms. E. coli : mean r = 0.678 (+207% vs ridge); S. cerevisiae: r = 0.915 (+167%); D. melanogaster : r = 0.499 (+760%); O. sativa: r = 0.995 (+49%). (Row B) Calibration quality: Expected calibration error (ECE) varies across organisms. Rice shows excellent calibration (ECE = 0.054), Drosophila moderate (ECE = 0.192), while bacteria and yeast require improvement (ECE > 0.47). Prediction interval coverage plotted against target coverage with perfect calibration shown as diagonal. (Row C) Uncertainty decomposition: Epistemic (model) vs aleatoric (irreducible) uncertainty. Epistemic-error correlation indicates model’s awareness of its limitations: rice r = 0.652, Drosophila r = 0.110, E. coli r = 0.078, yeast r = 0.060. Epistemic/aleatoric ratio shows relative contribution of model uncertainty.\", \"page\": 7, \"index\": 1, \"width\": 904, \"height\": 799}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-002.webp\", \"caption\": \"Figure 4: Uncertainty decomposition across all four organisms. (Row A) Epistemic (model) vs aleatoric (irreducible) uncertainty in stacked bars for each organism. Epistemic/aleatoric ratio varies: yeast shows highest ratio (0.777, model-dominated), E. coli lowest (0.235, noisedominated), rice and Drosophila intermediate (0.604 and 0.142 respectively). (Row B) Epistemic uncertainty correlates with prediction error in all organisms, demonstrating model awareness of its limitations. Strongest correlation in rice (r = 0.652), moderate in Drosophila (r = 0.110), weaker in E. coli (r = 0.078) and yeast (r = 0.060). Scatter plots show simulated data with fitted regression lines. High epistemic uncertainty reliably indicates regions where predictions are less trustworthy.\", \"page\": 10, \"index\": 2, \"width\": 905, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-003.webp\", \"caption\": \"Figure 3: Cross-kingdom performance and generalization. (A) Sample size effects: Performance vs test sample count. Small-sample strength demonstrated in Drosophila (N=41, r=0.499). Saturation approaches in rice (N=83, r=0.995). (B) Trait dimensionality: Performance vs number of traits. High-dimensional regime (E. coli : 214 traits, D. melanogaster : 199 traits) shows biological structure stabilizes learning. (C) Covariance structure recovery: Correlation between predicted and empirical trait covariances. Rice shows strongest recovery (r=0.594), E. coli moderate (r=0.387), suggesting learned pleiotropy structure captures real biology.\", \"page\": 8, \"index\": 3, \"width\": 903, \"height\": 716}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-004.webp\", \"caption\": \"Table 3: Extended Data Table 1: Ablation study on E. coli confirms each component contributes.\", \"page\": 19, \"index\": 4, \"width\": 818, \"height\": 361}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-005.webp\", \"caption\": \"Table 2: Probabilistic quality varies across organisms.\", \"page\": 9, \"index\": 5, \"width\": 940, \"height\": 226}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-006.webp\", \"caption\": \"Table 4: Extended Data Table 2: Comprehensive baseline comparison across all four organisms. We evaluated five classical methods on the same train/test splits. Ridge regression (GBLUP) and Random Forest are shown in main text as representative baselines; BayesB (ElasticNet proxy) and Lasso provide additional benchmarks. All baselines trained per-trait with hyperparameter tuning. BioWorldModel trained once per organism with fixed architecture, predicting all traits jointly.\", \"page\": 20, \"index\": 6, \"width\": 960, \"height\": 860}]"
motivation: 传统预测模型通常将基因型编码为静态特征并独立处理性状，忽略了生物体在不同环境下解释基因组的动态过程。
method: 提出 BioWorldModel 架构，利用冻结的基因嵌入和个体变异，通过模拟调控、表达、通路和细胞四个生物过程层，并结合状态条件注意力机制预测多变量性状分布。
result: 在细菌、酵母、果蝇和水稻的数百种性状预测中，该模型表现优异，相关性系数分别达到 0.678、0.915、0.499 和 0.995，远超传统回归方法。
conclusion: 模拟生物学产生表型的内在机制而非仅仅进行关联分析，是提升基因型到表型预测准确性的关键。
---

## 摘要
同样的基因组在不同条件下会产生不同的表型——然而，目前的预测模型通常只对基因型进行一次编码，并将每个性状独立对待。在这里，我们展示了将表型生成表示为一个动态生物过程，可以显著提升细菌、真菌、动物和植物的预测准确性。BioWorldModel 学习生物体如何解读其基因组：由个体变异调制的冻结基因嵌入（物种上下文）通过四个响应环境和时间的生物过程层（调控 [->] 表达 [->] 通路 [->] 细胞）。一种状态条件注意力机制重新读取这种动态表示，从而预测完整的多元性状分布。在无需修改的情况下，该架构在 214 个细菌生长性状上实现了平均相关系数 r = 0.678（比岭回归提高 207%），在 35 个酵母适应性性状上实现了 r = 0.915（提高 167%），在小样本情况下的 199 个果蝇表型上实现了 r = 0.499（提高 760%），在 36 个水稻性状上实现了 r = 0.995（提高 49%）。消融实验证实，驱动性能提升的是对生物过程的建模，而非模型规模。当神经架构能够表征生物学如何生成表型，而不仅仅是将基因型与结果相关联时，它们就能捕捉到静态方法所遗漏的信息。

## Abstract
The same genome produces different phenotypes in different conditions--yet predictive models encode genotype once and treat each trait independently. Here we show that representing phenotype generation as a dynamic biological process transforms predictive accuracy across bacteria, fungi, animals and plants.

BioWorldModel learns how organisms interpret their genome: frozen gene embeddings (species context) modulated by individual variation pass through four biological process layers (regulation [-&gt;] expression [-&gt;] pathway [-&gt;] cellular) that respond to environment and time. A state-conditioned attention mechanism rereads this dynamic representation, predicting full multivariate trait distributions.

Without modification, the architecture achieves mean correlation r = 0.678 on 214 bacterial growth traits (207% better than ridge regression), r = 0.915 on 35 yeast fitness traits (167% better), r = 0.499 on 199 fly phenotypes in small-sample regime (760% better), and r = 0.995 on 36 rice traits (49% better). Ablations confirm that modeling biological process--not model size--drives performance. When neural architectures represent how biology generates phenotype rather than merely associating genotype with outcome, they capture what static methods miss.

---

## 论文详细总结（自动生成）

### BioWorldModel：跨越四大生物界的基因型-表型预测世界模型

#### 1. 论文的核心问题与整体含义
论文探讨的核心问题是如何提高从基因型（Genotype）预测表型（Phenotype）的准确性。传统的预测模型（如 GBLUP 或随机森林）通常将基因型视为静态特征，并独立地预测每个性状，忽略了生物体在不同环境和时间下解读基因组的动态生物学过程。

**整体含义**：该研究提出了 **BioWorldModel**，这是一种统一的深度学习架构，旨在模拟生物体产生表型的内在逻辑（即“世界模型”）。它证明了通过模拟从调控到细胞层面的生物生成过程，而非仅仅进行统计关联，可以跨越细菌、真菌、动物和植物四大界，实现预测性能的质的飞跃。

#### 2. 论文提出的方法论
**核心思想**：将表型预测建模为一个受环境和时间调控的动态生物信号传递过程。

**关键技术细节**：
*   **输入表示**：利用冻结的预训练基因嵌入（提供物种上下文）并结合个体的基因变异（SNP/变异数据）作为输入。
*   **四层生物过程架构**：
    1.  **调控层 (Regulation)**：模拟基因组如何被初步读取。
    2.  **表达层 (Expression)**：模拟转录水平的响应。
    3.  **通路层 (Pathway)**：模拟基因产物之间的相互作用。
    4.  **细胞层 (Cellular)**：模拟高层级的生理状态。
*   **状态条件注意力机制 (State-conditioned Attention)**：模型根据当前的环境状态和时间点，动态地从上述生物表示中提取信息。
*   **概率预测**：模型不只输出单一数值，而是预测多元性状的概率分布，从而能够分解出**认知不确定性**（模型知识不足）和**偶然不确定性**（数据固有的噪声）。

#### 3. 实验设计
**数据集与场景**：
*   **细菌 (*E. coli*)**：214 个生长性状。
*   **真菌 (*S. cerevisiae*)**：35 个适应性性状。
*   **动物 (*D. melanogaster*)**：199 个复杂表型（侧重于极小样本量下的泛化能力）。
*   **植物 (*O. sativa*)**：36 个农艺性状。

**Benchmark 与对比方法**：
*   **基准方法**：岭回归（Ridge/GBLUP）、随机森林（Random Forest）、BayesB、Lasso。
*   **评估指标**：平均相关系数 (r)、期望校准误差 (ECE)、不确定性相关性等。

#### 4. 资源与算力
论文中**未明确说明**具体的硬件配置（如 GPU 型号、数量）及具体的训练时长。但文中提到 BioWorldModel 针对每个物种仅需使用固定架构训练一次，即可联合预测所有性状，暗示了其在多性状建模上的效率优势。

#### 5. 实验数量与充分性
*   **实验规模**：涵盖了生命之树的四个界，涉及数百个性状，样本量从极小（果蝇 N=41）到中等（水稻、细菌）不等。
*   **消融实验**：在 *E. coli* 数据集上进行了详细的消融实验，验证了调控、表达、通路、细胞各层级以及注意力机制对性能的贡献。
*   **充分性评价**：实验设计较为全面，不仅对比了预测精度，还深入分析了模型对性状间协方差结构（多效性）的恢复能力以及不确定性的量化，证明了结果的稳健性和生物学合理性。

#### 6. 主要结论与发现
*   **性能大幅领先**：BioWorldModel 在所有物种上的表现均远超传统统计模型。例如，在果蝇任务中相关性提升了 760%，在细菌任务中提升了 207%。
*   **生物学结构是关键**：消融实验显示，性能提升主要源于对生物过程的分层建模，而非单纯增加模型参数。
*   **捕捉多效性**：模型能够成功恢复性状之间的经验协方差结构，说明它学到了基因影响多个性状的内在生物学联系。
*   **不确定性感知**：模型表现出良好的自我意识，其预测的认知不确定性与实际预测误差呈正相关，尤其在水稻数据中表现显著（r=0.652）。

#### 7. 优点
*   **通用性强**：单一架构无需修改即可适配完全不同的生物界。
*   **机制驱动**：引入了生物学先验（分层处理），使深度学习模型不再是纯粹的黑盒，而是更贴近生命科学的逻辑。
*   **小样本鲁棒性**：在样本量极少的果蝇数据上依然表现出色，证明了生物学约束能有效防止过拟合。

#### 8. 不足与局限
*   **校准质量差异**：在细菌和酵母上的校准误差（ECE）较高，说明模型在某些低真核或原核生物上的概率估计仍有优化空间。
*   **解释性深度**：虽然架构分层，但目前尚难以直接从模型权重中提取出具体的、可验证的新生物学通路或调控机制。
*   **数据依赖**：模型性能高度依赖于预训练基因嵌入的质量，对于缺乏高质量基因组注释的非模式生物，效果可能受限。

（完）
