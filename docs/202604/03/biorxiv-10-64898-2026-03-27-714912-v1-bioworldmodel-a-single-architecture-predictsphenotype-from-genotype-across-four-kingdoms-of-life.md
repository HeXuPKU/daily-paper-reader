---
title: "BioWorldModel: a single architecture predictsphenotype from genotype across four kingdoms of life"
title_zh: BioWorldModel：一种跨越四个生物界从基因型预测表型的单一架构
authors: "Shaik, K. H. B., Sahu, A."
date: 2026-03-31
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.27.714912v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 从基因型预测表型的世界模型
tldr: BioWorldModel是一个跨物种的表型预测架构，通过模拟从基因组到表型的动态生物学过程（调控、表达、通路、细胞层级），实现了对细菌、真菌、动物和植物四大界生物性状的高精度预测。该模型超越了传统的静态关联方法，证明了模拟生物生成过程比单纯增加模型规模更能提升预测性能，为理解基因型到表型的复杂映射提供了新范式。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-001.webp\", \"caption\": \"Figure 2: Comprehensive evaluation across all four kingdoms. (Row A) Point prediction accuracy: BioWorldModel outperforms Ridge (GBLUP) and Random Forest baselines in all organisms. E. coli : mean r = 0.678 (+207% vs ridge); S. cerevisiae: r = 0.915 (+167%); D. melanogaster : r = 0.499 (+760%); O. sativa: r = 0.995 (+49%). (Row B) Calibration quality: Expected calibration error (ECE) varies across organisms. Rice shows excellent calibration (ECE = 0.054), Drosophila moderate (ECE = 0.192), while bacteria and yeast require improvement (ECE > 0.47). Prediction interval coverage plotted against target coverage with perfect calibration shown as diagonal. (Row C) Uncertainty decomposition: Epistemic (model) vs aleatoric (irreducible) uncertainty. Epistemic-error correlation indicates model’s awareness of its limitations: rice r = 0.652, Drosophila r = 0.110, E. coli r = 0.078, yeast r = 0.060. Epistemic/aleatoric ratio shows relative contribution of model uncertainty.\", \"page\": 7, \"index\": 1, \"width\": 904, \"height\": 799}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-002.webp\", \"caption\": \"Figure 4: Uncertainty decomposition across all four organisms. (Row A) Epistemic (model) vs aleatoric (irreducible) uncertainty in stacked bars for each organism. Epistemic/aleatoric ratio varies: yeast shows highest ratio (0.777, model-dominated), E. coli lowest (0.235, noisedominated), rice and Drosophila intermediate (0.604 and 0.142 respectively). (Row B) Epistemic uncertainty correlates with prediction error in all organisms, demonstrating model awareness of its limitations. Strongest correlation in rice (r = 0.652), moderate in Drosophila (r = 0.110), weaker in E. coli (r = 0.078) and yeast (r = 0.060). Scatter plots show simulated data with fitted regression lines. High epistemic uncertainty reliably indicates regions where predictions are less trustworthy.\", \"page\": 10, \"index\": 2, \"width\": 905, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-003.webp\", \"caption\": \"Figure 3: Cross-kingdom performance and generalization. (A) Sample size effects: Performance vs test sample count. Small-sample strength demonstrated in Drosophila (N=41, r=0.499). Saturation approaches in rice (N=83, r=0.995). (B) Trait dimensionality: Performance vs number of traits. High-dimensional regime (E. coli : 214 traits, D. melanogaster : 199 traits) shows biological structure stabilizes learning. (C) Covariance structure recovery: Correlation between predicted and empirical trait covariances. Rice shows strongest recovery (r=0.594), E. coli moderate (r=0.387), suggesting learned pleiotropy structure captures real biology.\", \"page\": 8, \"index\": 3, \"width\": 903, \"height\": 716}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-004.webp\", \"caption\": \"Table 3: Extended Data Table 1: Ablation study on E. coli confirms each component contributes.\", \"page\": 19, \"index\": 4, \"width\": 818, \"height\": 361}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-005.webp\", \"caption\": \"Table 2: Probabilistic quality varies across organisms.\", \"page\": 9, \"index\": 5, \"width\": 940, \"height\": 226}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-006.webp\", \"caption\": \"Table 4: Extended Data Table 2: Comprehensive baseline comparison across all four organisms. We evaluated five classical methods on the same train/test splits. Ridge regression (GBLUP) and Random Forest are shown in main text as representative baselines; BayesB (ElasticNet proxy) and Lasso provide additional benchmarks. All baselines trained per-trait with hyperparameter tuning. BioWorldModel trained once per organism with fixed architecture, predicting all traits jointly.\", \"page\": 20, \"index\": 6, \"width\": 960, \"height\": 860}]"
motivation: 传统预测模型通常将基因型视为静态编码并独立处理性状，忽略了生物体在不同环境和时间下解释基因组的动态生物学过程。
method: 该架构通过四个生物过程层（调控、表达、通路、细胞）处理受个体变异调制的基因嵌入，并利用状态条件注意力机制预测多元性状分布。
result: "在细菌、酵母、果蝇和水稻的测试中，该模型预测准确率显著超过传统方法，在小样本果蝇表型预测中相关性提升达760%。"
conclusion: 研究证明，模拟生物生成表型的内在逻辑而非仅仅进行统计关联，是提升神经网络捕捉复杂生物学特征能力的关键。
---

