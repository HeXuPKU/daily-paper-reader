---
title: "BioWorldModel: a single architecture predictsphenotype from genotype across four kingdoms of life"
title_zh: BioWorldModel：单一架构跨越四个生物界实现从基因型到表型的预测
authors: "Shaik, K. H. B., Sahu, A."
date: 2026-03-31
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.27.714912v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: BioWorldModel跨环境预测基因型到表型的转换
tldr: BioWorldModel 是一种跨物种的统一架构，通过模拟从调控到细胞的四个生物过程层，将基因型动态映射为表型。该模型结合了基因嵌入、个体变异以及环境和时间因素，利用状态调节注意力机制预测多元性状。在细菌、真菌、动物和植物四大界的实验中，其预测准确性显著超越传统方法，证明了模拟生物生成过程比单纯的关联学习更具优势。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-001.webp\", \"caption\": \"Figure 2: Comprehensive evaluation across all four kingdoms. (Row A) Point prediction accuracy: BioWorldModel outperforms Ridge (GBLUP) and Random Forest baselines in all organisms. E. coli : mean r = 0.678 (+207% vs ridge); S. cerevisiae: r = 0.915 (+167%); D. melanogaster : r = 0.499 (+760%); O. sativa: r = 0.995 (+49%). (Row B) Calibration quality: Expected calibration error (ECE) varies across organisms. Rice shows excellent calibration (ECE = 0.054), Drosophila moderate (ECE = 0.192), while bacteria and yeast require improvement (ECE > 0.47). Prediction interval coverage plotted against target coverage with perfect calibration shown as diagonal. (Row C) Uncertainty decomposition: Epistemic (model) vs aleatoric (irreducible) uncertainty. Epistemic-error correlation indicates model’s awareness of its limitations: rice r = 0.652, Drosophila r = 0.110, E. coli r = 0.078, yeast r = 0.060. Epistemic/aleatoric ratio shows relative contribution of model uncertainty.\", \"page\": 7, \"index\": 1, \"width\": 904, \"height\": 799}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-002.webp\", \"caption\": \"Figure 4: Uncertainty decomposition across all four organisms. (Row A) Epistemic (model) vs aleatoric (irreducible) uncertainty in stacked bars for each organism. Epistemic/aleatoric ratio varies: yeast shows highest ratio (0.777, model-dominated), E. coli lowest (0.235, noisedominated), rice and Drosophila intermediate (0.604 and 0.142 respectively). (Row B) Epistemic uncertainty correlates with prediction error in all organisms, demonstrating model awareness of its limitations. Strongest correlation in rice (r = 0.652), moderate in Drosophila (r = 0.110), weaker in E. coli (r = 0.078) and yeast (r = 0.060). Scatter plots show simulated data with fitted regression lines. High epistemic uncertainty reliably indicates regions where predictions are less trustworthy.\", \"page\": 10, \"index\": 2, \"width\": 905, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-003.webp\", \"caption\": \"Figure 3: Cross-kingdom performance and generalization. (A) Sample size effects: Performance vs test sample count. Small-sample strength demonstrated in Drosophila (N=41, r=0.499). Saturation approaches in rice (N=83, r=0.995). (B) Trait dimensionality: Performance vs number of traits. High-dimensional regime (E. coli : 214 traits, D. melanogaster : 199 traits) shows biological structure stabilizes learning. (C) Covariance structure recovery: Correlation between predicted and empirical trait covariances. Rice shows strongest recovery (r=0.594), E. coli moderate (r=0.387), suggesting learned pleiotropy structure captures real biology.\", \"page\": 8, \"index\": 3, \"width\": 903, \"height\": 716}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-004.webp\", \"caption\": \"Table 3: Extended Data Table 1: Ablation study on E. coli confirms each component contributes.\", \"page\": 19, \"index\": 4, \"width\": 818, \"height\": 361}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-005.webp\", \"caption\": \"Table 2: Probabilistic quality varies across organisms.\", \"page\": 9, \"index\": 5, \"width\": 940, \"height\": 226}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-006.webp\", \"caption\": \"Table 4: Extended Data Table 2: Comprehensive baseline comparison across all four organisms. We evaluated five classical methods on the same train/test splits. Ridge regression (GBLUP) and Random Forest are shown in main text as representative baselines; BayesB (ElasticNet proxy) and Lasso provide additional benchmarks. All baselines trained per-trait with hyperparameter tuning. BioWorldModel trained once per organism with fixed architecture, predicting all traits jointly.\", \"page\": 20, \"index\": 6, \"width\": 960, \"height\": 860}]"
motivation: 传统模型通常将基因型与表型视为静态关联，忽略了生物体在不同环境和时间下解释基因组的动态生物学过程。
method: 构建了包含调控、表达、通路和细胞四个生物层级的架构，利用冻结的基因嵌入和状态调节注意力机制来模拟表型的动态生成。
result: "在细菌、酵母、果蝇和水稻的多种性状预测中，该模型的相关性表现优异，较传统岭回归等方法提升了 49% 至 760% 不等。"
conclusion: 研究表明，通过神经架构表征生物学产生表型的过程，而非仅仅进行关联分析，能够捕捉到静态方法无法获取的关键生物学信息。
---

