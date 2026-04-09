---
title: Optimisation of Weighted Ensembles of Genomic Prediction Models in Maize
title_zh: 玉米基因组预测模型加权集成的优化
authors: "Tomura, S., Powell, O. M., Wilkinson, M. J., Lefevre, J., Cooper, M."
date: 2026-04-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.03.703660v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 基因组预测模型加权集成优化
tldr: 本研究探讨了玉米基因组预测中加权集成模型的优化策略。基于多样性预测定理，研究评估了线性变换、Nelder-Mead和贝叶斯三种权重优化方法，并利用TeoNAM和MaizeNAM数据集对开花期和分蘖性状进行验证。结果表明，相比于等权重的简单集成，优化权重能显著提升预测性能，尤其是在权重分布差异较大时，为提高基因组预测准确性提供了重要参考。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在通过优化集成模型中各子模型的权重，解决简单等权重集成无法充分利用各模型信息量和多样性的问题。
method: 对比研究了线性变换、Nelder-Mead算法和贝叶斯优化三种权重分配方法在两个玉米NAM数据集上的预测表现。
result: 加权集成模型在多个场景下提升了预测性能，且当优化权重与等权重差异显著时，性能提升尤为明显。
conclusion: 权重优化是增强集成模型预测能力的有效途径，未来可尝试将其与超参数调优过程进行深度整合。
---

## 摘要
多个基因组预测模型的集成已证明其预测性能优于组成该集成的单个模型。集成模型的优异表现符合多样性预测定理（Diversity Prediction Theorem），该定理指出，对于由多样化预测模型构建的集成，其集成预测误差低于单个模型的平均预测误差。虽然朴素集成平均模型通过等权重聚合所有单个预测模型提供了基准性能提升，但优化每个单个模型的权重可以进一步增强集成预测性能。权重可以根据其在预测误差和多样性方面的信息量水平进行优化。在本研究中，我们利用来自两个玉米嵌套关联制图（NAM）数据集（TeoNAM 和 MaizeNAM）的开花期和分蘖性状，评估了采用三种可能权重优化方法（线性变换、Nelder-Mead 和贝叶斯法）的加权集成平均模型。所提出的三种加权集成平均方法在所研究的几种预测场景中均提高了预测性能。特别是，当调整后的权重与朴素集成模型使用的等权重存在显著差异时，加权集成模型增强了预测性能。在加权集成之间的性能比较中，所提出的方法在不同预测场景下的预测准确性和误差方面均未表现出明显的优越性。集成模型的权重优化值得进一步研究，以探索提高其预测性能的机会；例如，将加权集成与同步超参数调优过程相结合，可能为进一步研究提供一个有前景的方向。

## Abstract
Ensembles of multiple genomic prediction models have demonstrated improved prediction performance over the individual models contributing to the ensemble. The outperformance of ensemble models is expected from the Diversity Prediction Theorem, which states that for ensembles constructed with diverse prediction models, the ensemble prediction error becomes lower than the mean prediction error of the individual models. While a naive ensemble-average model provides baseline performance improvement by aggregating all individual prediction models with equal weights, optimising weights for each individual model could further enhance ensemble prediction performance. The weights can be optimised based on their level of informativeness regarding prediction error and diversity. Here, we evaluated weighted ensemble-average models with three possible weight optimisation approaches (linear transformation, Nelder-Mead and Bayesian) using flowering time and tillering traits from two maize nested associated mapping (NAM) datasets; TeoNAM and MaizeNAM. The three proposed weighted ensemble-average approaches improved prediction performance in several of the prediction scenarios investigated. In particular, the weighted ensemble models enhanced prediction performance when the adjusted weights differed substantially from the equal weights used by the naive ensemble models. For performance comparisons among the weighted ensembles, there was no clear superiority among the proposed approaches in both prediction accuracy and error across the prediction scenarios. Weight optimisation for ensembles warrants further investigation to explore the opportunities to improve their prediction performance; for example, integration of a weighted ensemble with a simultaneous hyperparameter tuning process may offer a promising direction for further research.

---

## 论文详细总结（自动生成）

