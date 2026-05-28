---
title: "Robust Random Forests for Genomic Prediction: Challenges and Remedies"
title_zh: 用于基因组预测的鲁棒随机森林：挑战与对策
authors: "Lourenco, V. M., Ogutu, J. O., Piepho, H.-P."
date: 2026-05-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.30.715203v2.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 鲁棒随机森林用于基因组预测，可改进PRS预测准确性
tldr: 数据污染（如记录错误和极端异常值）会严重削弱随机森林在基因组预测中的性能。本研究针对响应变量污染，通过模拟和真实动植物育种数据，比较了预处理、算法修改和混合稳健化策略。结果表明数据转换策略整体最优，排名和加权稳健随机森林在污染下提供最佳预测与选择折衷。贡献在于提出了可推广的稳健化框架，为高维预测中何时及如何应用稳健化提供实践指导。
source: biorxiv
selection_source: fresh_fetch
motivation: 数据污染严重损害随机森林在基因组预测中的性能，亟需开发稳健化策略以提升污染下的预测准确性并指导实际应用。
method: 通过模拟动物育种数据评估预处理、算法级和混合稳健策略，并在多个真实动植物育种数据集上验证不同污染场景下的表现。
result: 数据转换策略最有效；排名和加权稳健随机森林在污染下提供最佳预测与选择折衷，但效益因数据集、性状和育种目标而异。
conclusion: 稳健化并非普遍必要，但在污染可能时至关重要；建议标准随机森林与稳健随机森林搭配使用，根据具体数据与目标选择最终模型。
---

## 摘要
数据污染——从记录错误到极端异常值——会通过使预测产生偏差、增大预测误差，在严重情况下还会在高维环境中破坏统计模型的稳定性。虽然污染会影响响应变量和协变量，但我们关注响应污染，并通过模拟评估随机森林。使用一个合成的动物育种数据集，我们在几种污染场景下评估鲁棒随机森林，并在植物和动物数据集上进行验证。我们从而阐明了污染对预测的影响，开发了一个鲁棒随机森林框架，并评估其性能。我们考察了预处理或数据转换策略、算法修改以及混合方法来实现随机森林的鲁棒化。在这些方法中，数据转换是最有效的策略，在污染下表现最佳。该策略简单、通用，并可迁移到其他机器学习方法，为鲁棒基因组预测提供了一种补救措施。在实际育种数据中，当存在大量污染、表型损坏、记录错误或训练-部署不匹配可能时，并且目标是恢复用于基因组预测和选择的潜在信号时，鲁棒随机森林是有用的；在这种情况下，基于排序和基于加权的鲁棒随机森林提供了互补的补救措施，后者通过以中位数为中心的公式，为收缩在不同响应分布之间提供了一致的解释。鲁棒化并非普遍必要，但当污染扭曲了观测响应与预测目标之间的联系时，它变得重要；标准随机森林依然是干净数据的默认选择，而每当可能存在污染时，应同时拟合鲁棒随机森林，最终选择由数据、性状和育种目标指导。

作者总结：机器学习（ML）方法广泛用于高维复杂数据的预测，诸如随机森林（RF）这样的监督学习方法已被证明对基因组预测（GP）和选择有效。然而，如果算法依赖于对异常观测敏感的传统数据驱动程序，其性能可能因数据污染而严重受损。因此，鲁棒化ML方法对于提高污染下的预测性能以及指导其在高维预测问题中的实际应用都很重要。为满足这一需求，我们开发了鲁棒的预处理、算法级和混合策略，以提高污染数据下RF的性能。利用模拟动物数据，我们表明基于排序和基于加权的鲁棒RF在污染下为基因组预测和选择提供了最强的整体折衷。在多个植物和动物育种数据集上的验证进一步表明，鲁棒化的好处并非普遍，而是取决于数据集、性状和育种目标。虽然以RF为动机，但我们提出的框架通用、实用，并易于迁移到其他ML方法。它还提供了一个基础，用于决定何时鲁棒性应补充标准RF而不是完全取代它。

## Abstract
Data contamination--from recording errors to extreme outliers--can compromise statistical models by biasing predictions, inflating prediction errors, and, in severe cases, destabilizing performance in high-dimensional settings. Although contamination can affect responses and covariates, we focus on response contamination and evaluate Random Forests through simulation. Using a synthetic animal-breeding dataset, we assess robust Random Forests across several contamination scenarios and validate them on plant and animal datasets. We thereby clarify the consequences of contamination for prediction, develop a robust Random Forest framework, and evaluate its performance. We examine preprocessing or data-transformation strategies, algorithmic modifications, and hybrid approaches for robustifying Random Forests. Across these approaches, data transformation emerges as the most effective strategy, delivering the strongest performance under contamination. This strategy is simple, general, and transferable to other Machine Learning methods, offering a remedy for robust genomic prediction. In real breeding data, robust Random Forests are useful when substantial contamination, phenotypic corruption, misrecording, or train-deployment mismatch is plausible and the goal is to recover a latent signal for genomic prediction and selection; in that setting, ranking-based and weighting-based robust Random Forests offer complementary remedies, the latter through a median-centred formulation that gives shrinkage a coherent interpretation across response distributions. Robustification is not universally necessary, but it becomes important when contamination distorts the link between observed responses and the predictive target; standard Random Forests remain the default for clean data, whereas robust Random Forests should be fitted alongside them whenever contamination is plausible, with the final choice guided by data, trait, and breeding objective.

Author summaryMachine learning (ML) methods are widely used for prediction with high-dimensional, complex data, and supervised approaches such as Random Forests (RF) have proved effective for genomic prediction (GP) and selection. Yet their performance can be severely compromised by data contamination if the algorithms rely on classical data-driven procedures that are sensitive to atypical observations. Robustifying ML methods is therefore important both for improving predictive performance under contamination and for guiding their practical use in high-dimensional prediction problems. To address this need, we develop robust preprocessing, algorithm-level, and hybrid strategies for improving RF performance with contaminated data. Using simulated animal data, we show that ranking- and weighting-based robust RF provide the strongest overall compromise for genomic prediction and selection under contamination. Validation on several plant and animal breeding datasets further shows that the benefits of robustification are not universal, but depend on the dataset, trait, and breeding objective. Although motivated by RF, the framework we propose is general, practical, and readily transferable to other ML methods. It also offers a basis for deciding when robustness should complement standard RF rather than replace it outright.