## 摘要
相同的基因组在不同条件下会产生不同的表型，然而现有的预测模型通常仅对基因型进行一次编码，并将每个性状视为相互独立。在本文中，我们展示了将表型生成过程表示为一个动态生物过程，能够彻底改变对细菌、真菌、动物和植物的预测准确性。BioWorldModel 学习生物体如何解读其基因组：受个体变异调节的冻结基因嵌入（物种上下文）通过四个生物过程层（从调控、表达、通路到细胞层级），这些层级能够对环境和时间做出响应。一种状态条件注意力机制通过重新读取这种动态表示，来预测完整的多元性状分布。在不进行任何修改的情况下，该架构在 214 个细菌生长性状上实现了 r = 0.678 的平均相关性（比岭回归提升 207%），在 35 个酵母适应性性状上实现了 r = 0.915（提升 167%），在小样本情况下的 199 个果蝇表型上实现了 r = 0.499（提升 760%），在 36 个水稻性状上实现了 r = 0.995（提升 49%）。消融实验证实，驱动性能提升的是对生物过程的建模，而非模型规模。当神经架构能够表征生物学如何生成表型，而不仅仅是将基因型与结果建立关联时，它们就能捕捉到静态方法所遗漏的关键信息。

## Abstract
The same genome produces different phenotypes in different conditions--yet predictive models encode genotype once and treat each trait independently. Here we show that representing phenotype generation as a dynamic biological process transforms predictive accuracy across bacteria, fungi, animals and plants. BioWorldModel learns how organisms interpret their genome: frozen gene embeddings (species context) modulated by individual variation pass through four biological process layers (regulation to expression to pathway to cellular) that respond to environment and time. A state-conditioned attention mechanism rereads this dynamic representation, predicting full multivariate trait distributions. Without modification, the architecture achieves mean correlation r = 0.678 on 214 bacterial growth traits (207% better than ridge regression), r = 0.915 on 35 yeast fitness traits (167% better), r = 0.499 on 199 fly phenotypes in small-sample regime (760% better), and r = 0.995 on 36 rice traits (49% better). Ablations confirm that modeling biological process--not model size--drives performance. When neural architectures represent how biology generates phenotype rather than merely associating genotype with outcome, they capture what static methods miss.

---

## 论文详细总结（自动生成）

以下是对论文《BioWorldModel: a single architecture predicts phenotype from genotype across four kingdoms of life》的结构化深度总结：

### 1. 核心问题与整体含义（研究动机和背景）
传统的基因型到表型（G2P）预测模型（如 GBLUP 或随机森林）通常将生物体视为“黑盒”，仅建立基因变异与最终性状之间的静态统计关联。这种方法存在三大缺陷：
*   **忽略动态过程：** 忽略了从 DNA 到表型之间复杂的生物学层级（调控、表达、代谢通路）。
*   **环境脱节：** 难以整合环境因子和时间维度对基因表达的影响。
*   **性状孤立：** 通常将每个性状视为独立变量，忽略了多效性（Pleiotropy）和性状间的内在联系。
**BioWorldModel 的核心动机**是构建一个能够模拟生物体“如何解读基因组”的动态生成模型，通过统一的神经架构跨越细菌、真菌、动物和植物四大界，实现高精度的多元表型预测。