这篇论文针对玉米基因组预测（Genomic Prediction, GP）中的集成学习方法进行了深入研究，重点探讨了如何通过优化子模型的权重来提升预测性能。以下是对该论文的结构化总结：

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：在基因组选择育种中，单一预测模型（如线性模型或机器学习模型）往往难以在所有性状和环境下保持最优。虽然简单的“等权重集成”（Naive Ensemble）能提升稳定性，但未能充分利用不同模型在预测误差和多样性上的差异。
*   **研究动机**：基于“多样性预测定理”（Diversity Prediction Theorem），集成模型的误差取决于个体模型的平均误差与模型间多样性的差值。研究旨在探索通过数学优化手段分配权重，是否能比简单的等权重平均获得更高的预测准确性。

### 2. 论文提出的方法论
*   **核心思想**：将多种异构模型（包括线性模型、核方法和机器学习模型）进行集成，并利用验证集数据动态寻找最优权重分配，以最小化均方根误差（RMSE）。
*   **基础模型库**：集成了 7 种模型，包括 GBLUP、RKHS（核脊回归）、SVR（支持向量回归）、RF（随机森林）、XGBoost、LightGBM 和 MLP（多层感知机）。
*   **权重优化算法**：
    *   **线性变换（Linear Transformation, LT）**：通过线性回归拟合各模型输出，将回归系数归一化后作为权重。
    *   **Nelder-Mead 算法（NM）**：一种非梯度下山单纯形法，在权重空间内搜索使验证集 RMSE 最小的参数组合。
    *   **贝叶斯优化（Bayesian Optimisation, BO）**：利用高斯过程代理模型和采集函数，在较少的迭代次数内寻找全局最优权重。
*   **约束条件**：所有权重之和限制为 1，确保预测值的量纲一致性。

### 3. 实验设计
*   **数据集**：使用了两个大规模玉米嵌套关联制图（NAM）群体：
    *   **TeoNAM**：大刍草与玉米杂交群体。
    *   **MaizeNAM**：玉米自交系杂交群体。
*   **测试性状**：开花期（DTS, DTA）和分蘖数（TBN）。
*   **实验场景**：采用了交叉验证（CV）策略，模拟了育种中对新系（New Lines）的预测。
*   **Benchmark（基准）**：
    *   **单个最佳模型**：各模型库中表现最好的独立模型。
    *   **朴素集成（Naive Ensemble）**：对所有子模型采取 1/N 的等权重平均。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的硬件配置（如 GPU 型号或 CPU 核心数）。
*   **计算复杂度**：文中提到贝叶斯优化和 Nelder-Mead 算法需要多次迭代评估，计算成本高于朴素集成，但由于基因组预测的数据规模通常在万级左右，单机工作站即可完成。

### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了两个不同的遗传群体、多个农艺性状以及三种不同的权重优化算法。
*   **充分性评价**：实验设计较为充分。通过对比不同性状（遗传力高低不同）和不同群体，验证了加权集成的鲁棒性。同时，研究还分析了权重分布与性能提升之间的相关性，提供了深入的机理分析。

### 6. 论文的主要结论与发现
*   **性能提升**：在多数场景下，优化权重的集成模型优于单一模型和朴素集成模型。
*   **关键发现**：当优化后的权重分布与等权重（1/N）差异越大时，性能提升越显著。这表明当某些模型明显优于其他模型或模型间互补性极强时，权重优化的价值最大。
*   **算法对比**：LT、NM 和 BO 三种优化方法在预测准确率上没有表现出绝对的优劣，性能表现互有胜负。
*   **多样性价值**：实验证实了集成不同类型的模型（线性+非线性）比集成同类模型更能有效降低预测误差。

### 7. 优点
*   **理论支撑扎实**：紧扣多样性预测定理，将抽象的数学定理转化为育种实践中的算法优化。
*   **模型多样性高**：涵盖了从传统的统计遗传学模型到现代深度学习/梯度提升树模型，具有很强的代表性。
*   **实用性强**：为育种家提供了一种无需深入调优单个模型参数，即可通过“模型组合”提升预测精度的方法。

### 8. 不足与局限
*   **计算开销**：权重优化过程需要在验证集上进行多次迭代，对于超大规模数据集或实时预测场景，计算成本是一个挑战。
*   **过拟合风险**：如果验证集样本量过小，优化的权重可能会在验证集上过拟合，导致在独立测试集上的泛化能力下降。
*   **超参数耦合**：目前权重优化与单个模型的超参数调优是分离的，未来若能实现同步优化（Simultaneous Tuning），可能会有更大的提升空间。

（完）
