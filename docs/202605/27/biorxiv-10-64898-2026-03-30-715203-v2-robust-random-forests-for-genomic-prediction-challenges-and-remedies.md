---
title: "Robust Random Forests for Genomic Prediction: Challenges and Remedies"
title_zh: 面向基因组预测的鲁棒随机森林：挑战与解决方案
authors: "Lourenco, V. M., Ogutu, J. O., Piepho, H.-P."
date: 2026-05-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.30.715203v2.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 鲁棒随机森林用于基因组预测，与GWAS/PRS方法学相关
tldr: 数据污染（如记录错误和极端离群值）会严重损害随机森林在基因组预测中的性能。本文通过模拟污染场景和真实育种数据评估了多种稳健化策略，发现基于排名或加权中位数的数据转换方法最为有效，能稳定预测精度。稳健随机森林应在污染风险高时作为标准RF的补充，而非替代，最终选择需结合数据特征和育种目标。
source: biorxiv
selection_source: fresh_fetch
motivation: 数据污染导致随机森林预测偏差和误差增大，现有方法缺乏针对高维基因组数据的系统稳健化方案。
method: 构建预处理、算法修改和混合三类稳健策略，重点测试基于排名和加权中位数的稳健随机森林，在合成动物数据及多种植物动物育种数据集上验证。
result: 数据转换策略（排名和加权）在污染场景下预测性能最优，显著优于标准RF，但稳健化效果因数据集和性状而异。
conclusion: 稳健随机森林在高污染时有效，但非通用；建议与标准RF并行使用，根据污染程度和育种目标选择策略。
---

## 摘要
数据污染——从记录错误到极端异常值——会通过使预测产生偏差、增大预测误差，甚至在严重情况下破坏高维环境中的稳定性，从而损害统计模型。尽管污染会影响响应变量和协变量，但我们专注于响应污染，并通过模拟评估随机森林。使用合成动物育种数据集，我们评估了几种污染场景下的鲁棒随机森林，并在植物和动物数据集上进行了验证。由此，我们阐明了污染对预测的影响，开发了一个鲁棒随机森林框架，并评估了其性能。我们考察了预处理或数据转换策略、算法修改以及混合方法来增强随机森林的鲁棒性。在这些方法中，数据转换成为最有效的策略，在污染下提供了最强的性能。该策略简单、通用，并可迁移到其他机器学习方法，为鲁棒的基因组预测提供了一种补救措施。在实际育种数据中，当可能出现大量污染、表型损坏、错误记录或训练-部署不匹配，并且目标是恢复用于基因组预测和选择的潜在信号时，鲁棒随机森林是有用的；在这种情况下，基于排序和基于权重的鲁棒随机森林提供了互补的补救措施，后者通过以中位数为中心的公式，在响应分布之间赋予收缩一致的解释。鲁棒化并非普遍必要，但当污染扭曲了观察到的响应与预测目标之间的联系时，它就变得重要；标准随机森林仍然是干净数据的默认选择，而每当可能存在污染时，应将其与鲁棒随机森林一起拟合，最终选择由数据、性状和育种目标指导。

作者总结
机器学习（ML）方法广泛用于高维复杂数据的预测，诸如随机森林（RF）这样的监督方法已被证明在基因组预测（GP）和选择中有效。然而，如果算法依赖于对异常观测敏感的传统数据驱动过程，它们的性能可能会受到数据污染的严重损害。因此，鲁棒化ML方法对于在污染下提高预测性能以及指导其在高维预测问题中的实际使用都很重要。为了满足这一需求，我们开发了鲁棒的预处理、算法级和混合策略，以改善污染数据下的RF性能。使用模拟动物数据，我们展示了基于排序和基于权重的鲁棒RF在污染下为基因组预测和选择提供了最强的整体折衷方案。在几个植物和动物育种数据集上的进一步验证表明，鲁棒化的好处并非普遍存在，而是取决于数据集、性状和育种目标。尽管以RF为动机，我们提出的框架是通用的、实用的，并且易于迁移到其他ML方法。它还为基础，用于决定何时鲁棒性应补充标准RF而不是完全替代它。

## Abstract
Data contamination--from recording errors to extreme outliers--can compromise statistical models by biasing predictions, inflating prediction errors, and, in severe cases, destabilizing performance in high-dimensional settings. Although contamination can affect responses and covariates, we focus on response contamination and evaluate Random Forests through simulation. Using a synthetic animal-breeding dataset, we assess robust Random Forests across several contamination scenarios and validate them on plant and animal datasets. We thereby clarify the consequences of contamination for prediction, develop a robust Random Forest framework, and evaluate its performance. We examine preprocessing or data-transformation strategies, algorithmic modifications, and hybrid approaches for robustifying Random Forests. Across these approaches, data transformation emerges as the most effective strategy, delivering the strongest performance under contamination. This strategy is simple, general, and transferable to other Machine Learning methods, offering a remedy for robust genomic prediction. In real breeding data, robust Random Forests are useful when substantial contamination, phenotypic corruption, misrecording, or train-deployment mismatch is plausible and the goal is to recover a latent signal for genomic prediction and selection; in that setting, ranking-based and weighting-based robust Random Forests offer complementary remedies, the latter through a median-centred formulation that gives shrinkage a coherent interpretation across response distributions. Robustification is not universally necessary, but it becomes important when contamination distorts the link between observed responses and the predictive target; standard Random Forests remain the default for clean data, whereas robust Random Forests should be fitted alongside them whenever contamination is plausible, with the final choice guided by data, trait, and breeding objective.

Author summaryMachine learning (ML) methods are widely used for prediction with high-dimensional, complex data, and supervised approaches such as Random Forests (RF) have proved effective for genomic prediction (GP) and selection. Yet their performance can be severely compromised by data contamination if the algorithms rely on classical data-driven procedures that are sensitive to atypical observations. Robustifying ML methods is therefore important both for improving predictive performance under contamination and for guiding their practical use in high-dimensional prediction problems. To address this need, we develop robust preprocessing, algorithm-level, and hybrid strategies for improving RF performance with contaminated data. Using simulated animal data, we show that ranking- and weighting-based robust RF provide the strongest overall compromise for genomic prediction and selection under contamination. Validation on several plant and animal breeding datasets further shows that the benefits of robustification are not universal, but depend on the dataset, trait, and breeding objective. Although motivated by RF, the framework we propose is general, practical, and readily transferable to other ML methods. It also offers a basis for deciding when robustness should complement standard RF rather than replace it outright.