## 摘要
相同的基因组在不同条件下会产生不同的表型，然而现有的预测模型通常仅对基因型进行一次编码，并将每个性状视为相互独立。在本文中，我们展示了将表型生成过程表示为一个动态生物过程，可以显著提升细菌、真菌、动物和植物的预测准确性。BioWorldModel 学习生物体如何解读其基因组：受个体变异调制的冻结基因嵌入（物种上下文）通过四个响应环境和时间的生物过程层（调控 [->] 表达 [->] 通路 [->] 细胞）。一种状态条件注意力机制重新读取这种动态表示，从而预测完整的多元性状分布。在无需修改的情况下，该架构在 214 个细菌生长性状上实现了平均相关系数 r = 0.678（比岭回归提升 207%），在 35 个酵母适应性性状上实现了 r = 0.915（提升 167%），在小样本情况下的 199 个果蝇表型上实现了 r = 0.499（提升 760%），在 36 个水稻性状上实现了 r = 0.995（提升 49%）。消融实验证实，驱动性能提升的是对生物过程的建模，而非模型规模。当神经架构能够表征生物学如何生成表型，而不仅仅是将基因型与结果相关联时，它们就能捕捉到静态方法所遗漏的信息。

## Abstract
The same genome produces different phenotypes in different conditions--yet predictive models encode genotype once and treat each trait independently. Here we show that representing phenotype generation as a dynamic biological process transforms predictive accuracy across bacteria, fungi, animals and plants.

BioWorldModel learns how organisms interpret their genome: frozen gene embeddings (species context) modulated by individual variation pass through four biological process layers (regulation [-&gt;] expression [-&gt;] pathway [-&gt;] cellular) that respond to environment and time. A state-conditioned attention mechanism rereads this dynamic representation, predicting full multivariate trait distributions.

Without modification, the architecture achieves mean correlation r = 0.678 on 214 bacterial growth traits (207% better than ridge regression), r = 0.915 on 35 yeast fitness traits (167% better), r = 0.499 on 199 fly phenotypes in small-sample regime (760% better), and r = 0.995 on 36 rice traits (49% better). Ablations confirm that modeling biological process--not model size--drives performance. When neural architectures represent how biology generates phenotype rather than merely associating genotype with outcome, they capture what static methods miss.

---

## 论文详细总结（自动生成）

以下是对论文《BioWorldModel: a single architecture predicts phenotype from genotype across four kingdoms of life》的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：传统的基因型到表型（G2P）预测模型（如 GBLUP、岭回归等）通常将基因组视为静态编码，并假设各性状之间相互独立。这种方法忽略了生物体在不同环境和时间下解释基因组的**动态生物学过程**。
*   **研究背景**：生物学本质上是一个多层级的生成过程。相同的基因组在不同条件下会通过调控、表达和代谢通路产生截然不同的表型。
*   **整体含义**：本研究提出了 **BioWorldModel**，这是一种模拟生物体内部“世界模型”的深度学习架构。它不再仅仅寻找统计关联，而是通过模拟从基因到细胞层级的生物信息流，实现了跨越细菌、真菌、动物和植物四大生物界的统一表型预测。