### 2. 方法论：核心思想与关键技术
BioWorldModel 的核心思想是将表型生成表示为一个受环境和时间调节的四层动态生物过程：
*   **输入层：** 结合了“冻结的基因嵌入”（提供物种上下文知识）和“个体变异向量”（捕捉 SNP 或突变）。
*   **四层生物架构：**
    1.  **调控层 (Regulatory Layer)：** 模拟基因组的开放性和转录因子的结合。
    2.  **表达层 (Expression Layer)：** 模拟转录本的丰度。
    3.  **通路层 (Pathway Layer)：** 模拟蛋白质相互作用和代谢网络。
    4.  **细胞层 (Cellular Layer)：** 整合上述信息形成细胞状态。
*   **状态调节注意力机制 (State-Conditioned Attention)：** 该机制允许模型根据当前的环境（Environment）和时间（Time）状态，动态地“重新读取”和加权生物层级中的信息。
*   **概率输出：** 模型不只给出点预测，还通过预测多元分布来量化**认识不确定性**（模型知识不足）和**偶然不确定性**（数据固有的噪声）。

### 3. 实验设计：数据集、Benchmark 与对比方法
研究在代表生命四大界的四种模式生物上进行了验证：
*   **细菌 (*E. coli*)：** 214 个生长性状（高维性状）。
*   **真菌 (*S. cerevisiae*)：** 35 个适应性性状。
*   **动物 (*D. melanogaster*)：** 199 个表型性状（极小样本场景，N=41）。
*   **植物 (*O. sativa*)：** 36 个农艺性状。
*   **Benchmark 方法：** 岭回归（GBLUP 的等效方法）、随机森林（Random Forest）、BayesB、Lasso 以及 ElasticNet。
*   **评估指标：** 皮尔逊相关系数 (r)、预期校准误差 (ECE)、不确定性分解相关性。

### 4. 资源与算力
*   **算力说明：** 论文中**未明确说明**具体的 GPU 型号、数量或总训练时长。
*   **模型特性：** 文中提到该架构在不同生物间保持固定（Fixed Architecture），且对于每个生物体只需训练一次即可同时预测所有性状，这暗示了其在多性状预测任务中比逐个训练性状的传统方法更具效率。

### 5. 实验数量与充分性
*   **实验规模：** 涵盖了从原核生物到高等真核生物的跨界验证，样本量从极小（果蝇 41 个）到中等（水稻等）均有覆盖。
*   **消融实验：** 进行了详细的消融研究（如表 3 所示），验证了调控层、表达层等各组件对性能的贡献，证明了性能提升源于“生物过程建模”而非单纯增加参数量。
*   **充分性评价：** 实验设计较为充分，通过跨物种验证证明了模型的通用性；通过不确定性分析证明了模型的可靠性。但在超大规模群体遗传学数据集上的表现仍有待进一步观察。

### 6. 主要结论与发现
*   **性能飞跃：** BioWorldModel 在所有生物界中均显著优于传统方法。在果蝇（小样本）上提升了 760%，在细菌上提升了 207%，在水稻上达到了近乎完美的 r=0.995。
*   **生物学一致性：** 模型能够成功恢复性状间的协方差结构（如水稻 r=0.594），说明它捕捉到了真实的生物多效性。
*   **不确定性感知：** 模型能够识别自己“不知道”的区域，认识不确定性与预测误差呈正相关，这对于育种和临床决策至关重要。
*   **核心发现：** 模拟生物学产生表型的**过程**，比单纯寻找基因与结果的**关联**更能捕捉生命系统的本质。

### 7. 优点
*   **跨界通用性：** 单一架构无需针对物种进行结构调整，展现了极强的泛化能力。
*   **动态建模：** 成功将环境和时间因素整合进 G2P 预测中。
*   **小样本鲁棒性：** 在果蝇实验中证明，即使在极少样本下，利用生物学结构先验也能获得可靠预测。
*   **可解释性潜力：** 四层生物架构为追踪变异如何影响特定生物通路提供了可能。

### 8. 不足与局限
*   **校准度差异：** 在细菌和酵母上的校准误差（ECE > 0.47）较高，说明在某些微生物场景下，模型对概率的估计尚不够准确。
*   **环境建模深度：** 虽然引入了环境状态，但对于极其复杂或多变的环境交互作用，目前的建模方式可能仍显简化。
*   **计算开销：** 尽管未详细列出，但深度学习架构的训练和推理成本显然高于简单的线性模型（GBLUP）。
*   **数据依赖：** 模型性能高度依赖于高质量的基因嵌入和变异标注，对于基因组注释不全的非模式生物可能受限。

（完）
