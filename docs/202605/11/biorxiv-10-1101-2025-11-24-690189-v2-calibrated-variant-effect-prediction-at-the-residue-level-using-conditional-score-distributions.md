---
title: Calibrated Variant Effect Prediction at the Residue Level Using Conditional Score Distributions
title_zh: 基于条件得分分布的残基水平校准变异效应预测
authors: "Passi, G., Amittai, S., Schneidman-Duhovny, D."
date: 2026-05-11
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.24.690189v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 残基水平的变异效应预测与校准
tldr: 本研究针对变异效应预测（VEP）模型在特定子群中校准不佳的问题，提出了残基水平的校准方法。通过分析24个VEP模型，发现其在子群层面存在显著失准。为此开发了RaCoon模型，利用条件得分分布进行差异化映射。RaCoon不仅在多个基准测试中实现了低校准误差，还显著提升了判别性能（如ProteinGym的AUROC），为临床应用提供了更可靠、可解释的预测工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有变异效应预测模型虽然平均校准良好，但在特定变异子群中存在显著的失准现象，限制了其临床可靠性。
method: 提出一种基于残基水平的条件得分分布校准方法，并据此开发了基于ESM1b的RaCoon模型，通过差异化得分映射实现多重校准。
result: RaCoon在保持低校准误差的同时，将ProteinGym基准测试的AUROC从0.909提升至0.916，展现出更强的判别能力。
conclusion: 残基级校准策略能有效提升VEP模型的可靠性与准确性，且该方法具有通用性，可推广至其他预测模型。
---

## 摘要
变异效应预测（VEP）的有效临床应用要求模型既准确又经过良好校准。校准是指模型产生有意义且可靠的概率估计的能力。通过对 24 种 VEP 进行基准测试，我们发现虽然模型在平均水平上可能表现出良好的校准性，但在特定的变异亚组内仍存在明显的失校准现象。我们提出了一种通过在残基水平进行校准来实现鲁棒 VEP 校准的实用路径，并引入了一种基于每个变异亚组差异化得分映射的校准方法。当校准目标选择得当时，我们的校准方法还可以提高模型的区分度。利用这些见解，我们开发了 RaCoon（基于条件分布的残基感知校准），并在 ESM1b 上实现，它提供了多重校准且具有可解释性的预测。RaCoon 在不同变异亚组和数据集上保持了较低的校准误差，同时还提高了多个基准测试的 AUROC。具体而言，RaCoon 将 ProteinGym 的 AUCROC 从 0.909 ± 0.000 提高到了 0.916 ± 0.001。我们的校准策略由模型特定的得分分布引导，可以很容易地迁移到其他 VEP。

## Abstract
Effective clinical use of variant effect prediction (VEP) requires models that are both accurate and well-calibrated. Calibration refers to a model's ability to produce meaningful and reliable probability estimates. Benchmarking 24 VEPs we show that while models may appear well calibrated on average, they remain markedly miscalibrated within specific variant subgroups. We propose a practical path toward robust VEP calibration by calibrating at the residue-level and introduce a calibration approach based on differential score mapping per variant subgroup. When calibration targets are chosen appropriately, our calibration approach can also improve model discrimination. Leveraging these insights, we develop RaCoon (Residue-aware Calibration via Conditional distributions), implemented on ESM1b, which provides multicalibrated and interpretable predictions. RaCoon maintains low calibration error across variant subgroups and datasets while also improving AUROC on multiple benchmarks. Specifically, RaCoon increases ProteinGym AUCROC from 0.909 {+/-} 0.000 to 0.916 {+/-} 0.001. Our calibration strategy, guided by model-specific score distributions, is readily transferable to other VEPs.