### 2. 论文提出的方法论
*   **核心思想**：将表型预测建模为一个受个体变异调制的动态生物过程，而非简单的回归任务。
*   **关键技术细节**：
    *   **分层生物架构**：模型包含四个顺序排列的生物过程层：**调控层 (Regulation) $\rightarrow$ 表达层 (Expression) $\rightarrow$ 通路层 (Pathway) $\rightarrow$ 细胞层 (Cellular)**。
    *   **输入处理**：使用预训练的冻结基因嵌入作为“物种上下文”，并将其与个体的基因变异（如 SNP）相结合。
    *   **状态条件注意力机制 (State-conditioned Attention)**：该机制允许模型根据当前的环境和时间状态，“重新读取”动态生成的生物表示，从而预测多元性状分布。
    *   **概率预测**：模型不仅给出点估计，还输出预测分布，能够分解出**认知不确定性**（模型知识不足）和**偶然不确定性**（数据固有的噪声）。

### 3. 实验设计
*   **数据集与场景**：
    *   **细菌 (*E. coli*)**：214 个生长性状。
    *   **真菌 (*S. cerevisiae*)**：35 个适应性性状。
    *   **动物 (*D. melanogaster*)**：199 个复杂表型（小样本场景，N=41）。
    *   **植物 (*O. sativa*)**：36 个农艺性状。
*   **Benchmark（基准）**：
    *   **Ridge Regression (GBLUP)**：传统的线性基因组预测标准。
    *   **Random Forest (随机森林)**：非线性机器学习基准。
    *   **其他**：包括 BayesB、Lasso 和 ElasticNet 等。
*   **对比方式**：在相同的训练/测试集划分下，对比平均相关系数 (r)、校准误差 (ECE) 和不确定性指标。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号、数量或总训练时长。
*   **训练特征**：提到 BioWorldModel 在每个物种上仅需使用固定架构训练一次，即可联合预测所有性状，而基准模型通常需要针对每个性状单独训练和调优。

### 5. 实验数量与充分性
*   **实验规模**：
    *   涵盖了生命之树的四个界，证明了架构的普适性。
    *   进行了**消融实验**（Ablation Study），通过逐步移除生物层级验证了每个组件对性能的贡献。
    *   分析了样本量（从极小样本到饱和样本）和性状维度对模型性能的影响。
*   **充分性评价**：实验设计非常充分且具有挑战性。特别是针对果蝇的小样本实验和针对大肠杆菌的高维性状实验，有力地证明了模型在极端数据情况下的鲁棒性。

### 6. 主要结论与发现
*   **性能飞跃**：BioWorldModel 在所有生物中均显著优于传统方法。在果蝇实验中，相关性提升高达 **760%**；在细菌和酵母中分别提升 **207%** 和 **167%**。
*   **生物结构胜过规模**：消融实验证实，性能的提升源于对生物过程（调控、通路等）的模拟，而非单纯增加神经网络的参数量。
*   **不确定性感知**：模型能够识别自己“不知道”的领域。在水稻数据中，认知不确定性与预测误差的相关性达到 0.652，表明模型具有良好的自我评估能力。
*   **多效性捕获**：模型能够恢复性状之间的协方差结构，证明其捕捉到了真实的生物学多效性（Pleiotropy）。

### 7. 优点
*   **跨物种统一性**：单一架构无需修改即可应用于完全不同的生物界，展示了极强的泛化能力。
*   **生物学可解释性**：通过分层设计，将深度学习的“黑箱”与已知的生物学层级（表达、通路）对齐。
*   **小样本鲁棒性**：在样本量极少（如 N=41）的情况下依然能通过生物学先验知识维持较高的预测精度。

### 8. 不足与局限
*   **校准质量差异**：虽然预测准确率高，但在细菌和酵母上的概率校准（ECE）较差（>0.47），意味着在某些物种上预测的置信度不够准确。
*   **计算复杂度**：虽然未详述，但模拟多层生物过程的计算开销显然高于简单的线性回归。
*   **依赖预训练嵌入**：模型性能部分依赖于高质量的基因嵌入，对于基因组注释较差的物种，效果可能会打折扣。
*   **环境因素简化**：虽然考虑了环境状态，但对于极其复杂的动态环境交互，模型的建模能力仍有待进一步验证。

（完）
